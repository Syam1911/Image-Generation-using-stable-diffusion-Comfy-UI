# Image-Generation-using-stable-diffusion-Comfy-UI

# Clone the ComfyUI repository
git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI

# Install dependencies
pip install -r requirements.txt

After the installation of ComfyUI software, open it and choose CPU or GPU to run as per your availabilty.
In the next step, we'll see the node arrangemnet as default with checkpoint node as input.

# Stable Diffusion v1.5 Model
Download here ---> https://civitai.com/models/62437/v1-5-pruned-emaonly

# Image Generation Workflow
# 1. Input node
Load the downloaded .safetensors model in the load checkpoints node which is an input node for our workflow.
{
    "seed": 314981253044060,
    "steps": 20,
    "cfg": 7.0,
    "sampler_name": "euler",
    "scheduler": "exponential",
    "denoise": 1.00
}
