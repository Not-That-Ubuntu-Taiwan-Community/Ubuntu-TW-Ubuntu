# 讓 TTY 終端機支援中文顯示與輸入
## 修改方式
1. 安裝 FbTerm（`fbterm`軟體包）、 UCIMF （`ucimf`軟體包）、FbTerm UCIMF 支援（`fbterm-ucimf` 軟體包）以及 UCIMF 新酷音輸入法支援（`ucimf-chewing` 軟體包）
1. [修正「安裝了 ucimf-chewing 但是新酷音輸入法還是叫不出來」的問題](https://github.com/Vdragon/Vubuntu/tree/master/Patches/%E8%AA%9E%E8%A8%80%E8%A8%AD%E5%AE%9A(Locale%20settings)/TTY%20%E7%B5%82%E7%AB%AF%E6%A9%9F%E4%B8%AD%E6%96%87%E6%94%AF%E6%8F%B4/%E4%BF%AE%E6%AD%A3%E3%80%8C%E5%AE%89%E8%A3%9D%E4%BA%86%20ucimf-chewing%20%E4%BD%86%E6%98%AF%E6%96%B0%E9%85%B7%E9%9F%B3%E8%BC%B8%E5%85%A5%E6%B3%95%E9%82%84%E6%98%AF%E5%8F%AB%E4%B8%8D%E5%87%BA%E4%BE%86%E3%80%8D%E7%9A%84%E5%95%8F%E9%A1%8C)
1. 以 `root` 身份執行過一次 FbTerm 之後編輯 `/root/.fbtermrc` FbTerm 設定檔，將 `font-names` key 的值設定為合適的等寬中文字型，將 `input-method` key 的值設定為 `fbterm_ucimf`
1. [讓 TTY 終端機使用 FbTerm](https://github.com/Vdragon/Vubuntu/tree/master/Patches/%E8%AA%9E%E8%A8%80%E8%A8%AD%E5%AE%9A(Locale%20settings)/TTY%20%E7%B5%82%E7%AB%AF%E6%A9%9F%E4%B8%AD%E6%96%87%E6%94%AF%E6%8F%B4/%E5%B0%87%20TTY1%20%E7%9A%84%20getty%20%E6%94%B9%E7%82%BA%20fbterm)

## 參考資料<br />Reference Data
* [Fbterm - ArchWiki](https://wiki.archlinux.org/index.php/Fbterm)
* `fbterm(1)` manpage 格式使用手冊