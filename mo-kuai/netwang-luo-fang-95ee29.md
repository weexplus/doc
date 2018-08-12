# net

网络请求，自动保持cookie

### API

```js
   /**
   * @param url 地址
   * @param param 参数
   * @param header header
   * @param start 开始的回调
   * @param success status==200的回调
   * @param compelete 完成的回调，不论请求成功失败
   * @param exception status!=200的回调
   */ 
    post(url, param,header,start,success,compelete,exception)



     /* @param start 开始的回调
     * @param success status==200的回调
     * @param compelete 完成的回调，不论请求成功失败
     * @param exception status!=200的回调
     */
    postJson(url, param,header,start,success,compelete, exception)




    /**
    * @param url 地址
    * @param param 参数
    * @param header header
    * @param start 开始的回调
    * @param success status==200的回调 参数back,包含back.sessionid(可以用于保持sessionid),和返回结果back.res
    * @param compelete 完成的回调，不论请求成功失败
    * @param exception status!=200的回调
    */
    get(url, param,header,start,success,compelete,exception)




    /**
    * @param url 地址
    * @param param 参数
    * @param header header
    * @param path path
    * @param start 开始的回调
    * @param success status==200的回调
    * @param compelete 完成的回调，不论请求成功失败
    * @param exception status!=200的回调
    */
     postFile(url, param,header,path,start,success,compelete,exception)




   /**获取sessionid
    * @param url 地址
   */       
   getSessionId( url)


   /**清除所有cookie
    * 
   */ 
    removeAllCookies()

    /**
    *下载文件
    *@param url 下载地址
    *@param process 下载进度回调（current,total,percent））
    *@param compelete 下载完成回调
    *@param exception下载失败回调
    */
    download(url,process,compelete,exception)
```

### 

### Demo

```js
 post()
{
     var self=this;
    self.back="";
    const net = weex.requireModule('net');
    net.post('http://121.40.81.1:9080/edu/getBanners.do',{a:"1",b:"2"},{},function(){
        //start
    },function(e){
        //success
        self.back=e.res;

    },function(e){
      //exception

    },function(){
        //compelete
    });


},
get()
{

   //一个保持session的demo
    var self=this;
    const net = weex.requireModule('net');
    var st=weex.requireModule('static')
    var sessionId=st.getString('sessionId')
    var header={};
    p.Cookie=sessionId;
    self.back="";
    net.get('http://121.40.81.1:9080/edu/getBanners.do',{},header,function(){
        //start
    },function(e){
        //success
        self.back=e.res;
        st.setString('sessionId',e.res.sessionid);
    },function(e){
        //exception

    },function(){
        //compelete
    });
},

//上传文件
 openPhoto()
    {
        var self=this;
        const photo = weex.requireModule('photo');
        photo.openPhoto(500,800,'#000000','#ffffff','#ffffff',function(e){

            self.src=e.path;
            var param={};
            var header={};
            var path={};
            path.file=e.path;
            var net=weex.requireModule("net");
            net.postFile('http://xxx/upload',param,header,path,()=>{
                //start
            },(e)=>{
                //succcess
                var modal=weex.requireModule("modal")
                modal.toast({message:'上传成功！'})
            },()=>{
                //compelete

            },()=>{
                //exception
                var modal=weex.requireModule("modal")
                modal.toast({message:'上传异常！'})
            })

        });
    },
```



