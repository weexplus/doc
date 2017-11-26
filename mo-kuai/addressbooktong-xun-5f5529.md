# addressBook

获取通讯录联系人信息

### API

```js
/**
 *读取联系人信息
 */
read(callback)
```

### Demo

```
read()
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



