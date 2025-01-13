# stable-diffusion-webui_AUTOMATIC1111_v1_1.ipynb

このノートブックでは、Google Colab上でAUTOMATIC1111氏が開発したStable Diffusion web UIのv1.1を実行するための完全なセットアップを提供します。モデル、LoRA、VAE、Embedding、ControlNet、拡張機能のダウンロードなど、さまざまな機能が含まれています。

## 免責事項

*   このコードは**現状のまま**提供され、一切の保証をしません。
*   このコードの利用によって生じたいかなる損害についても、一切の責任を負いません。
*   **生成された画像に関する責任は、すべて利用者自身にあります。**
*   **成人向けコンテンツや、他者の権利を侵害する画像の生成には、十分注意してください。**
*   **各生成モデル、LoRA、VAE、Embedding、ControlNet モデル、拡張機能のライセンス情報を必ず確認し、利用規約を遵守してください。**
*   **本コードは、すべてのモデル、LoRA、VAE、Embedding、ControlNet モデル、拡張機能がそれぞれのライセンス条項内で利用できることを保証するものではありません。**

## ライセンス

このコードは、[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/) の下で提供されています。ただし、以下の追加条項が適用されます。

*   **本コード（または改変版）の販売は許可されません。**

これは以下のことを意味します。

*   **表示 (Attribution, BY):**  改変版を配布する際は、元の作者を適切にクレジット表示する必要があります。
*   **継承 (ShareAlike, SA):**  このコードを改変したものを配布する際は、元のライセンス（コードの販売禁止を含む）と同じライセンスを適用する必要があります。
*   このライセンスの条項に従い、商用または非商用目的で素材を自由に共有および翻案できます。
    * 注意: 生成された画像は商用・非商用を問わず自由に使用できます。ただし、コード自体を販売することはできません。

## 使用方法

1.  **Googleドライブのマウント:** 最初のセルでは、Googleドライブを`/content/drive`にマウントし、ノートブックからドライブのデータにアクセスしたり保存したりできるようにします。

2.  **ディレクトリの設定:** 2番目のセルでは、Stable Diffusion Web UI、モデル、VAE、LoRA、Embedding、拡張機能などのディレクトリパスの変数を定義します。

    ```python
    webui_dir = "/content/stable-diffusion-webui"
    model_dir = f"{webui_dir}/models/Stable-diffusion"
    vae_dir = f"{webui_dir}/models/VAE"
    lora_dir = f"{webui_dir}/models/Lora"
    embedding_dir = f"{webui_dir}/embeddings"
    extension_dir = f"{webui_dir}/extensions"
    ```

3.  **Stable Diffusion Web UIのクローン:** 3番目のセルでは、GitHubからAUTOMATIC1111のWeb UIリポジトリをクローンし、必要なディレクトリが存在しない場合は作成します。

4.  **依存関係のインストール:** 4番目のセルでは、`xformers`や、Stable Diffusion Web UIが正しく機能するために必要な`torch`、`torchvision`、`torchaudio`の特定のバージョンを含む、必要なライブラリをインストールします。

5.  **トークンの設定:** 5番目のセルでは、環境変数またはGoogle Colabのシークレットから取得したHugging FaceとCivitai APIキーを使用してログインを試みます。

6.  **ダウンロード機能:** 6番目のセルでは、`wget`、`urllib.request`を使用してファイルをダウンロードしたり、ローカルファイルをコピーするためのユーティリティ関数を定義します。これらの関数には、ユーザーフィードバック用のプログレスバー更新も含まれています。

7.  **モデルのダウンロード選択:** 7番目のセルでは、Hugging Faceやローカルストレージから、実写系、イラスト系、セミリアル系モデルを含むモデルのセットを定義します。ユーザーはチェックボックスを使用してダウンロードする特定のモデルを選択できます。
    *   各モデルのエントリでは、`source`（"url"または"local"）、`url`または`local_path`、`path`、および`checked`ステータスを指定します。

8. **Civitaiモデルのダウンロード:** このセルでは、チェックボックスを使用してCivitaiからモデルをダウンロードするためのUIを提供します。ユーザーは、Colab SecretsにCivitai APIトークンを設定する必要があります。

