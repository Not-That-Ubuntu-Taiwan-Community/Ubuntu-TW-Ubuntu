# 設定預設使用所有可用的中文介面翻譯
## 設定方式
### 透過 `gnome-language-selector`（語言支援）工具
#### 已知問題<br />Known issues
`gnome-language-selector`（語言支援）不支援廣域的語系設定

### 修改 `/etc/default/locale` 設定檔
將 `LANGUAGE ` key 的值設定為 `zh_TW:zh_HK:zh:en_US:en`

1. 預設用台灣地區的正體中文
1. 香港地區的正體中文
1. 其他的中文（含簡體中文）
1. 美國地區的英文
1. 其他的英文

## 已知問題<br />Known issues
### 設定會在 `oem-config` 時期被覆寫，所以不會套用到新使用者上

## 其他事項<br />Misc.
### 移除使用者範圍的語言設定
刪除 `〈家目錄〉/.pam_environment` 檔案即可。