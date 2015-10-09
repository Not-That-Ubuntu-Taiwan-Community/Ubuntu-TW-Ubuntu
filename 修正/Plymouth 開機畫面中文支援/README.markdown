# Plymouth 開機畫面中文支援
由於初始化時期檔案系統(initramfs)中並沒有包含中文字型，Plymouth 開機畫面無法正常地顯示中文

## 上游軟體缺陷報告<br />Upstream bug report
[Bug #1339954 “Unable to display Chinese in Plymouth labels” : Bugs : plymouth package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/plymouth/+bug/1339954)

## 修正方式
1. 以 `root` 身份建立 `/etc/initramfs-tools/hooks/plymouth_cjk_support` 檔案，加入以下內容（以另外安裝的 Adobe 思源黑體為例）：
```sh
#!/bin/sh
# Vubuntu patch: CJK render support
PREREQ="plymouth"

prereqs()
{
echo "$PREREQ"
}

case $1 in
prereqs)
prereqs
exit 0
;;
esac

. /usr/share/initramfs-tools/hook-functions

mkdir -p "${DESTDIR}/usr/local/share/fonts/opentype/Adobe Source Han Sans"
cp "/usr/local/share/fonts/opentype/Adobe Source Han Sans/SourceHanSansTW-Normal.otf" "${DESTDIR}/usr/local/share/fonts/opentype/Adobe Source Han Sans"
```
2. 以 root 身份執行 `update-initramfs -k all -uv` 命令重新建立初始化時期 RAM 檔案系統(initramfs)。


