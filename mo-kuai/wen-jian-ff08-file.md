# file

文件操作

## api

```
/**
*path 解压路径
*callback 回调函数（参数：path（数组））
**/
unzip(path,callback)


/**
*path 解压路径
*callback 回调函数
**/
ls(path,callback)
```

## demo

```
var net =weex.requireModule('net')
var file =weex.requireModule('file')
var url='http://xxxxx/img/xxx.zip'
net.download(url,(percent)=>{
    this.percent=percent;
},(e)=>{
    this.percent=e.path
    file.unzip(e.path,(res)=>{
         this.url=res.path[0]
    })
},()=>{

})
```



