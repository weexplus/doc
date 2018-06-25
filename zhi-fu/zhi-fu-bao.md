# 支付宝支付

以模块的形式提供  （加密串请参考[https://docs.open.alipay.com/204/105465/](https://docs.open.alipay.com/204/105465/)）

返回消息体请参考[https://docs.open.alipay.com/204/105301](https://docs.open.alipay.com/204/105301)

## api

```
/**signstr 加密串，由服务端提供，具体请参考 https://docs.open.alipay.com/204/105465/
/**callack(res) (res)返回结构体请参考 https://docs.open.alipay.com/204/105301
open(sinstr,callback)
```

### demo

```
var pay=weex.requireModule('alipay')
var p={}
p.signstr=signstr

pay.open(p,(res)=>{


})
```



