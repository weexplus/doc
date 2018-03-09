# oss

# Api

```
 /**
     * @param url 文件地址(native端的)
     * @param param 服务器请求参数
     * @param progress 上传进度
     * @param compelete 上传结束(成功:err=0;失败:err=1)
     */
upload( url,param,progress,compelete)
```

## Demo

```js
//以图片上传为例
openAll()
{


    var self=this;
    const photo = weex.requireModule('photo');
    photo.open(500,800,'#000000','#ffffff','#ffffff',function(e){
   
          var oss=weex.requireModule('oss');
          var param={}
          param
          oss.upload(e.path,param,(process)=>{
          },(res)=>{
          })
     
    });


}
```



