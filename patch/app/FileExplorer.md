## 文件管理
APK位置： `/system/app/FileExplorer/FileExplorer.apk`

apktool命令： `apktool d -r -b *.apk`

### 移除广告
代码位置： `com/android/fileexplorer/model/ConfigHelper.smali`
```
# 搜索 Lmiui/os/Build;->IS_TABLET:Z 将其改成 Lcom/winterssy/MiuiPurify;->TRUE:Z

.method public static shouldShowStickerInCategory()Z
# return false

.method private static tryInit
# return false
```
代码位置： `com/android/fileexplorer/model/Config.smali`
```
.method public static isSystemXKVideoEnable()Z
# return false
```

### 移除想看视频的右上角三点菜单设置入口
代码路径： `com/android/fileexplorer/fragment`
```
# 关键代码： invoke-static {}, Lcom/xiangkan/XKAppConfig;->showSetting()Z
# 将该代码上方的 Lmiui/os/Build;->IS_INTERNATIONAL_BUILD:Z 改成 Lcom/winterssy/MiuiPurify;->TRUE:Z
# 使之直接跳转
```
代码位置： `com/xiangkan/XKAppConfig.smali`
```
.method public static showSetting()Z
# 搜索 Lmiui/os/Build;->IS_INTERNATIONAL_BUILD:Z 将其改成 Lcom/winterssy/MiuiPurify;->TRUE:Z
```

