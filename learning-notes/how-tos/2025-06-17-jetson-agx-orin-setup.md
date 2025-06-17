# Steps to flash Jetson AGX Orin via Ubuntu 24.04 LTS Host

![[Pasted image 20250617144800.png]]

## Via SDK Manger

Step 1: Install [SDK Manager](https://developer.nvidia.com/sdk-manager)

Step 2: Install Jetson AGX Orin OS and driver va sdkmanager.

```bash
    sdkmanager --cli
```

Step 3: Select the following options  to JetPack 6.2 and Ubuntu 22.02 as base OS.

```bash
    - Select action: Install
    - Select product: Jetson
    - Select system configuration: Target Hardware
    - Select target hardware: Jetson AGX Orin modules
    - Select target operating system: Linux
    - Do you want to show all release versions? No
    - Select SDK version: JetPack 6.2
    - Select additional SDKs: None
    - Do you want to customize the install settings? Yes
    - Select optional components: Jetson Linux, Jetson Linux image, Flash Jetson Linux, Jetson Runtime Components, Additional Setups, DateTime Target Setup, Gstreamer, DLA Compiler, CUDA Runtime, CUDA Runtime, CUDA X-AI Runtime, CuDNN Runtime, TensorRT Runtime, Computer Vision Runtime, OpenCV Runtime, CuPVA Runtime, VPI Runtime, NVIDIA Container Runtime, NVIDIA Container Runtime with Docker integration (Beta), Multimedia, Multimedia API, Jetson SDK Components, CUDA, CUDA Toolkit for L4T, CUDA-X AI, CuDNN on Target, TensorRT on Target, Computer Vision, OpenCV, VPI on Target, Developer Tools, Nsight Systems, Nsight Graphics, Jetson Platform Services, Jetson Platform Services, Jetson Platform Services

    - Do you want to flash Jetson AGX Orin module? Yes
    - Download folder: /home/arralyze/Downloads/nvidia/sdkm_downloads
    - SDKs install folder: /home/arralyze/nvidia/nvidia_sdk
```

## Via Jestson Manual Instruction

Step 1: Follow the necessary steps from the [Jetson Developer Guide](https://docs.nvidia.com/jetson/archives/r36.4.3/DeveloperGuide/IN/QuickStart.html#types-and-models-of-jetson-devices).