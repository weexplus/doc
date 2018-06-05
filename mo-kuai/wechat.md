# wechat\(微信\)

有支付和登录2个功能，请务必在首页调用regist方法，初始化微信

### api

```
(请务必在首页调用此方法，初始化微信)
/**appId
regist(appId)



/**param参数(appId,partnerId,prepayId,packageValue,nonceStr,timeStamp,sign)
pay(param,callback)


/**param参数(scope,state)
/**callback(返回参数包含authCode，请拿此code给后台向微信服务器请求用户信息)
login(param,callback)
```

### demo

```
var pay=weex.requireModule('wechat')
var p={}
p.appId = "wxd930ea5d5a258f4f";
p.partnerId = "1900000109";
p.prepayId= "1101000000140415649af9fc314aa427",;
p.packageValue = "Sign=WXPay";
p.nonceStr= "1101000000140429eb40476f8896f4c9";
p.timeStamp= "1398746574";
p.sign= "7FFECB600D7157C5AA49810D2D8F28BC2811827B";
pay.open(p,(res)=>{

     if(res.errCode==0)
     {
        //suucess
     }
})




```



