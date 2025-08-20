---
draft: true
date: 
  created: 2025-08-18
  updated: 2025-08-18
authors:
  - mnye
categories:
  - SIEM
  - Tutorials
tags:
  - SIEM
  - Tutorials
---

# Installing a Splunk Lab Environment

Update Ubuntu

``` bash
sudo apt update && sudo apt upgrade
```

Install dependencies

``` bash
sudo apt install -y curl wget
```

Sign up for Splunk Enterprise free trial and download installer

``` bash
wget -O splunk-10.0.0-e8eb0c4654f8-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/10.0.0/linux/splunk-10.0.0-e8eb0c4654f8-linux-amd64.deb"
```

Install Splunk

``` bash
sudo dpkg -i splunk-10.0.0-e8eb0c4654f8-linux-amd64.deb
```

Start Splunk

``` bash
sudo /opt/splunk/bin/splunk start - accept-license - answer-yes
```

Setup admin username and password when prompted

Enable Splunk to start at boot

``` bash
sudo /opt/splunk/bin/splunk enable boot-start
```