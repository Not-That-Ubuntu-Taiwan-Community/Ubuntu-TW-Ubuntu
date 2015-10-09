# 預設將硬體時鐘時間視為本地時間，避免 Ubuntu 與 Microsoft Windows 雙系統時對硬體時鐘的解讀產生差異
## 修正方法
以 `root` 身份編輯 `/etc/default/rcS` 設定檔，將 `#UTC=yes` 列替換為 `UTC=no`
