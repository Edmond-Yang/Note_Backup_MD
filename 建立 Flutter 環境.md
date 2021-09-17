# 建立 Flutter 環境



## Step 1. 安裝 [Git](https://git-scm.com/)

* **點選上方網址，選擇 Download for Windows 並安裝完成**
![](https://i.imgur.com/MjCbrfX.png)

## Step 2. 下載 [Flutter](https://flutter.dev/)

* **點選上方網址，選擇 Get Started**
![](https://i.imgur.com/auGaqLb.png)

* **往下滑看到灰色方框**
![](https://i.imgur.com/W8S94AV.png)

* **在C槽裡建立 src 資料夾**
![](https://i.imgur.com/LkGWuqf.png)

* **搜尋 cmd 並打開命令提示字元**
![](https://i.imgur.com/bieMQlL.png)

* **連續兩次輸入 cd.. 再輸入 cd src**
![](https://i.imgur.com/SzMUf3Q.png)

* **點選灰框中複製按鈕 並貼在 cmd 上，按 Enter 執行**
![](https://i.imgur.com/LtP3cPh.png)

* **下載完成**
![](https://i.imgur.com/2v22pzF.png)

## Step 3. 設定環境變數
* **搜尋 環境變數 並打開**
![](https://i.imgur.com/BHtVZAv.png)

* **選擇 環境變數**
![](https://i.imgur.com/FgHCvCS.png)

* **選擇 Path**
![](https://i.imgur.com/64AspuN.png)

* **按新增 輸入 C:\src\flutter\bin 並一直按確定**
![](https://i.imgur.com/zuZUc2k.png)

## Step 4. 檢查 flutter

* **打開下載好的 flutter 資料夾 ( 在 src 資料夾裡 )**
![](https://i.imgur.com/xJWC8tN.png)

* **打開 flutter_console**
![](https://i.imgur.com/QGRtrOf.png)

* **輸入 flutter doctor ( 下載並檢查問題 )**
  發現未安裝 Android Studio
  
  ![](https://i.imgur.com/VfTVQHj.png)

## Step 5. 下載並設定 [Android Studio](https://developer.android.com/studio?gclid=Cj0KCQjw-NaJBhDsARIsAAja6dMRG_DruHlpn9u83Ip1FfVIRa0doPmqo97UL6JlCrLJSb2_vq5ttbIaArotEALw_wcB&gclsrc=aw.ds)

* **選擇 Download Android Studio 並安裝**
![](https://i.imgur.com/RRevM3G.png)

* **打開 Android Studio 並選擇 More Actions**
![](https://i.imgur.com/47CLJqU.png)

* **選擇 SDK Manager**
![](https://i.imgur.com/aUUhbF5.png)

* **選擇打勾 Android 11.0 ( 我需要的版本，大家可以自行下載所需版本 ) **
![](https://i.imgur.com/HcM7ZKy.png)

* **按下 SDK Tools ( SDK Platforms 旁 ) 並選擇打勾 Android SDK Command-line Tools**
![](https://i.imgur.com/TlI7iak.png)

* **按下 OK 等待下載 ( 或需要重開 Android Studio ) 並回到原本初始畫面**
![](https://i.imgur.com/0tW6Vrl.png)

* **同樣選擇 More Actions 並點 AVD Manager**
![](https://i.imgur.com/T1dL4Lu.png)

* **選擇 Create Visual Device...**
![](https://i.imgur.com/PLCDyRE.png)

* **選擇 Pixel XL 並選擇 Android 11.0 ( 按照個人喜好選擇，手機安卓系統會要求安裝 )**
![](https://i.imgur.com/JiItQmo.png)

* **將 Graphics 的 Automatic 改成 Hardware 並完成**
  這樣就完成模擬器設定囉
  
  ![](https://i.imgur.com/hJc76fG.png)

* 注意 : 安裝[HAXM](https://github.com/intel/haxm/releases/tag/v7.6.6) ( 如若出現尚未安裝時，所需要執行的步驟 )
  
  * 重新開機且按住 F2 或是 Delete 來進入 BIOS
  ![](http://kmpic.asus.com/images/2020/07/21/2633fec8-a75a-412b-a517-7354d6fbe689.jpg)
  
  * 按下F7進入 Advanced Mode
  ![](http://kmpic.asus.com/images/2020/07/21/e932a0ec-544b-4c30-91f1-b94773482dd1.jpg)
  
  * 按 Advanced 並點 CPU Configuration
  ![](http://kmpic.asus.com/images/2020/07/21/46e2e0d3-97ff-40f5-9744-8b9defbffc71.jpg)
  
  * 往下滑看到 Intel Visualization Technology 並將 Disabled 改成 Enabled
  ![](http://kmpic.asus.com/images/2020/07/21/f8cc2412-337d-46ec-88d0-9a4c19f0a32a.jpg)
  
  * 按 F7 回原本畫面並按 Save & Exit
  ![](http://kmpic.asus.com/images/2020/07/21/2633fec8-a75a-412b-a517-7354d6fbe689.jpg)
  
  * 點選上方 HAXM 並往下滑 選擇 haxm-windows_v7_6_6.zip ，解壓縮後並安裝完成
  ![](https://i.imgur.com/uFslyHC.jpg)



## Step 6. 設定並確認 flutter 沒有問題
* **開啟 Android Studio 並點選 Plugins ( 左側第三個 )**
![](https://i.imgur.com/ebrvOgc.jpg)

* **搜尋 Flutter 並安裝**
![](https://i.imgur.com/zqftYMi.jpg)

* **搜尋 Dart 並安裝**
![](https://i.imgur.com/J7BDsBB.jpg)

* **回到 flutter console 並輸入 flutter doctor**
  * 如若發現問題 : Android Studio ( not install ) ， 請輸入 : 
  ``` 
  flutter config --android-studio-dir="C:\Program Files\Android\Android Studio"    
  ```
  * 如若只剩如下圖的問題 ， 則下一步會解開
  ![](https://i.imgur.com/Ip39mr4.jpg)
   
* **輸入下方灰框後，並一直同意 ( 輸入 y )，最後再輸入 flutter doctor 確認無任何問題**
  ```
  flutter doctor --android-licenses
  ```
  ![](https://i.imgur.com/fT1DFV7.jpg)



## 建立第一個 Flutter Project
* **點選 New Flutter Project**
![](https://i.imgur.com/uzVgUHe.jpg)

* **點選 Flutter 並在上方輸入下方灰框內容後，點選 Next**
  ```
  C:\src\flutter
  ```
  ![](https://i.imgur.com/0O51pFP.jpg)

* **輸入喜歡的檔名，並按 Finish**
![](https://i.imgur.com/U0XWwYb.jpg)

* **在右上方 <no devices selected> 點選 refresh 後，點選剛剛所建立的模擬器**
![](https://i.imgur.com/6gyM3RN.png)

* **開始第一個 Flutter Project**
![](https://i.imgur.com/sqKxqvl.png)

