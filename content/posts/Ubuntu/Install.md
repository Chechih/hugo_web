---
title: "在 VirtualBox 中安裝 Ubuntu"
date: 2024-07-20T17:23:23+08:00
categories: ["VirtualBox", "Ubuntu"]
---
### 前置準備
- 前往 [VirtualBox 官網](<https://www.virtualbox.org/>) 下載 EXE 安裝，下載完成安裝起來
- 前往 [Ubuntu 官網](<https://ubuntu.com/download/desktop/>) 下載印象檔
  - 此範例使用 24.04 LTS 版本
### 開始安裝
Step1: 開啟安裝好的 VirtualBox  
![VirtualBox Start Screen](/images/VirtualBox/Start_Screen.jpg "VirtualBox Start Screen")  
Step2: 點選右上角的新增按鈕  
![VirtualBox Insert](/images/VirtualBox/Insert.jpg "VirtualBox Insert")  
Step3: 輸入參數，以下是說明  
a. 名稱: 打 Ubuntu 即可，這是之後用來是別虛機的名稱  
b. 資料夾: 是建立起的虛機檔案存放路徑，如果沒有特別需要預設即可  
c. 印象檔: 使用*剛剛 Ubuntu 下載下來的 ISO 檔案*  
d. 略個無人職守安裝: 有點像之後自動幫你安裝到系統起來，不過他要填的訊息也比較多，先勾起來，用一般安裝  
![VirtualBox Ubuntu Parameter1](/images/VirtualBox/Ubuntu_Parameter1.jpg "VirtualBox Ubuntu Parameter1")  
Step4: 設定記憶體和 CPU 大小，一需求設定  
![VirtualBox Ubuntu Parameter2](/images/VirtualBox/Ubuntu_Parameter2.jpg "VirtualBox Ubuntu Parameter2")  
Step5: 設定虛擬硬碟，這個有點像系統要跑在多大的硬碟上  
選項 1. 建立一個，但就算你輸入 100G 也不會直接吃掉你硬碟的 100G，除非你勾選的**預設配置完整大小**  
選項 2. 指的是使用已建立好的  
選項 3. 先不處理，之後也可以到**設定**那邊處理  
建議如果第一次用的話，先選擇 1.  
![VirtualBox Ubuntu Parameter3](/images/VirtualBox/Ubuntu_Parameter3.jpg "VirtualBox Ubuntu Parameter3")  
Strp6: 確認剛剛輸入的值，沒問題直接按**完成**  
![VirtualBox Ubuntu Confirm](/images/VirtualBox/Ubuntu_Confirm.jpg "VirtualBox Ubuntu Confirm")  
![VirtualBox Ubuntu Init](/images/VirtualBox/Ubuntu_Init.jpg "VirtualBox Ubuntu Init")  
Step7: 先別急著啟動，先進行初始設定，點選剛剛建立的虛機，再按**設定**  
![VirtualBox Ubuntu Setting1](/images/VirtualBox/Ubuntu_Setting1.jpg "VirtualBox Ubuntu Setting1")  
點選**一般**>**進階**將共用剪貼簿和拖拉設定成雙向，這能讓之後複製和拖拉更方便。  
![VirtualBox Ubuntu Setting2](/images/VirtualBox/Ubuntu_Setting2.jpg "VirtualBox Ubuntu Setting2")  
點選**儲存裝置**>**控制器**，勾選固態硬碟  
![VirtualBox Ubuntu Setting3](/images/VirtualBox/Ubuntu_Setting3.jpg "VirtualBox Ubuntu Setting3")  
點選**網路**增加新的網卡2，**僅限主機**，顧名思義就是宿主能連近來而已，網卡2，選擇橋接介面卡，這能把虛機放到內網裡，其他電腦能 Ping 的到  
![VirtualBox Ubuntu Setting4](/images/VirtualBox/Ubuntu_Setting4.jpg "VirtualBox Ubuntu Setting4")  
![VirtualBox Ubuntu Setting5](/images/VirtualBox/Ubuntu_Setting5.jpg "VirtualBox Ubuntu Setting5")  
備註: 共用資料夾，就是讓宿主和虛機能共用的資料夾，之後有需要再設定即可  
沒問題先按**確定**  
Step8: 啟動  
![VirtualBox Ubuntu Run](/images/VirtualBox/Ubuntu_Run.jpg "VirtualBox Ubuntu Run")  
Step9: 安裝 Ubuntu，選擇第一項  
![VirtualBox Ubuntu Install1](/images/VirtualBox/Ubuntu_Install1.jpg "VirtualBox Ubuntu Install1")    
![VirtualBox Ubuntu Install2](/images/VirtualBox/Ubuntu_Install2.jpg "VirtualBox Ubuntu Install2")   
選擇語系  
![VirtualBox Ubuntu Install3](/images/VirtualBox/Ubuntu_Install3.jpg "VirtualBox Ubuntu Install3")  
無障礙功能  
![VirtualBox Ubuntu Install4](/images/VirtualBox/Ubuntu_Install4.jpg "VirtualBox Ubuntu Install4")  
鍵盤配置  
![VirtualBox Ubuntu Install5](/images/VirtualBox/Ubuntu_Install5.jpg "VirtualBox Ubuntu Install5")  
網路配置  
![VirtualBox Ubuntu Install6](/images/VirtualBox/Ubuntu_Install6.jpg "VirtualBox Ubuntu Install6")  
檢查 Ubuntu 更新，這裡可以略過，安裝完後再更新 
![VirtualBox Ubuntu Install7](/images/VirtualBox/Ubuntu_Install7.jpg "VirtualBox Ubuntu Install7")  
選擇**安裝 Ubuntu**
![VirtualBox Ubuntu Install8](/images/VirtualBox/Ubuntu_Install8.jpg "VirtualBox Ubuntu Install8")  
選擇**互動是安裝**
![VirtualBox Ubuntu Install9](/images/VirtualBox/Ubuntu_Install9.jpg "VirtualBox Ubuntu Install9")  
是否按裝推薦軟體，依需求安裝  
![VirtualBox Ubuntu Install10](/images/VirtualBox/Ubuntu_Install10.jpg "VirtualBox Ubuntu Install10")  
硬碟是否要切割?基本上預設即可  
![VirtualBox Ubuntu Install11](/images/VirtualBox/Ubuntu_Install11.jpg "VirtualBox Ubuntu Install11")  
設定帳密  
![VirtualBox Ubuntu Install12](/images/VirtualBox/Ubuntu_Install12.jpg "VirtualBox Ubuntu Install12")  
設定時區，系統會自己抓  
![VirtualBox Ubuntu Install13](/images/VirtualBox/Ubuntu_Install13.jpg "VirtualBox Ubuntu Install13")  
確認剛剛的設定  
![VirtualBox Ubuntu Install14](/images/VirtualBox/Ubuntu_Install14.jpg "VirtualBox Ubuntu Install14")  
安裝 Ubuntu 中  
![VirtualBox Ubuntu Install15](/images/VirtualBox/Ubuntu_Install15.jpg "VirtualBox Ubuntu Install15")  
等待一下就安裝完畢
![VirtualBox Ubuntu](/images/VirtualBox/Ubuntu.jpg "VirtualBox Ubuntu")  
### 共享設置
Step 1: 插入 Guest Additions CD  
![Insert Guest Additions CD](/images/VirtualBox/Insert_Guest_Additions_CD.jpg "Insert Guest Additions CD")  
Step 2: 打開終端機  
![Install Guest Additions CD1](/images/VirtualBox/Install_Guest_Additions_CD1.jpg "Install Guest Additions CD1")  
Step 3: 安裝 Guest Additions CD，輸入
```shell
sudo ./VBoxLinuxAdditions.run
```
![Install Guest Additions CD2](/images/VirtualBox/Install_Guest_Additions_CD2.jpg "Install Guest Additions CD2")  
Step 4: 發現他還要安裝 bzip2，那先安裝起來  
```shell
sudo apt-get install bzip2
```
![Install Guest Additions CD3](/images/VirtualBox/Install_Guest_Additions_CD3.jpg "Install Guest Additions CD3")  
Step 5: 安裝完後再是一次，這次應該可以順利安裝了  
```shell
sudo ./VBoxLinuxAdditions.run
```
![Install Guest Additions CD4](/images/VirtualBox/Install_Guest_Additions_CD4.jpg "Install Guest Additions CD4")  
Step 6: 重新開機，開完機應該可以發現，視窗可以依比例伸縮
```shell
reboot
```
Step 7: 設定共用剪貼簿和共用資料夾，如果前面有設定這裡可以跳過，共用資料夾一樣需要再來設定也可以  
![Public Scrapbook](/images/VirtualBox/Public_Scrapbook.jpg "Public Scrapbook")  
### 共用資料夾
設定
![Public Folder1](/images/VirtualBox/Public_Folder1.jpg "Public Folder1")  
設定完成後，會發現 **/media** 底下，多了剛剛設定的資料夾，這是可以和宿主戶通的資料夾

### 一般套件安裝和更新
- 更新
```shell
sudo apt-get update
sudo apt-get upgrade 
```
- 安裝 vim
```shell
sudo apt-get install -y vim 
```
- 安裝 openssh server
```shell
sudo apt-get install -y openssh-server 
```
- 安裝 net tools
```shell
sudo apt-get install net-tools 
```

### 參考
- [【 VM 】如何在 Oracle VirtualBox 中安裝 Ubuntu](https://learningsky.io/install-ubuntu-on-oracle-virtualbox/)  
- [[Linux] VirtualBox Ubuntu 22.04 安裝與設定 Part.2 Guest Additions與共享設置篇](https://medium.com/@zeroro247/linux-virtualbox-ubuntu-22-04-%E5%AE%89%E8%A3%9D%E8%88%87%E8%A8%AD%E5%AE%9A-part-2-guest-additions%E8%88%87%E5%85%B1%E4%BA%AB%E8%A8%AD%E7%BD%AE%E7%AF%87-6138e71e9ba)  
- [APT method bzip2 doesn't exist](https://askubuntu.com/questions/692223/apt-method-bzip2-doesnt-exist)  

