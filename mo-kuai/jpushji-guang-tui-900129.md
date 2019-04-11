# jpush

**首次使用请执行weexplus plugin add jpush**

极光推送

### api

```
/**获取极光推送的设备码
getJPushId()
```
```
/**注册极光（param:appkey,channel）
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



