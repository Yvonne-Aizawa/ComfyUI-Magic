# ComfyUI-Magic: 🔋Batteries🔋 included 

## Why

We're AI Art enthusiasts, developers, and artists. We wanted this to be easier for everyone to reliably use. 

This work began in discord channels and through serendipity - it felt wrong not to give this back to everyone, so we open sourced it here.

Preview: 

[![asciicast](https://asciinema.org/a/621943.svg)](https://asciinema.org/a/621943)

## Quick Start

1. Update your NVIDIA Drivers (only NVIDIA cards supported right now)
2. Install Docker and NVIDIA's container toolkit (Windows: Install WSL, then install Docker Desktop)
3. Run the following command if all you want is a ComfyUI: 
4. Have roughly 20GB of space ready for default models and room to grow for any others you might want to add!

```
docker run --name comfyui-magic -p 8188:8188 --gpus all -it --rm -v magic:/storage futrlabsmagic/comfyui-magic:latest
```

### Run it as a service

```
docker run -d --name comfyui-magic --restart=unless-stopped -p 8188:8188 --gpus all -it -v magic:/storage futrlabsmagic/comfyui-magic:latest
```

### Auto accept terms and run as service
```
docker run -e AUTOACCEPT=yes -d --name comfyui-magic --restart=unless-stopped -p 8188:8188 --gpus all -it -v magic:/storage futrlabsmagic/comfyui-magic:latest
```



## Features

### Prepackaged Custom Nodes for Your Sanity

Currently, we automatically bake in stable mixtures of these popular custom nodes:

- https://github.com/ltdrdata/ComfyUI-Inspire-Pack.git
- https://github.com/ltdrdata/ComfyUI-Impact-Pack.git 
- https://github.com/cubiq/ComfyUI_IPAdapter_plus.git 
- https://github.com/storyicon/comfyui_segment_anything.git 
- https://github.com/Gourieff/comfyui-reactor-node.git  
- https://github.com/WASasquatch/was-node-suite-comfyui.git 
- https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git
- https://github.com/RockOfFire/ComfyUI_Comfyroll_CustomNodes.git
- https://github.com/Kosinkadink/ComfyUI-Advanced-ControlNet
- https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite
- https://github.com/Fannovel16/comfyui_controlnet_aux
- https://github.com/jags111/efficiency-nodes-comfyui
- https://github.com/Kosinkadink/ComfyUI-AnimateDiff-Evolved.git
- https://github.com/Fannovel16/ComfyUI-Frame-Interpolation.git

### Automatic downloading of models at boot

We place a sample "extra_downloads.yml" file in your storage directory. 

Edit that file to download and place any custom models you'd like to have, then restart the container and watch the magic.

See this file for our default models we download at boot: [extra_downloads.yml](extra_downloads.yml)

To add your own models, take note that the `path` item in the yml is the path inside the container. 

All paths should generally use `/storage/ComfyUI/.../...` unless you have very good reason not to.

Once the file is placed for the first time in your storage directory, it won't be overwritten again.
