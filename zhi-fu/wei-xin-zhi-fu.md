# 微信支付

以模块的形式提供（官方参数参考:[https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8\_5](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_5)）

### api

```
/**param参数
open(param,callback)
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
errCode:错误码
errMsg:错误消息
m.put("err",resp.errCode);
m.put("msg",resp.errStr);
m.put("transaction",resp.transaction);
m.put("openId",resp.openId);
        
```



