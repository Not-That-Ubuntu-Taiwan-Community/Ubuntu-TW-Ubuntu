# 安裝符合台灣筆劃規範的字型
## 修改方式
1. 安裝字型
	1. 以 `root` 身份安裝 `fonts-cns11643-kai`、`fonts-cns11643-sung`、<del>`fonts-noto-cjk`（來自 backports 區域）</del>軟體包。
	1. 於 [Releases · adobe-fonts/source-han-sans](https://github.com/adobe-fonts/source-han-sans/releases) 下載新字型釋出版本並解壓縮封存檔。
	1. 以 root 身份將 `〈封存檔根目錄〉/source-han-sans-〈版本號〉R/SubsetOTF/TW/` 目錄底下的檔案安裝到 `/usr/local/share/fonts/opentype/Adobe Source Han Sans/`
1. 以 `root` 身份於終端機下執行 `fc-cache --system-only --verbose` 命令更新 fontconfig 快取資料。