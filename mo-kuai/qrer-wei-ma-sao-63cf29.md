# qr

二维码扫描组件

# API

```js
/**
  * 存储对象
  * @param param 设置二维码扫描界面的参数
  * @param callback 回调函数
  */
open( param,  callback)
```

### Demo

```js
open()
{
  var qr=weex.requireModule('qr')
  var p={};
  p.color='#000000'
  p.bgcolor='#ffffff'
  qr.open(p,(res)=>{
    var url=res.url
  })
}
```



