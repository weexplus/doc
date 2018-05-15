# env

环境模块

### api {#api}

```
//获得app版本号（整数）
versionCode()



//获取版本名入1.1，1.2
versionName()



//读取src/config.json中的jsVersion值
jsVersionCode()
```

### demo {#demo}

```
var env=weex.requireModule('env')

var nativeVersionCode=env.versionCode();

var nativeVersionName=env.versionName();

var jsersionCode=env.jsVersionCode();
```



