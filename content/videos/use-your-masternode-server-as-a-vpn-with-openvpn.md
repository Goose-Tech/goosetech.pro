---
title: "Use Your Masternode Server as a VPN with OpenVPN - Protect Your Data for Free!"
image: images/videos/134.jpg
date: 2018-10-31T12:00:00-05:00
draft: false
type: "videos"
author: Goose-Tech
tags: ["crypto", "masternode", "vultr", "VPS", "OpenVPN", "VPN", "tutorial"]
---

#### VIDEO

{{< youtube a8srTofTn84 >}}

&nbsp;

#### DESCRIPTION

Most MasterNode servers have additional resources and available bandwidth to run double as Virtual Private Network Access Servers (VPN). While the MasterNode is busy paying for itself, you might as well use the remaining resources as a VPN to secure your own internet connection and responsibly protect your data. I show you how in the video.

📘Table of Contents:  
◆ 00:08 Intro  
◆ 00:25 OpenVPN Website & Explanation  
◆ 03:55 Vultr Setup  
◆ 06:30 Putty Terminal Download  
◆ 06:45 Login to VPS w/Putty  
◆ 07:37 Install Updates & Create Swap space  
◆ 13:30 Download & Install OpenVPN  
◆ 15:28 Configure OpenVPN Server  
◆ 19:30 Setup OpenVPN Client  
◆ 22:16 Final Thoughts  
●▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬●  
⭐Links:  
💻Vultr VPS Hosting Service: https://goo.gl/pU7ph3  
💻OpenVPN: https://openvpn.net/get-open-vpn/  
💻Putty Client: https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html  
●▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬●  
⌨Commands:  
(Run as root)

#### Swap Space Creation:
---
Show free space:  
`free -h`  
Check available HDD space:  
`df -h`  
Create swap:  
`'fallocate -l 3G /swapfile`  
Modify permissions:  
`chmod 600 /swapfile`  
Make swap:  
`mkswap /swapfile`  
Enable swap:  
`swapon /swapfile`

To initialize on startup:  
`echo '/swapfile none swap sw 0 0' | tee -a /etc/fstab`

To improve speed & swappiness:  
`nano /etc/sysctl.conf`  

Add the following at bottom of file:  
`#Swap Configuration`  
`vm.swappiness=10`  
`vm.vfs_cache_pressure=50`


#### Install OpenVPN:
---
It is recommended to add the OpenVPN-as repo to keep the packages up-to-date whenever you update.

```
apt update && apt -y install ca-certificates wget net-tools gnupg

wget -qO - https://as-repository.openvpn.net/as-repo-public.gpg | apt-key add -

echo "deb http://as-repository.openvpn.net/as/debian bionic main">/etc/apt/sources.list.d/openvpn-as-repo.list

apt update && apt -y install openvpn-as

```

#### Optional
You could also download the .deb package directly from [here](https://openvpn.net/download-open-vpn/).

The linux command to do this is:  

`wget https://openvpn.net/downloads/openvpn-as-latest-ubuntu18.amd_64.deb`  

Then install the package using:  

`dpkg -i ./openvpn-as-latest-ubuntu18.amd_64.deb`  

Follow instructions after installation to complete setup.