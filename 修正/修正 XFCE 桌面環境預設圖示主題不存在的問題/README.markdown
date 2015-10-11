# 修正 XFCE 桌面環境預設圖示主題不存在的問題
目前透過 `xfce4` 軟體包安裝的 XFCE 桌面環境其預設設定之圖示主題為 `elementary-xfce-dark`，但是該軟體包的軟體依賴關係設定卻沒有依賴提供該圖示主題的 `elementary-icon-theme` 軟體包，造成大多數圖示皆無法顯示。

## 上游軟體缺陷報告<br />Upstream Bug Report
[Bug #1504822 “[PACKAGING] Missing dependency of elementary-icon-...” : Bugs : xfce4 package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/xfce4/+bug/1504822)

## 修正方式
安裝 `elementary-icon-theme` 軟體包。