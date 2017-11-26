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
  var book=weex.requireModule('addressBook')

  book.read((res)=>{
    var url=res.url
  })
}
```



