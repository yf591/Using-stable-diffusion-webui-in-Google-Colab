# stable-diffusion-webui_AUTOMATIC1111_v1_1.ipynb

This notebook provides a complete setup to run the AUTOMATIC1111 Stable Diffusion web UI v1.1 on Google Colab. It includes various features for downloading models, LoRAs, VAEs, embeddings, ControlNet models, and extensions.

## Disclaimer

*   This code is provided **as is**, without any warranty.
*   The user assumes all responsibility for any damages that may arise from using this code.
*   **The user is solely responsible for the content of the generated images.**
*   **Exercise caution when generating mature content or images that may infringe on the rights of others.**
*   **Always verify the license information for each generative model, LoRA, VAE, embedding, ControlNet model, and extension you use, and adhere to their terms of service.**
*   **This code does not guarantee that all models, LoRAs, VAEs, embeddings, ControlNet models, and extensions can be used within their respective license terms.**

## License

This code is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/), with the following additional restriction:

*   **You are not allowed to sell this code (or modified versions of it).**

This means:

*   **Attribution:** You must give appropriate credit to the original author when distributing modified versions.
*   **ShareAlike:** If you modify this code, you must distribute your contributions under the same license (including the additional restriction against selling the code).
*   You are free to share and adapt the material under the terms of this license, for both commercial and non-commercial use.
    * Note: You are free to utilize the generated images for both commercial and non-commercial use, however you cannot sell the code itself.

## Usage

1.  **Google Drive Mounting:** The first cell mounts your Google Drive to `/content/drive`, allowing the notebook to access and save data on your drive.

2.  **Setting up Directories:** The second cell defines variables such as the directory paths for Stable Diffusion Web UI, models, VAEs, LoRAs, embeddings, and extensions.

    ```python
    webui_dir = "/content/stable-diffusion-webui"
    model_dir = f"{webui_dir}/models/Stable-diffusion"
    vae_dir = f"{webui_dir}/models/VAE"
    lora_dir = f"{webui_dir}/models/Lora"
    embedding_dir = f"{webui_dir}/embeddings"
    extension_dir = f"{webui_dir}/extensions"
    ```

3.  **Cloning Stable Diffusion Web UI:** The third cell clones the AUTOMATIC1111 web UI repository from GitHub and creates the necessary directories if they don't exist.

4.  **Installing Dependencies:** The fourth cell installs required libraries including `xformers` and specific versions of `torch`, `torchvision`, and `torchaudio` to ensure the Stable Diffusion web UI functions correctly.

5.  **Setting up Tokens:** The fifth cell attempts to log in using Hugging Face and Civitai API keys obtained from environment variables or Google Colab secrets.

6.  **Download Functions:** The sixth cell defines utility functions for downloading files using `wget`, `urllib.request`, and copying local files. These functions also include progress bar updates for user feedback.

7.  **Model Download Selection:** The seventh cell defines a set of models, including real-life, illustration-based, and semi-realistic models from Hugging Face and local storage. Users can select specific models to download using checkboxes.
    *   Each model entry specifies its `source` ("url" or "local"), `url` or `local_path`, `path`, and `checked` status.

8. **Civitai Model Download:** This cell provides UI for downloading models from Civitai via check boxes. The user must set the Civitai API token in Colab Secrets.

9.  **LoRA Download Selection:** The eighth cell allows users to select and download LoRA models from Hugging Face and local storage, using checkboxes.
    *   Similar to models, LoRA entries include `source`, `url` or `local_path`, `path`, and `checked` status.

10. **VAE Download Selection:** The ninth cell provides an interface to download VAE files from Hugging Face. VAE (Variational Autoencoder) models are crucial for generating clear and high-quality images.

11. **Embedding Download Selection:** The tenth cell enables users to download embedding files from Hugging Face. Embeddings are used for fine-tuning the model’s understanding of prompts.

12. **Civitai Embedding Download:** This cell provides UI for downloading embeddings from Civitai via check boxes. The user must set the Civitai API token in Colab Secrets.

13. **Upscale Model Instructions:** This cell provides guidance on where to manually download upscale models (4x-UltraSharp and 4x-AnimeSharp) due to hosting limitations and how to place them in the correct directory.

14. **ControlNet Model Download:** The eleventh cell installs the ControlNet extension and provides an interface to download ControlNet models, which allow for image generation based on various input conditions (e.g., edge detection, depth maps, human poses, etc). Includes models for SD 1.5 and SDXL.

    *  The code also installs and downloads necessary files for IP-Adapter-FaceID, which allow for generating images with specific facial features.

15. **Extension Download:** This cell installs various useful extensions that add additional functionality to the Stable Diffusion WebUI such as image upscaling, animation creation, and more.

16.  **Starting Web UI:** The last cell executes the `launch.py` script with necessary options (`--share`, `--xformers`, and `--enable-insecure-extension-access`), starting the Stable Diffusion web UI. The Web UI URL will be printed.

## Notes

*   The performance may vary depending on Google Colab's utilization and GPU availability.
*   Downloading models and generating images can take time. Be patient while the downloads complete.
*   Refer to the latest information and update the code if necessary.
*   If you encounter any errors, please carefully check the output messages and ensure you have installed all the required dependencies.
*   The Colab environment is dynamic, which may result in some unexpected behaviors. Please make sure the code is run from top to bottom, following the order of the sections.
*   The usage of extensions may affect the performance. It is recommended that only necessary extensions be enabled during a session.

## About Model, LoRA, VAE, Embedding, ControlNet, and Extension Licenses

*   Please check the license of each Stable Diffusion model, LoRA, VAE, embedding, ControlNet model, and extension you use from their respective distribution sources (Hugging Face, Civitai, or GitHub).
*   Please comply with the terms of use of each component and do not infringe on copyrights.
*   **This code does not guarantee that all models, LoRAs, VAEs, embeddings, ControlNet models, and extensions can be used within their respective license terms.**
*   Be particularly mindful of licenses that restrict commercial use or require attribution.

## Reference

[safa-dayo/sd-webui-google-colab-setup.sh](https://gist.github.com/safa-dayo/b25f3737675c7667fefb51498dbf7212)

## Acknowledgements

*   This code is based on the Stable Diffusion web UI by AUTOMATIC1111.
*  We also acknowledge the generous contributions of the model, LoRA, VAE, embedding, ControlNet, and extension creators for sharing their work.
