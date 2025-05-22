# Set Up Triton Inference Server in Ubuntu 24.04 LTS VM in Hyper V in Window 11
---- 
*Note: Make sure you have permission to turn on Hyper V Virtualization on Window 11*
## Steps:

1. Download the Ubuntu ISO Image of 12.04 LTS version from [here](https://ubuntu.com/download/desktop)
2. Create new VM instance  with Generation 2 Version of VM Instance. And maker VM setting of Boot Setup Order to boot from DVD Drive.
3. Make sure Enable Secure Boot under Security turn-off from both VM Setting and Hyper-V settings.
4. Disable Enhanced Session Mode in Hyper-V settings. This has been reported to resolve the issue for some users. To do this:
    - Open Hyper-V Manager and  Right-click on the Ubuntu VM and select “Hyper V Settings”
    - Navigate to “Enhanced Session  Mode Policy ” and toggle off “Allow Enhanced Session Mode”
    -  Under Enhanced Session Mode, and toggle off "Use enhanced session mode"
5. Update grub file to solve display issue - CRCL + ALT + F5 to trigger the terminal logged in 
6. Install net-tools to check for network configuration of VM instance.
```bash
sudo apt install net-tools vim 
```
```bash 
sudo vim /etc/default/grub

GRUB_CMDLINE_LINUX_DEFAULT="video=hyperv_fb:1920x1080"
GRUB_TERMINAL=console

sudo update-grub
```

7. Create 99verify_peer to allow for unsecured download apt get 
```bash
vim /etc/apt/apt.conf.d/99verify-peer
# Add this into 99verify-peer file
Acquire::https::download.docker.com::Verify-Peer "false";
Acquire::https::nvidia.github.io::Verify-Peer "false";
```
8. Install docker in VM.
```bash
#!/bin/bash

sudo apt-get update

sudo apt-get -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

curl -k -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt-get update
sudo apt-get -y install docker-ce docker-ce-cli containerd.io
sudo apt-get -y install docker-compose-plugin
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

- Add the following line in the `/etc/docker/daemon.json` file in Ubuntu:
    
    ```json
    {
        "runtimes": {
            "nvidia": {
                "args": [],
                "path": "nvidia-container-runtime"
            }
        },
        "insecure-registries": ["nvcr.io"]
    }
    ```
    
- Restart Docker service by running the following command in Ubuntu:
    
	```bash
    sudo systemctl restart docker
    ```

 - Pull Triton Inference Server Image from nvcr.io docker registry
```bash
docker pull nvcr.io/nvidia/tritonserver:24.03-py3
```

9. Set Up for on boot application loading process for Ubuntu VM

	- In the Settings window, under the `Management` section, click on `Automatic Start Action`
	- Select `Always start this virtual machine automatically`. Click Apply.
	
10. Set Up for on boot application loading process for Hyper V
    
    - Press `Win + R`, type `services.msc`, and press Enter.
    - Look for the following services:
        - `Hyper-V Virtual Machine Management`
        - `Hyper-V Host Compute System`
        - `Hyper-V Guest Service Interface`
        - `Hyper-V Remote Desktop Virtualization Service`
	- **Set Startup Type:**
	    - Right-click on each service and select `Properties`.
	    - Set the `Startup type` to `Automatic`.
	    - Click `Apply` and then `OK`.