# Using-stable-diffusion-webui-in-Google-Colab

This repository provides complete setups for running Stable Diffusion web UI by AUTOMATIC1111 on Google Colab. It includes various features such as downloading models, LoRAs, VAEs, Embeddings, ControlNets, and extensions.

## Disclaimer

*   This code is provided **as is** without any warranty.
*   We are not responsible for any damages caused by the use of this code.
*   **You are solely responsible for the images you generate.**
*   **Be careful not to generate adult content or images that infringe on the rights of others.**
*   **Always check the license information for each generation model, LoRA, VAE, Embedding, ControlNet model, and extension, and comply with the terms of use.**
*   **This code does not guarantee that all models, LoRAs, VAEs, Embeddings, ControlNet models, and extensions are available under their respective license terms.**

## License

This code is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/). However, the following additional clause applies:

*   **Selling this code (or modified versions) is not permitted.**

This means:

*   **Attribution (BY):** You must give appropriate credit to the original author when distributing modified versions.
*   **ShareAlike (SA):** If you distribute derivative works, you must license them under the same license (including the prohibition of selling the code) as the original.
*   You are free to share and adapt the material for any purpose, commercial or non-commercial, as long as you comply with the terms of this license.
    * Note: Generated images can be freely used for commercial and non-commercial purposes. However, the code itself cannot be sold.

## Notebooks

This repository includes the following notebooks:

| Notebook                                          | Description                                                                                                                                                                                             | <div style="text-align: center;">GitHub Link</div>                                                                                                                              | <div style="text-align: center;">Colab Link</div>                                                                                                                                |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `stable-diffusion-webui_AUTOMATIC1111_v1_0.ipynb` | This notebook provides a complete setup to run Stable Diffusion web UI by AUTOMATIC1111 on Google Colab. It downloads **a limited set of models**, LoRAs, VAEs, Embeddings, ControlNets, and extensions using **individual processing** for all download tasks. This approach is more reliable but may take longer to complete downloads.  | <div style="text-align: center;">[<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="20" height="20" alt="GitHub" />](https://github.com/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_0.ipynb)</div> | <div style="text-align: center;">[<img src="https://colab.research.google.com/img/colab_favicon_256px.png" width="20" height="20" alt="Colab" />](https://colab.research.google.com/github/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_0.ipynb)</div> |
| `stable-diffusion-webui_AUTOMATIC1111_v1_1.ipynb` | This notebook also sets up Stable Diffusion web UI on Google Colab with the same downloading capabilities, but supports **a large selection of models**, and utilizes **parallel processing for Hugging Face downloads**, which significantly speeds up the process. However, **Civitai downloads are processed individually** to avoid errors, providing a balance between speed and stability.       | <div style="text-align: center;">[<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="20" height="20" alt="GitHub" />](https://github.com/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_1.ipynb)</div> | <div style="text-align: center;">[<img src="https://colab.research.google.com/img/colab_favicon_256px.png" width="20" height="20" alt="Colab" />](https://colab.research.google.com/github/yf591/Using-stable-diffusion-webui-in-Google-Colab/blob/main/stable_diffusion_webui_AUTOMATIC1111_v1_1.ipynb)</div> |
## Usage

1.  Open the desired notebook in Google Colab.
2.  Run the cells in order.
3.  Follow the prompts to authorize access to your Google Drive, if necessary.
4.  Use the checkboxes to select the models, LoRAs, VAEs, Embeddings, and extensions you want to download.
5.  Wait for the downloads to complete.
6.  Run the final cell to launch the Stable Diffusion Web UI.
7.  Use the displayed URL to access the Web UI.

## Notes

*   Performance may vary depending on Google Colab's usage and GPU availability.
*   Downloading models and generating images may take some time. Please be patient while the downloads complete.
*   Refer to the latest information and update the code if necessary.
*   If you encounter errors, carefully check the output messages and make sure all required dependencies are installed.
*   Colab environments are dynamic, and unexpected behavior may occur. Make sure the code is executed in order from top to bottom of the section.
*   The use of extensions can affect performance. It is recommended to enable only the necessary extensions during the session.

## About Licenses for Models, LoRAs, VAEs, Embeddings, ControlNets, and Extensions

*   Please check the licenses for each Stable Diffusion model, LoRA, VAE, Embedding, ControlNet model, and extension you use from their respective distributors such as Hugging Face, Civitai, and GitHub.
*   Comply with the terms of use for each component and do not infringe on copyrights.
*   **This code does not guarantee that all models, LoRAs, VAEs, Embeddings, ControlNet models, and extensions are available under their respective license terms.**
*   Pay special attention to licenses that restrict commercial use or require credit.

## References

[safa-dayo/sd-webui-google-colab-setup.sh](https://gist.github.com/safa-dayo/b25f3737675c7667fefb51498dbf7212)

## Acknowledgments

*   This code is based on the Stable Diffusion web UI by AUTOMATIC1111.
*   We would also like to thank the creators who have shared their models, LoRAs, VAEs, Embeddings, ControlNets, and extensions.
