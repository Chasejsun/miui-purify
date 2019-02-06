## 短信
APK位置： `/system/priv-app/Mms/Mms.apk`

apktool命令： `apktool d -r -b *.apk`

### 移除广告
代码位置： `com/android/mms/util/SmartMessageUtils.smali`
```
.method public static disableAD()Z
# return true

.method public static allowMenuMode
# return false
```
