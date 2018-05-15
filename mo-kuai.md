# location

定位，使用系统自带的定位

### api {#api}

```
/*
* param (once:是否只定位一次)
*/
start(param,callback)
```

## demo {#demo}

```js
 var location=weex.requireModule('location')
 location.start({once:true},(res)=>{
     var modal=weex.requireModule('modal')
     modal.alert({message:res})
  })
```



