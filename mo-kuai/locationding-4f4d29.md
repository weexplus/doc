# location

系统定位模块

### api

```
/**
/*param(once:是否只定位一次(true,false))
start(param,callback)
```

### demo

```
 var location=weex.requireModule('location')
 var modal=weex.requireModule('modal')

 location.start({once:false},(res)=>{
modal.alert({message:res})
 })
```



