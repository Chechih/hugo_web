---
title: "Hugo 建置"
date: 2022-07-30T21:20:33+08:00
categories: ["網站建置"]
---
雖然架 GitHub 網站時，我有發現有 Jekyll ,Hexo, Hugo，不過 Jekyll 裝完發現太舊，Hexo, Hugo 選了好久，發現用 Hugo 的人比較多，而且 Hugo 如果文章多，建置似乎比較快，就選他了XDDDD  
  
這會介紹基本 Hugo 建置，因為我是用 Windows 版的，我只介紹 Windows 版的安裝方法
## 安裝套件管理器 Chocolatey
先到開始右鍵，選擇 Windows PowerShell(系統管理員)  
![Windows PowerShell](/images/Hugo/Windows_PowerShell.jpg "Windows PowerShell")  
執行下方指令  
  
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol =[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
若沒有錯誤，在執行 choco 
```powershell
> choco
Chocolatey v1.1.0
Please run 'choco -?' or 'choco <command> -?' for help menu.
```
如果出現版本資訊就可以了。
## 安裝 Hugo
之後的流程可以在 Windows PowerShell 或是 命令提示字元 執行
```powershell
choco install hugo -confirm
```
如果沒有錯誤，恭喜你 Hugo 安裝完成了!!!
## Hugo 架網站
先把位子移到一個資料夾裡面
```powershell
cd XXXXX
```
在執行
```powershell
hugo new site myweb
```
後面 myweb 是會在資料夾裡面再建一個 myweb 的資料夾，裡面包含基本的 Hugo 檔案
再來執行，進入資料夾中
```powershell
cd myweb
```
最後執行
```powershell
hugo server
```
讓 Hugo 網站起來，在瀏覽器輸入 [http://localhost:1313/](http://localhost:1313/) 輸入後如果是一片白，代表成功拉!!!
之後就可以選擇風格 
## 選擇風格 
到 [Hugo Theme](https://jamstackthemes.dev/ssg/hugo/) 網站裡面選擇一個喜歡的風格，假設你選到一個風格叫 [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) 選他的 GitHub 把他的檔案下載下來，
![Ananke GitHub](/images/Hugo/AnankeGitHub.jpg "Ananke GitHub")  
解壓縮到一個資料夾裡面，並把他命名成 Ananke (這名稱可以制定，指示之後會用到記得就好)，資料夾內容如下  
![Ananke 資料夾](/images/Hugo/AnankeFolder.jpg "Ananke 資料夾")  
之後把這個資料夾剪下，貼到剛剛 hugo new site myweb 產生的資料夾裡面的 themes 資料夾裡面  
![HugoThemes](/images/Hugo/HugoThemes.jpg "HugoThemes")  
再到 myweb\themes\Ananke\exampleSite 資料夾裡的 config.toml 剪下，這是範例的 config
![Hugo exampleSite](/images/Hugo/AnankeExe.jpg "Ananke exampleSite")  
貼到 myweb 資料夾裡面覆蓋上去  
![myweb 資料夾](/images/Hugo/myweb.jpg "myweb 資料夾")  
之後用記事本打開剛剛貼上去的 config.toml  ， 將裡面的 theme = ["github.com/theNewDynamic/gohugo-theme-ananke"] 修改成 theme = "Ananke"，這是要把風格修改成找資料夾裡面的  
![myweb Config](/images/Hugo/AnankeConfigOre.jpg "myweb Config")  
![myweb Config](/images/Hugo/AnankeConfigEd.jpg "myweb Config")  
最後一樣執行  
```powershell
cd myweb
hugo server
```
出現選定的風格就可以了  
![Ananke](/images/Hugo/AnankeWeb.jpg "Ananke")  
## 修改風格
這裡開始需要用到一些 HTML 技巧  
執行後如果想修改風格的 html 檔案，其實只要找到他的 html 檔案位子，一般在 themes/XXX， XXX 是對應的風格，舉個例子來說，你想改 themes\Ananke\layouts 裡面的 index.html 你不用直接改他，你可以到 myweb (剛剛 hugo new site myweb 路徑)的資料夾底下，找到 layouts 資料夾，裡面加上 index.html 的檔案，這樣 Hugo 就會自動把那個黨按取代掉了，執行完就是要的結果~~
![Ananke Layouts Index](/images/Hugo/AnankeLayoutsIndex.jpg "Ananke Layouts Index")  
![myweb Layouts](/images/Hugo/mywebLayouts.jpg "myweb Layouts")  
![myweb Layouts Test](/images/Hugo/mywebLayoutsTest.jpg "myweb Layouts Test")  
![Ananke Test](/images/Hugo/AnankeTest.jpg "Ananke Test")  
這樣至少不會直接改到原檔案，後面改壞了還有救XDDDD  
不過修改時，要小心，裡面會有 Go 的語法在裡面，像剛剛改  
![myweb Layouts Test](/images/Hugo/mywebLayoutsTest2.jpg "myweb Layouts Test")  
要改在 define "main" 裡面，是因為這是一個 Ananke 切的區塊，如果整個蓋掉，那應該看不到效果，被坑過(X)  
參考資料:  
[網站開張！在 GitHub Pages 架設 Hugo 靜態網站](https://www.zoeydc.com/zh/posts/2021-05-23-hugo-website_github-pages_custom-domain/)  
實作時參考:  
- [Hugo 主题 Even 的自定义配置](https://blog.dontjudge.cn/post/hugo-%E4%B8%BB%E9%A2%98-even-%E7%9A%84%E8%87%AA%E5%AE%9A%E4%B9%89%E9%85%8D%E7%BD%AE/)  
- [iT邦幫忙-Louissu](https://ithelp.ithome.com.tw/users/20142010/ironman/4917)  
- [iT邦幫忙-littlebookboy](https://ithelp.ithome.com.tw/users/20106430/ironman/3613)  
- [Hugo debugging](https://gohugo.io/templates/template-debugging/)  
- [如何创建自己的hugo主题](https://www.jianshu.com/p/0b9aecff290c?u_atoken=a09bd15b-2942-41ed-a27b-585048916162&u_asession=01ibeTyrO0b-6soyY1ZVMVGetyXOcp72Z3tXvLUl7J27MwyRyOO7wcvKk1rOcT6qCPX0KNBwm7Lovlpxjd_P_q4JsKWYrT3W_NKPr8w6oU7K8rUuPXhSrGGE4IwwVDMLj1Ppcarp92QKzyJKyYjREPlmBkFo3NEHBv0PZUm6pbxQU&u_asig=05Q8crcoTkvttMf0fF8w8Fcc2y4y4tT8lYu_jNa7kiriMJPjFLc6Rsfk9yqcYP2seQLvl3F4DoBp_7wYs2eYi6rc7qNOA6xS6-C85Fu3qMSg1insEUE569p-b7Kn9z_Z0hKAroHTU-RaOUotdHF_ZIgyPPdXkooD-2X5soVadGhaT9JS7q8ZD7Xtz2Ly-b0kmuyAKRFSVJkkdwVUnyHAIJzR6W9xF9UQazkic-9JULeE1aaz5yacafDrtqp8_tndodWPRPQyB_SKrj-61LB_f61u3h9VXwMyh6PgyDIVSG1W-qGsCDEK9a3JgjBJp_mk7CS0gA-YCVD9qXtlq4leRItEc80rs_RyY2cZX2NhtSF7Gg1wJ3Vtk1_ug0vJ12v-qsmWspDxyAEEo4kbsryBKb9Q&u_aref=CspdvuBywZCBZszC%2F5e83W%2FYa8s%3D)   
- [Hugo 的文件管理 - 資料夾結構](https://jimmylin212.github.io/post/0002_hugo_content_management_dir_structure/)  
- [Hugo 加入 Disqus 整合性留言管理系統](https://coreychen71.github.io/posts/2019-05/hugoadddisqus/)  