### net

网络访问

### API

```js
  /** post请求  
   * @param url 地址
   * @param param 参数
   * @param header header
   * @param start 请求开始的回调
   * @param success status==200的回调
   * @param compelete 请求完成的回调，不论成功失败
   * @param exception status!=200的回调
   */
  post(url,param, header,start, success, compelete, exception)



  /** get请求
  * @param url 地址
  * @param param 参数
  * @param header header
  * @param start 请求开始的回调
  * @param success status==200的回调
  * @param compelete 请求完成的回调，不论成功失败
  * @param exception status!=200的回调
  */
  get(url,param,header,start,success,compelete,exception)

 /**
   * 
   * @param url 地址
   * @param param 参数
   * @param header header
   * @param path 文件地址可以有多个
   * @param start 请求开始的回调
   * @param success status==200的回调
   * @param compelete 请求完成的回调，不论成功失败
   * @param exception status!=200的回调
   */
   postFile(url,param,header,path,start,success,compelete,exception)
```

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
        self.header=r.headers;
    },function(e){
      //exception

    },function(){
        //compelete
    });


 },
get()
 {


    var self=this;
    const net = weex.requireModule('net');
    self.back="";
    net.get('http://121.40.81.1:9080/edu/getBanners.do',{},{},function(){
        //start
    },function(e){
        //success
        self.back=e.res;
    },function(e){
        //exception

    },function(){
        //compelete
    });


}
```



