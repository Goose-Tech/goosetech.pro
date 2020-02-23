---
title: "Need More RAM for your MasterNode?  Create a Swap File for your Linux VPS!"
image: images/videos/133.jpg
date: 2018-10-26T12:00:00-05:00
draft: false
type: "videos"
author: Goose-Tech
tags: ["crypto", "linux", "vultr", "swap", "masternode", "tutorial"]
---

#### VIDEO

{{< youtube BOxqXOFwx6o >}}

&nbsp;

#### DESCRIPTION

In this video I show how to create a swap file for an Ubuntu Server v16.04 Virtual Private Server to add more efficiency and available RAM space for running multiple MasterNodes. This can be done for new or existing setups.

📘Table of Contents:  
◆ 00:08 Intro  
◆ 01:00 Vultr VPS Options  
◆ 04:03 Updating Linux  
◆ 04:36 Swap File Setup  
◆ 14:41 Final Thoughts  
●▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬●  
⭐Links:  
💻Vultr VPS Hosting Service: https://goo.gl/pU7ph3  
💻Swap Guide Article: https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04  
●▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬●  

⌨Commands:  
(Run as root)

Show active swap:  
`swapon --show`  
Show free space:  
`free -h`  
Check available HDD space:  
`df -h`  

Create swap:  
`fallocate -l 3G /swapfile`  
Modify permissions:  
`chmod 600 /swapfile`  
Make swap:  
`mkswap /swapfile`  
Enable swap:  
`swapon /swapfile`  

To initialize on startup:  
`echo '/swapfile none swap sw 0 0' | tee -a /etc/fstab`  

To improve speed & swappiness open sysctl.conf:  
`/# nano /etc/sysctl.conf`  

Then add the following to the bottom of file:  
`#Swap Configuration`  
`vm.swappiness=10`  
`vm.vfs_cache_pressure=50`
