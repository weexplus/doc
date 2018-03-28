# updater

用于更新检测，其实是一个业务方法，你可以直接下载我的建议后台检测，或者自己实现然后调用暴露了下载app安装的方法

## Api

```
/**
*此方法为比较业务的方法，需要结合我的后台程序来使用，你可以自己实现自己的更新检测机制，调用下方的download去下载更新即可
*param(包含：appid(app的id) url(检测更新的地址) theme(界面主题色) failtoast(失败后是否提示)  showprogress(是否显示进度) )
**/
docheck(param)

/**
* url下载地址，
* android 的是apk的下载地址 （例如：http://59.110.169.226/img/app-debug.apk）
* ios是商店的地址 （例如：itms-apps://itunes.apple.com/us/app/apple-store/id375380948）
**/
download(url)
```

## Demo

```js
var updater=weex.requireModule('updater')
updater.docheck({
appid:'1',
url:'',
theme:'#808080',
failtoast:true,
showprogress:true
})

//android
updater.download('http://59.110.169.226/img/app-debug.apk')

//ios
updater.download('http://59.110.169.226/img/app-debug.apk')
```



