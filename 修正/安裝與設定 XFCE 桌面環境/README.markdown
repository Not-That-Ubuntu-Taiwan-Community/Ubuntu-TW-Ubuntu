# 安裝與設定 XFCE 桌面環境
## 修正方式
### 安裝 XFCE 桌面環境
以 `root` 身份安裝 `xfce4` 軟體包

### 安裝 XFCE 相關軟體
以 `root` 身份安裝 `xfce4-goodies` 軟體包

### 安裝 XFCE 面板 Application Indicator 支援
以 `root` 身份安裝  `xfce4-indicator-plugin`

#### 設定（限佈署用使用者）
##### 透過圖形介面
1. 預設面板上點右鍵選擇「面板→面板偏好設定(E)」。
1. 於「項目(M)」頁面中點選「加入新項目至此面板」按鈕，加入「指示器插件」項目。
1. 選取「指示器插件」項目點選「編輯目前所選的項目」，將「Keyboard」、「Session Management」、「Application Menus (Global Menu)」、「Date and Time」指示器隱藏。
1. 執行 `xfce4-panel --restart` 命令重新啟動面板讓設定生效。

##### 修改設定檔
* `$HOME/.config/xfce4/xfconf/xfce-perchannel-xml/xfce4-panel.xml`

```
--- default.xml	2014-02-20 15:14:46.000000000 +0800
+++ default.xml.patched	2015-10-10 06:00:50.586326999 +0800
@@ -17,6 +17,7 @@
         <value type="int" value="4"/>
         <value type="int" value="5"/>
         <value type="int" value="6"/>
+        <value type="int" value="99"/>
         <value type="int" value="2"/>
       </property>
     </property>
@@ -70,5 +71,13 @@
     </property>
     <property name="plugin-13" type="string" value="separator"/>
     <property name="plugin-14" type="string" value="directorymenu"/>
+    <property name="plugin-99" type="string" value="indicator">
+      <property name="blacklist" type="array">
+        <value type="string" value="com.canonical.indicator.keyboard"/>
+        <value type="string" value="com.canonical.indicator.session"/>
+        <value type="string" value="com.canonical.indicator.datetime"/>
+        <value type="string" value="libappmenu.so"/>
+      </property>
+    </property>
   </property>
 </channel>
```
 
#### 設定（系統全域）
1. 以 `root` 身份將 [_etc_xdg_xfce4_panel_default.xml.patch](_etc_xdg_xfce4_panel_default.xml.patch) 修正套用到 `/etc/xdg/xfce4/panel/default.xml` 檔案。
1. 為了避免 XFCE 面板詢問新建立使用者要不要使用預設面板以 root 身份將 `/etc/xdg/xfce4/panel/default.xml` 複製到 `/etc/skel/.config/xfce4/xfconf/xfce-perchannel-xml/` 目錄下。
