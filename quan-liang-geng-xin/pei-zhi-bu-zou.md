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



