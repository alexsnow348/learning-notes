---
category: development-related-script
tags:
  - data_engineer
  - mlops
  - devops
title: Set Up Window Network Share to Linux System mount (data folder)
---
c# Set Up Window Network Share to Linux System mount (data folder)
----

## Steps:

1.  Create data folder on the host Ubuntu Linux sever where the data are needed to map.
```bash
sudo mkdir /data/<your_linux_ubuntu_folder_path>
```
2. Install required ubuntu system library.
```bash
sudo apt-get install cifs-utils
```
3. Map the Window Network share drive with Ubuntu folder.
```bash
sudo mount -t cifs -o username=<your_username>,domain=<your_domain_name>  <your_window_network_share_path>  <your_linux_ubuntu_folder_path>

# sample command
sudo mount -t cifs -o username=<your_username>,domain=LPKF.com //10.10.10.45/ARRALYZE_Picture /data/biolab_arralyze_picture_data

```
4. Set up the mount for auto reboot operation.
```bash
sudo vim /etc/mycredentials
# insert following to above file
username=<your_username>
password=<your_password>
domain=LPKF.com

sudo chmod 600 /etc/mycredentials
sudo vim /etc/fstab
# insert the following to above file
//10.10.10.45/ARRALYZE_Picture /data/biolab_arralyze_picture_data cifs credentials=/etc/mycredentials,iocharset=utf8 0 0
```

## References

1. [Window Network Share to Linux System mount (data folder)](https://www.thomas-krenn.com/de/wiki/Windows_Freigabe_unter_Linux_mounten#smbfs))
