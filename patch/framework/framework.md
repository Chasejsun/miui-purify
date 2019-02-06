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