9.  **LoRAのダウンロード選択:** 8番目のセルでは、ユーザーはチェックボックスを使用して、Hugging FaceおよびローカルストレージからLoRAモデルを選択してダウンロードできます。
    *   モデルと同様に、LoRAエントリには`source`、`url`または`local_path`、`path`、および`checked`ステータスが含まれます。

10. **VAEのダウンロード選択:** 9番目のセルでは、Hugging FaceからVAEファイルをダウンロードするためのインターフェースを提供します。VAE（変分オートエンコーダ）モデルは、クリアで高品質な画像を生成するために不可欠です。

11. **Embeddingのダウンロード選択:** 10番目のセルでは、Hugging FaceからEmbeddingファイルをダウンロードできます。Embeddingは、モデルがプロンプトを理解するのを微調整するために使用されます。

12. **Civitai Embeddingのダウンロード:** このセルでは、チェックボックスを使用してCivitaiからEmbeddingをダウンロードするためのUIを提供します。ユーザーは、Colab SecretsにCivitai APIトークンを設定する必要があります。

13. **Upscaleモデルの手順:** このセルでは、ホスティングの制限により、手動でアップスケールモデル（4x-UltraSharpと4x-AnimeSharp）をダウンロードする場所と、それらを正しいディレクトリに配置する方法に関するガイダンスを提供します。

14. **ControlNetモデルのダウンロード:** 11番目のセルでは、ControlNet拡張機能をインストールし、さまざまな入力条件（例：エッジ検出、深度マップ、人物のポーズなど）に基づいて画像生成を可能にするControlNetモデルをダウンロードするためのインターフェイスを提供します。SD 1.5およびSDXL用のモデルが含まれています。
    *   コードには、特定の顔の特徴を持つ画像を生成できるIP-Adapter-FaceIDに必要なファイルのインストールとダウンロードも含まれます。

15. **拡張機能のダウンロード:** このセルでは、画像のアップスケーリング、アニメーションの作成など、Stable Diffusion WebUIに追加機能を追加するさまざまな便利な拡張機能をインストールします。

16.  **Web UIの開始:** 最後のセルでは、必要なオプション（`--share`、`--xformers`、`--enable-insecure-extension-access`）を指定して`launch.py`スクリプトを実行し、Stable Diffusion Web UIを開始します。Web UIのURLが表示されます。

## 注意点

*   パフォーマンスは、Google Colabの利用状況とGPUの可用性によって異なる場合があります。
*   モデルのダウンロードと画像の生成には時間がかかる場合があります。ダウンロードが完了するまでお待ちください。
*   最新情報を参照し、必要に応じてコードを更新してください。
*   エラーが発生した場合は、出力メッセージを注意深く確認し、必要な依存関係がすべてインストールされていることを確認してください。
*   Colab環境は動的であり、予期しない動作が発生する可能性があります。コードがセクションの順序に従って上から下まで実行されていることを確認してください。
*   拡張機能の使用はパフォーマンスに影響を与える可能性があります。セッション中に必要な拡張機能のみを有効にすることをお勧めします。

## モデル、LoRA、VAE、Embedding、ControlNet、拡張機能のライセンスについて

*   Hugging Face、Civitai、GitHubなどのそれぞれの配布元から、使用する各Stable Diffusionモデル、LoRA、VAE、Embedding、ControlNetモデル、拡張機能のライセンスを確認してください。
*   各コンポーネントの使用条件を遵守し、著作権を侵害しないでください。
*   **本コードは、すべてのモデル、LoRA、VAE、Embedding、ControlNetモデル、および拡張機能が、それぞれのライセンス条項内で利用できることを保証するものではありません。**
*   商用利用を制限したり、クレジット表記が必要なライセンスには特に注意してください。

## 参照

[safa-dayo/sd-webui-google-colab-setup.sh](https://gist.github.com/safa-dayo/b25f3737675c7667fefb51498dbf7212)

## 謝辞

*   このコードは、AUTOMATIC1111氏によるStable Diffusion web UIを基に作成しました。
*  また、モデル、LoRA、VAE、Embedding、ControlNet、拡張機能を共有してくださったクリエイターの方々に感謝いたします。
