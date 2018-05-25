# 全量更新步骤

调用updater模块即可

```js
var updater=weex.requireModule('updater')

//整包检测
updater.doCheck({
appid:'1',
url:'http://xxxx/version.do',(这里记得改成自己的接口地址)
theme:'#808080',
failtoast:true,
showprogress:true
})
```

原理：

android 端读取的build.gradle 里面的 versionCode,来跟数据库表version version\_code进行对比，如果比他小，就认为有更新，然后弹更新提示框，所以打新包的时候，记得新包的versionCode值要增加，然后数据库也要改成最新的versionCode值， 位置如下![](/assets/WechatIMG118.jpeg)

ios端：请改途中所示的值，鼠标点击主项目-&gt;General

![](/assets/WechatIMG120.jpeg)

