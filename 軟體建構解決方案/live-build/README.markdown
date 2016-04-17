# live-build
本軟體建構解決方案使用 Debian 的 live-build 工具搭配 Ubuntu 的 livecd-rootfs 來建構 Live 安裝媒體映像檔。

這也是 Ubuntu 官方目前在用的作法。

## 本軟體建構解決方案所依賴的軟體
* live-build
* livecd-rootfs
* syslinux-utils
	* 用於 `isohybrid` 命令
* ubuntu-cdimage（來源碼參考用）
* launchpad-buildd（來源碼參考用）
	* 據說是現在在用的[1]

### 參考資料
[1] [2.376 : livecd-rootfs package : Ubuntu](https://launchpad.net/ubuntu/+source/livecd-rootfs/2.376)

```
  [ Steve Langasek ]
  * Drop BuildLiveCD from the examples; we now use launchpad-buildd to drive
    livefs builds, so BuildLiveCD is obsolete and misleading.
```

## 建構步驟
### 1. 將本目錄 bind mount 到安全路徑的目錄上（若必要）
由於 live-build 程式對含空白字元的路徑的有缺陷，故可能需要暫時先將本目錄 bind mount 到安全的目錄上：

```
# mount --bind 〈本目錄路徑〉 〈安全目錄路徑：如 ~使用者名稱/Workarounds/Safepath〉
# cd ~使用者名稱/Workarounds/Safepath
```

### 1. （若先前有執行過的話）以 root 身份執行 `lb clean` 清除過去建構產物

### 1. 執行 `env PROJECT=ubuntu ARCH=amd64 SUITE=trusty BINARYFORMAT=iso-hybrid MIRROR=http://free.nchc.org.tw/ubuntu lb config` 產生設定檔

### 1. 編輯 `config/bootstrap` 設定檔，設定 `LB_MIRROR_BINARY="http://free.nchc.org.tw/ubuntu/"`

### 1. 編輯 `config/binary` 設定檔，設定 `LB_SYSLINUX_THEME="ubuntu-trusty"`

### 1. 以 root 身份執行 `env PROJECT=ubuntu ARCH=amd64 lb build` 開始建構 Live 安裝媒體
* 為什麼在 launchpad-buildd 中需要再次設定 PROJECT、ARCH？

### 1. 由於 syslinux bootloader 被設定使用錯誤的 Linux 作業系統核心跟 initramfs 映像檔路徑，我們要手動修正它
#### a. 以 root 身份編輯 `binary/isolinux/txt.cfg`，將 vmlinuz 跟 initrd.lz 替換為正確的名稱
#### a. 移除 `lb binary iso` 的 stage file `.build/binary_iso`
#### a. 重新以 root 身份執行 `lb binary`

## 已知問題
### 預設 live-build 使用 11.10 版本 Ubuntu 的 Syslinux 主題
LB_SYSLINUX_THEME="ubuntu-trusty"

### 預設不支援 UEFI 開機模式...？
沒看到 Grub EFI bootloader 的檔案

### 預設安裝兩版本 Linux 作業系統核心
```
update-initramfs: Generating /boot/initrd.img-3.13.0-85-generic
cryptsetup: WARNING: could not determine root device from /etc/fstab
update-initramfs: Generating /boot/initrd.img-3.13.0-24-generic
cryptsetup: WARNING: could not determine root device from /etc/fstab
```

### Syslinux 預設 kernel 路徑跟 initramfs 路徑錯誤
Syslinux 預期 `/casper/vmlinuz` 跟 `/casper/initrd.lz`，但是實際上裝上去的卻不是同樣的路徑

### 安裝完成之系統缺少 Linux 作業系統核心
...該不會是被移出去 casper 了吧

發現被 config/binary_rootfs/exclude 排除掉了，原因待查

### LB_MIRROR_BINARY="http://free.nchc.org.tw/ubuntu/" 無效

### P: Begin installing disk information...(lb_binary_disk)因 lzcat： : 無效的檔案名稱字尾 錯誤出錯
[Bug #1555980 “broke on binary stage by wrong on lzcat” : Bugs : live-build package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/live-build/+bug/1555980)
