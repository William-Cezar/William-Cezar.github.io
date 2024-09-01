---
layout: post
title:  "Installing and Accessing Cockpit, Uptime Kuma, and Netdata"
date:   2024-08-31 21:09:04 -0300
permalink: /server-monitoring-tools.html
---

## Introduction
In this post, we'll cover how to install and access three essential monitoring tools: **Cockpit**, **Uptime Kuma**, and **Netdata**. Each offers unique insights into your systems and can be accessed securely from your local machine.

## Installing the Tools

### Cockpit Installation

Cockpit is a powerful, web-based interface that allows users to manage Linux servers with ease. Designed to be easy to use, even for those new to server management, Cockpit makes it possible to perform complex server tasks directly from a browser without needing extensive command-line interactions.

#### Key Features:
- **System Overview**: Provides a dashboard that gives you a quick overview of your server's status and health, including CPU, memory usage, and disk performance.
- **Service Management**: Allows you to start, stop, restart, and check the status of system services. This is crucial for managing the components that your applications rely on.
- **User Management**: Offers tools to add, remove, and manage user accounts, ensuring only authorized users have access to your system.
- **Logs**: Displays logs from the system and services, which are essential for troubleshooting issues and ensuring everything is running smoothly.
- **Terminal Access**: Includes a web-based terminal where you can directly execute commands, offering the convenience of command-line access without needing to use SSH.
- **Software Updates**: Facilitates the installation of software updates directly from the interface, helping keep your system secure.

#### Installing Cockpit on Ubuntu:
Cockpit comes pre-installed on some Linux distributions, but if it’s not included by default, you can install it easily on Ubuntu with the following command:
```
sudo apt install cockpit
```
After installation, Cockpit can be accessed via a web browser at http://localhost:9090/. However, to securely access Cockpit over the internet or from a non-local network, it's recommended to set up an SSH tunnel. This approach encrypts the traffic between your local machine and the server, enhancing security.

#### Setting Up SSH Tunneling for Cockpit:
To access Cockpit securely, use the following command to create an SSH tunnel from your local machine to the server:
```
ssh -L 9090:localhost:9090 your-username@your-server-ip
```


### Uptime Kuma Installation

```
docker run -d --name uptime-kuma -p 3001:3001 louislam/uptime-kuma
```

Access Uptime Kuma at `http://localhost:3001/` after tunneling.