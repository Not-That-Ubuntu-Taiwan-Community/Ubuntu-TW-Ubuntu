# 將 TTY1 的 getty 改為 fbterm
## 修正方式
1. `# stop tty1`
2. 以 root 身份編輯 /etc/init/tty1.override 設定檔，加上  
exec rungetty -u root tty1 -- fbterm -- login
3. `# start tty1`

## 已知問題
### [無法正常啟動 ucimf 輸入法](https://github.com/Vdragon/Vubuntu/tree/master/Patches/%E8%AA%9E%E8%A8%80%E8%A8%AD%E5%AE%9A(Locale%20settings)/TTY%20%E7%B5%82%E7%AB%AF%E6%A9%9F%E4%B8%AD%E6%96%87%E6%94%AF%E6%8F%B4/%E4%BF%AE%E6%AD%A3%E3%80%8C%E5%AE%89%E8%A3%9D%E4%BA%86%20ucimf-chewing%20%E4%BD%86%E6%98%AF%E6%96%B0%E9%85%B7%E9%9F%B3%E8%BC%B8%E5%85%A5%E6%B3%95%E9%82%84%E6%98%AF%E5%8F%AB%E4%B8%8D%E5%87%BA%E4%BE%86%E3%80%8D%E7%9A%84%E5%95%8F%E9%A1%8C)
這是 ucimf 的軟體缺陷，ucimf 於 HOME 環境變數未設定的情況下會程式崩潰，上游新版本中已經修正本問題

#### 暫時解決方案<br />Workarounds
於 exec 後加上「env HOME=/root」即可
