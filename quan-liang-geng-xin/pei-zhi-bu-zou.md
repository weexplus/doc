# 全量更新步骤

调用updater模块即可

```js
var updater=weex.requireModule('updater')

//整包检测
updater.docheck({
appid:'1',
url:'',
theme:'#808080',
failtoast:true,
showprogress:true
})
```

原理：

android 端读取的build.gradle 里面的 versionCode,来跟数据库表version version\_code进行对比，如果比他小，就认为有更新，然后弹更新提示框

