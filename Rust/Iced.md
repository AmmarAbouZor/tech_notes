## Hybrid Laptop

At the time it seems that Iced can't figure out which graphic card to choose in the case of Vulkan. To set them manually we must set the environment variable `VK_ICD_FILENAMES` to the configuration file.
#### Here is to set it to nvidia
`VK_ICD_FILENAMES=/usr/share/vulkan/icd.d/nvidia_icd.x86_64.json`
#### Here is to set it to Intel
`VK_ICD_FILENAMES=/usr/share/vulkan/icd.d/intel_icd.x86_64.json`

Vulkan config files are in the path  `/usr/share/vulkan/icd.d/` there is a one for each graphic card type 

## Rendering Images on Linux

Rendering PNG Images on Linux works currently only with Vulkan. To set vulkan as back-end you need to set the environment variable:  
`WGPU_BACKEND=vulkan`