# 安裝並設定 HIME 輸入法框架為預設輸入法
## 安裝 HIME 輸入法框架
### 當 GNU/Linux 作業系統散佈版本提供的 HIME 沒問題時
安裝下列軟體包：

* hime
* hime-anthy
* hime-chewing
* hime-*-immodule

### 當 GNU/Linux 作業系統散佈版本提供的 HIME 有問題時
1. 安裝 Git（`git-core` 軟體包）、`devscripts`、`equivs` 軟體包。
1. 以 `root` 身份於終端機中於 `/usr/local/src` 目錄執行 `git clone https://github.com/hime-ime/hime.git` 命令複刻(fork) HIME 的軟體來源代碼庫。
1. 以 `root` 身份編輯 `/usr/local/src/hime` 目錄下的 `distro/debian/control` 檔案，將 `Build-Depends` 行的 `dpkg | libqt4-dev | libqt3-mt-dev | libanthy-dev | libchewing3-dev | libappindicator-dev | libappindicator3-dev | qtbase5-private-dev` 段替換為
 ` | libqt3-mt-dev, libqt4-dev, qtbase5-private-dev, libappindicator-dev, libappindicator3-dev, libanthy-dev, libchewing3-dev`，將 `libgtk2.0-dev` 與 `libgtk-3-dev` 之間的 ` | ` 改為
 `, `。
 1. 以 `root` 身份於終端機中於 `/usr/local/src/hime` 目錄下
執行 `mk-build-deps ./distro/debian/control` 命令建構用於安裝[建構 HIME 需要用到的軟體](https://github.com/hime-ime/hime/wiki/Software-dependencies-for-building-HIME)的 `hime-build-deps` 軟體包， 建構完了之後用 Ubuntu 軟體中心或 Gdebi 軟體包安裝程式安裝該軟體包。
1. 以 `root` 身份於終端機中於 `/usr/local/src/hime` 目錄下執行 `./configure` 確認需要用到的選用項目皆已啟用，範例輸出如下：  
```
prefix: /usr/local
.... Testing Xtst               :  Found.
.... Testing gtk+-2.0           :  Found.
.... Testing anthy              :  Found.
.... Testing chewing            :  Found.
.... Testing appindicator       :  Found.
.... Testing Qt 3.x             :  Not found, Qt 3.x immodule is turned off.
.... Testing Qt 4.x             :  Found.
.... Testing Qt 5.x             :  Found.
.... Path of Qt4 moc            :  /usr/lib/i386-linux-gnu/qt4/bin/moc
.... Path of Qt5 moc            :  /usr/lib/i386-linux-gnu/qt5/bin/moc
.... Testing GTK+ 2.x immodule  :  Found.
.... Testing GTK+ 3.x immodule  :  Found.
-> CFLAGS = .
```
1. 以 `root` 身份於終端機中於 `/usr/local/src/hime` 目錄下執行 `./distro/debian/gen-deb` 建構 HIME 的軟體包，軟體包會建立在 `/usr/local/src` 目錄下。
1. 安裝 HIME  軟體包

## 設定 HIME 輸入法框架為系統預設輸入法
以 `root` 身份執行 `im-config` 