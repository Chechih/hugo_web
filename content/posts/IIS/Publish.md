---
title: "IIS 上部屬 ASP.NET Core"
date: 2024-09-24T00:50:03+08:00
categories: ["Windows", "IIS", "NET"]
---
### 前言
本範例使用 Windows Server 2022，要安裝的 ASP.NET Core 版本使用 8，專案的話選擇 Visual Studio 2022 的 **ASP.NET Web 應用程式(Model-View-Controller)**，專案名**TestWeb**，ASP.NET 的發佈流程都可以參考這篇
### 安裝
請至[微軟官網](https://dotnet.microsoft.com/zh-tw/download/dotnet/) 下載安裝 dotnet-runtime、aspnetcore-runtime、Windows Server Hosting，版本請選擇和要發佈上去一樣的版本，比如此範例專案使用版本 8，就全都安裝版本 8 的，其中 Windows Server Hosting 測試可以向下相容，不保證未來也可以XDDD  
![微軟官網](/images/IIS/dotnet_runtime_download.jpg "dotnet_runtime_download")  
下載完成再來是安裝，依序安裝 Windows Server Hosting -> dotnet-runtime -> aspnetcore-runtime，建議用這個安裝順序，如果沒有按照此順序，可能還要再設定其他東西  
#### Windows_Server_Hosting 安裝
![Windows_Server_Hosting](/images/IIS/Windows_Server_Hosting1.jpg "Windows_Server_Hosting1")  
![Windows_Server_Hosting](/images/IIS/Windows_Server_Hosting2.jpg "Windows_Server_Hosting2")  
![Windows_Server_Hosting](/images/IIS/Windows_Server_Hosting3.jpg "Windows_Server_Hosting3")  
#### dotnet-runtime 安裝
![dotnet_runtime](/images/IIS/dotnet_runtime1.jpg "dotnet_runtime1")  
![dotnet_runtime](/images/IIS/dotnet_runtime2.jpg "dotnet_runtime2")  
![dotnet_runtime](/images/IIS/dotnet_runtime3.jpg "dotnet_runtime3")  
#### aspnetcore-runtime 安裝
![aspnetcore_runtime](/images/IIS/aspnetcore_runtime1.jpg "aspnetcore_runtime1")  
![aspnetcore_runtime](/images/IIS/aspnetcore_runtime2.jpg "aspnetcore_runtime2")  
![aspnetcore_runtime](/images/IIS/aspnetcore_runtime3.jpg "aspnetcore_runtime3")  
安裝完成後，再來選擇專案
## 建立專案
選擇 Visual Studio 2022 的 ASP.NET Web 應用程式(Model-View-Controller)
![ASP.NET_MVC](/images/IIS/ASP.NET_MVC.jpg "ASP.NET_MVC")  
名稱路徑大約填一下，反正測試用(?  
其他資訊方面最重要的就是**架構**，一定要選跟剛剛安裝的那些 .NET 套件相同，確認好可直接按*建立*，建立完成後，可以執行看看，看能不能跑  
![ASP.NET_MVC_RUN](/images/IIS/ASP.NET_MVC_RUN.jpg "ASP.NET_MVC_RUN")  
## 發佈
測試完畢後，再來開始發佈，先到專案那邊，右鍵按下**發佈**  
![ASP.NET_MVC_Publish](/images/IIS/ASP.NET_MVC_Publish1.jpg "ASP.NET_MVC_Publish")  
選擇**資料夾**那個選項  
![ASP.NET_MVC_Publish](/images/IIS/ASP.NET_MVC_Publish2.jpg "ASP.NET_MVC_Publish")  
發佈路徑可以先用預設沒關係，只是路徑要先記好，如果 IIS 和 Visual Studio 是在同一電腦，可以直接指到 IIS 路徑，如果不清楚，可以先用預設  
![ASP.NET_MVC_Publish](/images/IIS/ASP.NET_MVC_Publish3.jpg "ASP.NET_MVC_Publish")  
![ASP.NET_MVC_Publish](/images/IIS/ASP.NET_MVC_Publish4.jpg "ASP.NET_MVC_Publish")  
再來直接點擊發佈紐即可，檔案就會開始產生了~~  
![ASP.NET_MVC_Publish](/images/IIS/ASP.NET_MVC_Publish5.jpg "ASP.NET_MVC_Publish")  
## IIS 部屬
再來把剛剛產生的檔案[預設路徑-->[專案]\bin\release\net8.0\publish]，整包丟到要部屬的 IIS 電腦上，此範例放置[C:\TestWeb]
再來開啟 IIS  
![IIS_View](/images/IIS/IIS_View.jpg "IIS_View")  
點選**應用程式集區**，右鍵**新增應用程式集區**  
![Application_Cluster_Add](/images/IIS/Application_Cluster_Add.jpg "Application_Cluster_Add")  
名稱輸入能識別即可，.NET CLR 版本選擇**沒有受控碼**，然後確定  
![Application_Cluster_Add](/images/IIS/Application_Cluster_Add2.jpg "Application_Cluster_Add")  
再來選擇**站台**，右鍵**新增網站**  
![Add_Web](/images/IIS/Add_Web.jpg "Add_Web")  
站台名稱一樣輸入可識別得就好，**應用程式集區**選擇剛剛建立的，**實體路徑**選擇發佈檔案的位置[此範例是 C:\TestWeb]，連接埠輸入網站要開放的 Port，然後確定  
![Add_Web](/images/IIS/Add_Web2.jpg "Add_Web")  
測試看看，選擇 IIS 的預覽網站，選擇剛剛的 Port 就可以看到剛剛發佈的網站了!!!  
![Preview_Web](/images/IIS/Preview_Web.jpg "Preview_Web")  


### 參考
[[.NET Core] 如何在 IIS 上部屬 .NET Core](https://ithelp.ithome.com.tw/articles/10190336)  