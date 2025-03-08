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

# 2. Prompt node

**positive prompt:** (masterpiece, best quality, ultra-detailed, 8K), breathtaking mountain landscape, crystal-clear lake, vibrant green forest, golden sunlight, soft mist, perfect reflections, ultra-realistic nature photography, depth of field, stunning composition.<br>
**negative prompt:** (low quality, blurry, pixelated, overexposed, unnatural colors, noisy background, flat lighting, text, watermark, distorted perspective)<br>

# 3. Empty Latent Image

This is considered to determine the result in out desired dimensions.

# 4. K Sampler

The parameters considered for the generation of background images for content creation was shown in the below figure. The inputs for this node are:<br>
-> model<br>
-> positive prompt<br>
-> negative prompt<br>
-> latent_image<br>
{<br>
    "seed": 314981253044060,<br>
    "control_after_generate": randomize,<br>
    "steps": 20,<br>
    "cfg": 7.0,<br>
    "sampler_name": "euler",<br>
    "scheduler": "exponential",<br>
    "denoise": 1.00<br>
}<br>

# 5. VAE Decode & Preview Image

-- The node is used to map the values from Ksampler tries to generate the accurate image as per the prompts given. <br>
-- The preview node will be the result image ultimately.<br>
-- We can also save these images by right-click --> Save Image. <br>
-- Or Directly, add the node "Save Image" this will perform the save operation on every time the preview image generated.<br>
