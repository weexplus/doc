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

demo

```
var file=weex.requireModule('file')
var net =weex.requireModule('net')
var file =weex.requireModule('file')
var url='http://59.110.169.246/img/1.zip'
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



