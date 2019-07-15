# updater

用于更新检测，包含了整包更新和热更新。 我们提供了建议的后台程序，配合doCheck，doCheckJs 直接使用，或者自己实现更新检测然后调用download（下载安装app），hotUpdate（下载zip解压覆盖本地资源文件）

付后台地址：[https://github.com/farwolf2010/updater](https://github.com/farwolf2010/updater) java后端程序，包含了数据库脚本

## Api

```
/**
*此方法为比较业务的方法，需要结合我的后台程序来使用，你可以自己实现自己的更新检测机制，调用下方的download去下载更新即可
*param(包含：appid(app的id) url(检测更新的地址) theme(界面主题色) failtoast(失败后是否提示)  showprogress(是否显示进度) 
* installNextOpen（是否在下次打开app的时候才提示安装） )
*callback 检测到没有更新时的回调
**/
doCheck(param,callback)



/**
* url下载地址，
* android 的是apk的下载地址 （例如：http://59.110.169.226/img/app-debug.apk）
* ios是商店的地址 （例如：itms-apps://itunes.apple.com/us/app/apple-store/id375380948）
**/
download(url)


/**
*检测是否已经有下载好未安装的apk的，如果有自动弹出提示安装
*callback 不存在apk的时候调用
**/
checkDownloadApk(callback)



/**
*此方法为比较业务的方法，需要结合我的后台程序来使用，你可以自己实现自己的更新检测机制，调用下方的hotUpdate去下载更新即可
*param(包含：appid(app的id) url(检测更新的地址) theme(界面主题色) failtoast(失败后是否提示)  showprogress(是否显示进度) )
**/
doCheckJs(param)




/** 回调函数不传，就是静默更新
*param: (url:zip下载地址，注意：被压缩的文件夹名称必须是app；version:新版)
*start 开始下载
*progress 下载中，参数:(percent)整型
*compelete 下载完成
*exception 异常
**/
hotUpdate(param,start,progress,compelete,exception)
```

## Demo

```js
var updater=weex.requireModule('updater')

//整包检测
updater.doCheck({
appid:'1',
url:'',
theme:'#808080',
failtoast:true,
showprogress:true
},()=>{
   //检测到没有更新时的回调
})



//android
updater.download('http://59.110.169.226/img/app-debug.apk')

//ios
updater.download('itms-apps://itunes.apple.com/us/app/apple-store/id375380948')




//热更新检测和我们提供的后台配套
updater.doCheckJs({
appid:'1',
url:'',
theme:'#808080',
failtoast:true,
showprogress:true
})

//热更新下载 (可以自己实现更新检测的逻辑，然后调用这个)
updater.hotUpdate({urL:'http://xxxxx/app.zip',version:'当前jsversion的版本',mode:'0：静默更新，只下载存储，下次启动app的时候才覆盖本地；2:'弹出选择框提示更新，点确定立即生效''},()=>{},(percent)=>{

},()=>{

},()=>{

})
```



