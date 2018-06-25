# alipay

有支付和登录2个功能,以模块的形式提供  （加密串请参考[https://docs.open.alipay.com/204/105465/](https://docs.open.alipay.com/204/105465/)）

返回消息体请参考[https://docs.open.alipay.com/204/105301](https://docs.open.alipay.com/204/105301)

### api

```
/**param参数(signstr(加密串请在服务端加密好了传给客户端),iosscheme（ios才需要，用于支付完之后跳回本app）)
pay(param,callback)


/**param参数(scope,state)
/**callback(返回参数包含authCode，请拿此code给后台向微信服务器请求用户信息)
login(param,callback)
```



