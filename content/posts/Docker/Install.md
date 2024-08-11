---
title: "Docker 安裝 By Ubuntu"
date: 2024-08-12T01:02:01+08:00
categories: ["Docker", "Ubuntu"]
---
### 安裝
在 Ubuntu 中安裝 Docker 使用 docker.io 會比較快速，能省去許多麻煩。  
1. 打開終端機，輸入  
```shell
sudo apt-get install docker.io -y
```
![Install Docker](/images/Docker/Install.jpg "Install Docker")  
2. 檢查 Docker 是否正常啟動
```shell
service docker status
```
![Docker Status](/images/Docker/Docker_Status.jpg "Docker Status")  
3. 將自己加入 docker 群組，這樣之後下指令就不需要再加 sudo
```shell
sudo usermod -a -G docker $(whoami)
```
4. 重開機，也可以登出再登入
```shell
reboot
```
這樣就可以開始使用 Docker 了

### 參考
[Ubuntu Linux 安裝 Docker 步驟與使用教學](https://blog.gtwang.org/virtualization/ubuntu-linux-install-docker-tutorial/)  
[在 Ubuntu 上安裝 Docker](https://how.wtf/installing-docker-on-ubuntu.html)  