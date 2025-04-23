---
title: "使用 GitHub 製作個人網站"
date: 2022-07-19T21:43:22+08:00
categories: ["網站建置"]
---

GitHub 上只能架設靜態網站，如果想要架設動態的可能要去找其他的地方，但如果只是要架靜態網站是個不錯的選擇。

## 建立帳號
要在 GitHub 上架網站當然需要一個帳號拉~ 先到 [GitHub 網站](https://github.com/)，  
還沒註冊的可以參考[這個](/posts/GitHub/Register/)

## GitHub 新增專案
再來就是點頭像，到專案去，按綠色的按紐新增  
![GitHub Your Repositories](/images/GitHub/GitHub_Your_Repositories.jpg "GitHub Your Repositories")  
或是我記得一開始一個專案都沒有時，可以從左邊那個很大的大頭貼下方直接新增。 
再來到新增畫面，填寫 Repository name ，要是 Owner 的 名稱，加上 .github.io(ex: Owner叫 abcdef，Repository name 要叫 abcdef.github.io 才行)。
![GitHub Page Repositories](/images/GitHub/GitHub_Build_Repositories.jpg "GitHub Page Repositories")  
再來按 Create repository 就完成 GitHub 的部分了  
![GitHub Page Repositories 建置](/images/GitHub/GitHub_Build_Repositories_end.jpg "GitHub Page Repositories 建置")  
## 寫個簡單的 Html
接下來，找個空的目錄，建立 index.html，內容如下：
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>GitHub Test</title>
  </head>
  <body>
    <h1>GitHub Test</h1>
  </body>
</html>
```
## Git 上去
之後我是使用 [Git Extensions](http://gitextensions.github.io/)，因為指令我常常忘記，XDDD  
不過，也是要先裝 [Git](https://git-scm.com/downloads) 的歐~  
都裝好了後
先在剛剛建好的目錄按右鍵 Create NewRepositories， 然後一直按就好啦
![Git Extensions 建新專案](/images/Git_Extensions/New_Repositories.jpg "Git Extensions 建新專案")  
再來打開剛剛建置的目錄  
![Git Extensions 打開專案](/images/Git_Extensions/Open_Repositories.jpg "Git Extensions 打開專案")  
Commit  
![Git Extensions Commit](/images/Git_Extensions/Commit.jpg "Git Extensions Commit")  
![Git Extensions Commit](/images/Git_Extensions/Commit2.jpg "Git Extensions Commit")  
最後 Push 上去
![Git Extensions Push](/images/Git_Extensions/Push.jpg "Git Extensions Push")  
Url 填 剛剛在 GitHub 建立完專案得到的一組 url 應該是長類似這樣 https:// github.com/XXX/XXX.github.io.git，  
後面會再跳出 Remote repositories， 填個喜歡的 Name ，Url 跟剛剛一樣(https:// github.com/XXX/XXX.github.io.git)  
![Git Extensions Remote Repositories](/images/Git_Extensions/Remote_Repositories.jpg "Git Extensions Remote Repositories")  
途中可能會跳出 GitHub 登入  
![Git Extensions GitHub](/images/GitHub/Git_Extension_GitHub.jpg "Git Extensions GitHub")  
登入完畢後，應該就上去 GitHub 了
剛剛 GitHub Repositories 的頁面應該也會變成   
![GitHub Repositories](/images/GitHub/GitHub_Repositories.jpg "GitHub Repositories")  
在瀏覽器輸入 https:// XXX.github.io/ 也會跑出剛剛的 html， 不過一開始可能會出現 404， 等一段時間就可以拉。  
![GitHub Page 測試](/images/GitHub/GitHub_Page_Test.jpg "GitHub Page 測試") 

參考資料:  
- [使用 GitHub 免費製作個人網站](https://gitbook.tw/chapters/github/using-github-pages)