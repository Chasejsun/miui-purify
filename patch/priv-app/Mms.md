## 短信
APK位置： `/system/priv-app/Mms/Mms.apk`

apktool命令： `apktool d -r -b *.apk`

### 移除广告
代码位置： `com/android/mms/util/SmartMessageUtils.smali`
```
.method public static disableAD()Z
# return true
```

### 移除底部菜单

APK位置： `/system/app/SmsExtra/SmsExtra.apk`

apktool命令： `apktool d -r -b *.apk`

代码位置： `com/miui/smsextra/ui/BottomMenu.smali`
```
.method public static allowMenuMode
# return false
```

