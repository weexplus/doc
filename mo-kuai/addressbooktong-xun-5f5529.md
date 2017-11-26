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

```js
read()
{
  var book=weex.requireModule('addressBook')

  book.read((res)=>{
      var people=res.people;
      var p0=people[0];
      var firstname=p0.firstName
      var lastName=p0.lastName
      var phones=p0.phones 
       
  })
}
```



