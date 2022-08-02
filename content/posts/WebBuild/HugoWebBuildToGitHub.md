---
title: "Hugo 建置到 GitHub Page"
date: 2022-08-01T20:05:01+08:00
categories: ["網站建置"]
---
這裡會介紹建置好的 Hugo 網站，Push 到 GitHub Page 上
## 產生靜態檔案
先移到 Hugo 的資料夾(hugo new site myweb 產生的資料夾)，
```powershell
cd myweb
```
執行
```powershell
hugo
```
就會看到 Hugo 資料夾裡面的 public 資料夾裡面產生了檔案
![public 資料夾](/images/Hugo/publicFolder.jpg "public 資料夾")  
將這些檔案 Push 到 XXX.github.io 上面去就可以了  
如果 XXX.github.io 還沒建置，可以參考[使用 GitHub 製作個人網站](/posts/WebBuild/GitHub-Page-Build/)，將檔案中的 index.html 那些全部換掉就可以了

實作時參考:  
[在 GitHub 部署 Hugo 靜態網站](https://medium.com/@chswei/%E5%9C%A8-github-%E9%83%A8%E7%BD%B2-hugo-%E9%9D%9C%E6%85%8B%E7%B6%B2%E7%AB%99-9c40682dfe40) 