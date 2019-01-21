# 微信支付
**首次使用请执行weexplus plugin add wechat**

以模块的形式提供（官方参数参考:[https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8\_5](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_5)）

### api

```
/**param参数
pay(param,callback)
```

### param 说明

```
appId = "wxd930ea5d5a258f4f";

partnerId = "1900000109";

prepayId= "1101000000140415649af9fc314aa427",;

packageValue = "Sign=WXPay";

nonceStr= "1101000000140429eb40476f8896f4c9";

timeStamp= "1398746574";

sign= "7FFECB600D7157C5AA49810D2D8F28BC2811827B";
```

### callback说明

```
type:回调类型（‘pay’,'share'）
errCode:错误码(0成功,-1错误,-2用户取消)参考：https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_5
errMsg:错误消息
transaction:未知
openId:未知
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



