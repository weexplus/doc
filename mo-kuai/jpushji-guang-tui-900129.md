# jpush

**首次使用请执行weexplus plugin add https://github.com/farwolf2010/jpush**

极光推送

### api

```
/**获取极光推送的设备码
getJPushId()
```
```
/**注册极光（param:{appkey:'注册极光后获得',channel:'渠道号自己随便填'}）
regist(param,callback)
```

### demo

```js
1.首先注册
var jpush=weex.requireModule('jpush')
jpush.regist({appkey:'',channel:''},(res)=>{
 if(res.err==0){
    //success
    var id=jpush.getJPushId()
 }
})



```



