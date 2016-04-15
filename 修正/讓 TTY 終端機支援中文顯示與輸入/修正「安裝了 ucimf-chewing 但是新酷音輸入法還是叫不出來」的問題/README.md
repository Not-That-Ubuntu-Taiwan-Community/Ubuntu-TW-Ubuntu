# 修正「安裝了 ucimf-chewing 但是新酷音輸入法還是叫不出來」的問題
## 適用範圍
* 16.04 已不再適用
* 14.04LTS

## 上游軟體缺陷報告<br />Upstream bug report
[Bug #1395509 “[PACKAGING]IMF module not installed in ucimf's sca...” : Bugs : ucimf-chewing package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/ucimf-chewing/+bug/1395509)

## 修正方式
以 root 身份建立一個 `/usr/lib/〈硬體平台名稱〉/ucimf/chewing.so` 硬連結指向 `/usr/lib/ucimf/chewing.so`

