# 暫時修正 XFCE 桌面環境下無法切換使用者的問題
## 適用範圍
Ubuntu <14.10

## 上游軟體問題報告
### Ubuntu
[Bug #1320560 “Removal of gdmflexiserver breaks user switching” : Bugs : xfswitch-plugin package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/xfswitch-plugin/+bug/1320560)

### XFCE
[Bug 11786 – "Switch User" via 'xflock4'](https://bugzilla.xfce.org/show_bug.cgi?id=11786)

## 暫時排解問題方式<br />Workaround
1. 以 root 身份將 [gdmflexiserver](gdmflexiserver) 複製到 `/usr/local/bin` 目錄下
1. 如果需要立即生效的話，執行 `xfce4-panel --restart` 命令重新啟動 XFCE 面板

### 感謝<br />Credits
[Anton Asche](https://launchpad.net/~aasche) 於 [Bug #1320560 “Removal of gdmflexiserver breaks user switching” : Bugs : xfswitch-plugin package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/xfswitch-plugin/+bug/1320560/comments/4) 提供的 workaround。
