## framework.jar
JAR位置： `/system/framework/framework.jar`

### 初始化 `miui-purify`

`miui-purify` 为简化操作，引入了 `MiuiPurify` 核心类（位于 `patch/smali` 目录下），你必须将其写入到 `framework.jar` 中的相应位置。

```
.
└── smali
    ├── android
    └── com
        ├── android
        └── winterssy
            └── MiuiPurify.smali
```

### 优化文字选择菜单搜索按钮的点击行为

代码位置： `android/widget/Editor$ActionPopupWindow.smali`
```
.method public onClick(Landroid/view/View;)V
# 关键代码：android.intent.action.WEB_SEARCH
# 将其上方的 Lmiui/os/Build;->IS_INTERNATIONAL_BUILD:Z 修改为 Lcom/winterssy/MiuiPurify;->TRUE:Z
# 如果你删除了MIUI搜索APP，必须执行此修改，否则点击会FC
```
