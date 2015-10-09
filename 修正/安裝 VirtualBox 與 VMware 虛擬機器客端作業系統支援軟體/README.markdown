# 安裝 VirtualBox 與 VMware 虛擬機器客端作業系統支援軟體
## 修正方式
以 `root` 身份安裝 `virtualbox-guest-dkms` 跟 `open-vm-tools` 軟體包。

## VirtualBox：如果要立刻啟用支援
1. 於終端機內以 `root` 身份執行 `service virtualbox-guest-utils start` 與 `service virtualbox-guest-x11`。
1. 登出使用者帳號。
1. 切換到 TTY 終端機登入。
1. 以 `root` 身份執行 `restart 〈X Display Manager 服務名稱〉` 重新啟動 X Display Manager。
