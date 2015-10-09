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

 ```xml
<?xml version="1.0" encoding="UTF-8"?>

<channel name="xfce4-panel" version="1.0">
  <property name="configver" type="int" value="2"/>
  <property name="panels" type="array">
    <value type="int" value="1"/>
    <value type="int" value="2"/>
    <property name="panel-1" type="empty">
      <property name="position" type="string" value="p=6;x=0;y=0"/>
      <property name="length" type="uint" value="100"/>
      <property name="position-locked" type="bool" value="true"/>
      <property name="size" type="uint" value="30"/>
      <property name="plugin-ids" type="array">
        <value type="int" value="1"/>
        <value type="int" value="3"/>
        <value type="int" value="15"/>
        <value type="int" value="4"/>
        <value type="int" value="5"/>
        <value type="int" value="6"/>
        <value type="int" value="16"/>
        <value type="int" value="2"/>
      </property>
    </property>
    <property name="panel-2" type="empty">
      <property name="position" type="string" value="p=10;x=0;y=0"/>
      <property name="position-locked" type="bool" value="true"/>
      <property name="plugin-ids" type="array">
        <value type="int" value="7"/>
        <value type="int" value="8"/>
        <value type="int" value="9"/>
        <value type="int" value="10"/>
        <value type="int" value="11"/>
        <value type="int" value="12"/>
        <value type="int" value="13"/>
        <value type="int" value="14"/>
      </property>
    </property>
  </property>
  <property name="plugins" type="empty">
    <property name="plugin-1" type="string" value="applicationsmenu"/>
    <property name="plugin-2" type="string" value="actions"/>
    <property name="plugin-3" type="string" value="tasklist"/>
    <property name="plugin-15" type="string" value="separator">
      <property name="expand" type="bool" value="true"/>
      <property name="style" type="uint" value="0"/>
    </property>
    <property name="plugin-4" type="string" value="pager"/>
    <property name="plugin-5" type="string" value="clock"/>
    <property name="plugin-6" type="string" value="systray">
      <property name="names-visible" type="array">
        <value type="string" value="hime"/>
        <value type="string" value="networkmanager 面板程式"/>
      </property>
    </property>
    <property name="plugin-7" type="string" value="showdesktop"/>
    <property name="plugin-8" type="string" value="separator">
      <property name="style" type="uint" value="1"/>
    </property>
    <property name="plugin-9" type="string" value="launcher">
      <property name="items" type="array">
        <value type="string" value="14439940321.desktop"/>
      </property>
    </property>
    <property name="plugin-10" type="string" value="launcher">
      <property name="items" type="array">
        <value type="string" value="14439940322.desktop"/>
      </property>
    </property>
    <property name="plugin-11" type="string" value="launcher">
      <property name="items" type="array">
        <value type="string" value="14439940323.desktop"/>
      </property>
    </property>
    <property name="plugin-12" type="string" value="launcher">
      <property name="items" type="array">
        <value type="string" value="14439940324.desktop"/>
      </property>
    </property>
    <property name="plugin-13" type="string" value="separator">
      <property name="style" type="uint" value="1"/>
    </property>
    <property name="plugin-14" type="string" value="directorymenu">
      <property name="base-directory" type="string" value="/home/oem"/>
    </property>
    <property name="plugin-16" type="string" value="indicator">
      <property name="known-indicators" type="array">
        <value type="string" value="libapplication.so"/>
        <value type="string" value="libprintersmenu.so"/>
        <value type="string" value="libappmenu.so"/>
        <value type="string" value="com.canonical.indicator.datetime"/>
        <value type="string" value="com.canonical.indicator.keyboard"/>
        <value type="string" value="com.canonical.indicator.power"/>
        <value type="string" value="com.canonical.indicator.messages"/>
        <value type="string" value="com.canonical.indicator.session"/>
        <value type="string" value="com.canonical.indicator.bluetooth"/>
        <value type="string" value="com.canonical.indicator.sound"/>
      </property>
      <property name="blacklist" type="array">
        <value type="string" value="com.canonical.indicator.keyboard"/>
        <value type="string" value="com.canonical.indicator.session"/>
        <value type="string" value="com.canonical.indicator.datetime"/>
        <value type="string" value="libappmenu.so"/>
      </property>
    </property>
  </property>
</channel>

 ```