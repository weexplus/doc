# oss

# Api

```
 /**
     * @param url 文件地址(native端的)
     * @param params 包含参数(url,param,objectkey)
     * @param progress 上传进度
     * @param compelete 上传结束(成功:err=0;失败:err=1)
     */
upload( params,progress,compelete)
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
          var param={}//从你们后台获取，需要和阿里对接
          param.Endpoint=''
          param.AccessKeyId=''
          param.AccessKeySecret=''
          param.SecurityToken=''
          param.BucketName=''
          
          var params={}
          params.param=param;
          params.url=e.path;
          //上传路径
          params.objectkey='xxx/xxx/xx.png' 
          
          oss.upload(params,(process)=>{
              var send= process.send;
               var  total=process.total;

          },(res)=>{

             if(res.err==0)
             {
                 console.log('成功')
             }
             else
             {
                console.log('失败')
             }
          })

    });


}
```



