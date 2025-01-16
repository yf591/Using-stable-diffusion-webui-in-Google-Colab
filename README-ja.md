# Using-stable-diffusion-webui-in-Google-Colab

このリポジトリでは、Google Colab上でAUTOMATIC1111氏が開発したStable Diffusion web UIを実行するための完全なセットアップを提供します。モデル、LoRA、VAE、Embedding、ControlNet、拡張機能のダウンロードなど、さまざまな機能が含まれています。

## 免責事項

*   このコードは**現状のまま**提供され、一切の保証をしません。
*   このコードの利用によって生じたいかなる損害についても、一切の責任を負いません。
*   **生成された画像に関する責任は、すべて利用者自身にあります。**
*   **成人向けコンテンツや、他者の権利を侵害する画像の生成には、十分注意してください。**
*   **各生成モデル、LoRA、VAE、Embedding、ControlNetモデル、拡張機能のライセンス情報を必ず確認し、利用規約を遵守してください。**
*   **本コードは、すべてのモデル、LoRA、VAE、Embedding、ControlNet モデル、拡張機能がそれぞれのライセンス条項内で利用できることを保証するものではありません。**

## ライセンス

このコードは、[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/) の下で提供されています。ただし、以下の追加条項が適用されます。

*   **本コード（または改変版）の販売は許可されません。**

これは以下のことを意味します。

*   **表示 (Attribution, BY):**  改変版を配布する際は、元の作者を適切にクレジット表示する必要があります。
*   **継承 (ShareAlike, SA):**  このコードを改変したものを配布する際は、元のライセンス（コードの販売禁止を含む）と同じライセンスを適用する必要があります。
*   このライセンスの条項に従い、商用または非商用目的で素材を自由に共有および翻案できます。
    * 注意: 生成された画像は商用・非商用を問わず自由に使用できます。ただし、コード自体を販売することはできません。

## ノートブック一覧

このリポジトリには、以下のノートブックが含まれています。

| Notebook                                          | 説明                                                                                                                       | <div style="text-align: center;">GitHub Link</div>                                                                                                                              | <div style="text-align: center;">Colab Link</div>                                                                                                                                |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `stable-diffusion-webui_AUTOMATIC1111_v1_0.ipynb` | このノートブックは、Google Colab上でAUTOMATIC1111氏によるStable Diffusion web UIを実行するための完全なセットアップを提供します。少数のモデル、LoRA、VAE、Embedding、ControlNet、拡張機能をダウンロードする際、すべてのダウンロードタスクに個別処理を使用します。このアプローチはより安定していますが、ダウンロード完了に時間がかかる場合があります。                                      | <div style="text-align: center;">[<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="20" height="20" alt="GitHub" />](https://github.com/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_0.ipynb)</div> | <div style="text-align: center;">[<img src="https://colab.research.google.com/img/colab_favicon_256px.png" width="20" height="20" alt="Colab" />](https://colab.research.google.com/github/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_0.ipynb)</div> |
| `stable-diffusion-webui_AUTOMATIC1111_v1_1.ipynb` | このノートブックも、Google Colab上でStable Diffusion web UIをセットアップし、同様のダウンロード機能を提供しますが、多数のモデルに対応しており、Hugging Faceからのダウンロードには並列処理を利用し、プロセスを大幅に高速化します。ただし、Civitaiからのダウンロードはエラーを避けるために個別処理で行い、速度と安定性のバランスを取っています。 | <div style="text-align: center;">[<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="20" height="20" alt="GitHub" />](https://github.com/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_1.ipynb)</div> | <div style="text-align: center;">[<img src="https://colab.research.google.com/img/colab_favicon_256px.png" width="20" height="20" alt="Colab" />](https://colab.research.google.com/github/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_1.ipynb)</div> |

## 使用方法

1.  Google Colabで目的のノートブックを開きます。
2.  セルを順番に実行します。
3.  必要に応じて、Googleドライブへのアクセスを許可します。
4.  チェックボックスを使用して、ダウンロードするモデル、LoRA、VAE、Embedding、拡張機能を選択します。
5.  ダウンロードが完了するまで待ちます。
6.  最後のセルを実行して、Stable Diffusion Web UIを起動します。
7.  表示されたURLを使用してWeb UIにアクセスします。

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
*   また、モデル、LoRA、VAE、Embedding、ControlNet、拡張機能を共有してくださったクリエイターの方々に感謝いたします。
