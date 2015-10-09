# 台灣社群非官方客製版 Ubuntu 作業系統<br />Taiwan Community Customized Unofficial Ubuntu Operating System
<https://github.com/Vdragon/Ubuntu-TW-Ubuntu>

## 內容大綱<br />Table of Contents
如果這裡只看得到 [TOC] 的話代表這個閱讀器不支援 Markdown 的「內容大綱」擴充功能。

[TOC]

## 本專案的智慧財產授權條款<br />Intellectual Property License of This Project
除了另外聲明之內容以外，本作品之內容採用「Creative Commons **<span class="important_warning" style="color: red">姓名標示</span>**-**<span class="important_warning" style="color: red">相同方式分享</span>**第 3.0 版或其任意更近期版本」授權條款釋出供所有人在授權條款限制範圍內使用。  
![「創用 CC-BY-SA 3.0 台灣地區版本或其後版本」授權條款圖示](https://cdn.rawgit.com/Vdragon/Vdragon_s_License_Templates/217eea4d6e13a5f72eddf1f1a3b22dbdee9e9639/Creative%20Commons/CC%20BY-SA/Resources/Creative%20Commons%20CC-BY-SA%20logo.svg)

於下列條件的**<span class="important_warning" style="color: red">限制</span>**下您可以自由使用本作品之內容於任何用途：

* 姓名標示  
  **<span class="important_warning" style="color: red">BY</span>** as known as Attribution
	* 您必須**以本作品指定的方式**明確地標註本作品創作者的名稱「Ｖ字龍 &lt;<Vdragon.Taiwan@gmail.com>&gt;」於本作品之任何衍伸作品中（且不得以任何方式暗示本作品為您或您使用本作品的方式背書）。
* 相同方式分享  
  **<span class="important_warning" style="color: red">S</span>**hared **<span class="important_warning" style="color: red">A</span>**like
	* 本作品之衍伸作品必須以本作品採用之授權條款釋出
* 您必須明確標註衍伸作品中屬於本作品之內容所採用的授權條款。

如您不確定您的使用方式是否違反授權條款，敬請參閱：

* Creative Commons — 姓名標示-相同方式分享 3.0 台灣 — CC BY-SA 3.0  
  <http://creativecommons.org/licenses/by-sa/3.0/tw/>

本作品同時仍於「合理使用(fair use)」之有限範圍下使用其他資源，將於可行範圍內另外註明其著作權擁有者(copyright holder)與其授權條款，如需了解如何使用該類資源敬請參閱：

* 合理使用 - 維基百科，自由的百科全書  
  <http://zh.wikipedia.org/wiki/合理使用>
  
如果有任何需求，敬請不吝來信洽詢

* 國立台灣海洋大學網路發展協會　Ｖ字龍  
  &lt;<Vdragon.Taiwan@gmail.com>&gt;

感謝您的配合，並祝您使用愉快！

## 特色<br />Features
### 預設使用正體中文語系與輸入法
* 同時安裝了簡體中文與香港語系，增加介面在地化的程度

![同時安裝了簡體中文與香港語系，增加介面在地化的程度](資源/特色%20-%20同時安裝了簡體中文與香港語系，增加介面在地化的程度.png)

* 預設使用 [HIME 輸入法框架](http://hime-ime.github.io/)（同時安裝了 ibus 新酷音輸入法作為選用項目）
* 預設安裝了中文 manpage 說明文件

![預設安裝了中文 manpage 說明文件](資源/特色%20-%20預設安裝了中文%20manpage%20說明文件.png)

### 預設支援中文顯示與輸入的 TTY 終端機
![預設支援中文顯示與輸入的 TTY 終端機](資源/特色%20-%20預設支援中文顯示與輸入的%20TTY%20終端機.png)

* 藉由 fbterm 與 ucimf 專案的幫助支援了預設支援中文顯示與輸入的 TTY 終端機

### 預設安裝了符合台灣筆劃規範的 [Adobe 思源黑體](https://github.com/adobe-fonts/source-han-sans)與台灣行政院研考會 CNS11643 字型

### 預設支援中文訊息顯示的 Plymouth 開機畫面！
菱形什麼的還是去死吧。

![預設支援中文訊息顯示的 Plymouth 開機畫面！](資源/特色%20-%20預設支援中文訊息顯示的%20Plymouth%20開機畫面！.png)

### 預設將硬體時鐘時間視為本地時間，避免 Ubuntu 與 Microsoft Windows 雙系統時對硬體時鐘的解讀產生差異
重新啟動到 Microsoft Windows 時系統時間不會再少 8 小時

### 預設採用[國家實驗研究院國家高速網路與計算中心自由軟體實驗室](http://free.nchc.org.tw/) 20 Gbps 的高速軟體來源鏡像站
更短的軟體與更新下載時間

![](資源/特色%20-%20預設採用國家實驗研究院國家高速網路與計算中心自由軟體實驗室%2020%20Gbps%20的高速軟體來源鏡像站.png)

### 預設安裝了 Unity 與 XFCE 桌面環境
同時滿足高階跟低階硬體的需求，不需要 OpenGL 繪圖支援也可以順暢運行

![預設安裝了 Unity 與 XFCE 桌面環境](資源/特色%20-%20預設安裝了%20Unity%20與%20XFCE%20桌面環境.png)

### 預設安裝了 VirtualBox 與 VMware 虛擬機器客端作業系統支援軟體
* 只要主端系統有足夠的 OpenGL 繪圖能力 Unity 桌面環境就不再卡卡
* 畫面大小自動適應虛擬機器視窗大小，不再屈就於小畫面！
* 主客端系統剪貼簿同步！

### 預設安裝了 SSH 伺服器與 Fail2ban

### 預設套用了一些還沒收入 Ubuntu 中的修正
* 修正以 root 身份執行的程式無法使用中文輸入法的問題([Ubuntu Bug #1373521](https://bugs.launchpad.net/ubuntu/+source/sudo/+bug/1373521))
* 修正以 sudo 執行的命令預設會保留呼叫者的 HOME 環境變數的問題([Ubuntu Bug #1373495](https://bugs.launchpad.net/ubuntu/+source/sudo/+bug/1373495))
* 修正錯誤的 `/etc/adduser.conf` `NAME_REGEX` 預設值([Ubuntu Bug #1387825](https://bugs.launchpad.net/ubuntu/+source/adduser/+bug/1387825), [Debian Bug #630750](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=630750))
* 修正「安裝了 ucimf-chewing 但是新酷音輸入法還是叫不出來」的問題([Ubuntu Bug #1395509](https://bugs.launchpad.net/ubuntu/+source/sudo/+bug/1395509))

## 獲取軟體<br />Acquire software
軟體下載連結位於本專案的[釋出頁面](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/releases)

## 進行本軟體的開發需要的軟體<br />Dependencies for Development of This Software
### Ubuntu GNU/Linux 作業系統散佈版本
### 一個虛擬機器軟體，比方說 Oracle VirtualBox

## 本目錄下的檔案與目錄說明<br />Description of files and directories under this directory
### [專案說明文件.markdown<br />README.markdown](README.markdown)
本說明文件  
This documentation

## 如何對本專案做出貢獻<br />How to Contribute to This Project
### 回報問題與改善建議<br />Report Issues and Improvement Suggestions
發現問題或是有改善本專案的建議的話請到[本專案的議題追蹤系統(issue tracker)](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/issues)建檔回報。  
File report at [this project's issue tracker](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/issues) if you noticed some problem or have improvement suggestions.

### 貢獻本專案內容<br />Contribute Contents to This Project
要貢獻內容的話歡迎[建立您的分支版本倉庫](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/fork)，建立並切換至一個新的 Git 分支(branch)完成編輯後提交(commit)為一個新版本，推送(push)到您的 GitHub 遠端版本倉庫再跟我們[建檔拉取請求(pull request)](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/pull/new)。  
[Create your fork repository](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/fork), create and switch to a new Git branch, do your edits and commit as a new version, push them to your remote repository on GitHub and [file us a pull request](https://github.com/Vdragon/Ubuntu-TW-Ubuntu/pull/new)!

### 宣傳本專案給別人<br />Promote!
將本專案宣傳出去，讓更多人知道有這個專案！  
Promote this project so that more people recognize it!

### 翻譯本專案內容並進行在地化<br />Translate and Do Localization!
如果您熟悉其他語言，歡迎將本專案之內容翻譯為不同的語言  
If you are familiar to other languages, it is welcomed to translate this project's content to other languages.

### 更多……？<br />More...?
[向我們詢問](../../issues)更多可以貢獻的方式！    
[Ask us](../../issues) more ways you can contribute!
