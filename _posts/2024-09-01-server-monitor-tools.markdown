---
layout: post
title:  "Installing and Accessing Cockpit, Uptime Kuma, and Netdata"
date:   2024-08-31 21:09:04 -0300
permalink: /server-monitoring-tools.html
---

## Introduction
In the digital age, the health of your servers is as crucial as the functionality of the applications they host. Monitoring these servers can prevent downtime, optimize performance, and predict resource needs. Today, we'll cover how to install and access three essential monitoring tools: **Cockpit**, **Uptime Kuma**, and **Netdata**. Each offers unique insights into your systems and can be accessed securely from your local machine.

## Installing the Tools

### Cockpit Installation
Cockpit is integrated into many Linux distributions, making its installation straightforward:

#### For Ubuntu:
```
sudo apt install cockpit
```

Access Cockpit at `http://localhost:9090/` after tunneling.

### Uptime Kuma Installation

```
docker run -d --name uptime-kuma -p 3001:3001 louislam/uptime-kuma
```

Access Uptime Kuma at `http://localhost:3001/` after tunneling.