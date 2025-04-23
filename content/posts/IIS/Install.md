---
title: "開啟 IIS By Windows Server 2022"
date: 2024-09-04T23:48:22+08:00
categories: ["IIS", "Windows", "網站建置"]
---
### 安裝
1. 開啟**伺服器管理員**  
![Server Administrator](/images/IIS/Server_Administrator.jpg "Server_Administrator")  
2. 選擇**新增角色及功能**
3. 會跳出**新增角色及功能精靈**，直接點選**下一步**
![New Role And Function Elves](/images/IIS/New_Role_And_Function_Elves.jpg "New_Role_And_Function_Elves")  
4. 安裝類型選擇**角色型或功能型安裝**
![Installation Type](/images/IIS/Installation_Type.jpg "Installation_Type")  
5. 目的地伺服器選擇**從伺服器集區選取伺服器**
![Destination Server](/images/IIS/Destination_Server.jpg "Destination_Server")  
6. 角色勾選**網頁伺服器(IIS)**
![Role IIS](/images/IIS/Role_IIS.jpg "Role_IIS")  
7. 邊檢查 .NET Framework 4.x 功能是否有勾選，基本上系統會幫你勾選
![NET Framework4X](/images/IIS/NET_Framework4X.jpg "NET_Framework4X")  
8. 網頁伺服器角色這邊，按**下一步**
![Web Server Role](/images/IIS/Web_Server_Role.jpg "Web_Server_Role")  
9. 角色服務這邊，可以直接**下一步**，之後都可以再回來勾選
![Role Service](/images/IIS/Role_Service.jpg "Role_Service")  
10.  確認安裝，按**安裝**
![Check Install](/images/IIS/Check_Install.jpg "RCheck_Install")  
11.  等待安裝  
![Start Installation](/images/IIS/Start_Installation.jpg "Start_Installation")  
備註: 如果是一般 Windows，會在**控制台-->程式集-->程式及功能-->開啟或關閉 Windows 功能**找到 IIS  
![Windows Function](/images/IIS/Windows_Function.jpg "Windows_Function")  
### 確認安裝
開起瀏覽器，輸入**localhost**，出現下圖即可
![IIS Localhost](/images/IIS/IIS_Localhost.jpg "IIS_Localhost")  

### IIS 介面
搜尋輸入**IIS**，點擊  
![IIS Icon](/images/IIS/IIS_Icon.jpg "IIS_Icon")  
![IIS Interface](/images/IIS/IIS_Interface.jpg "IIS_Interface")  


### 參考
- [Windows Server 2019 如何安裝IIS 運行ASP.NET 專案](https://blog.hungwin.com.tw/windows-server-iis-install/)