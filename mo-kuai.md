### net

网络访问

### API

```js
   /**     
     * @param url 地址
     * @param param 参数
     * @param header header
     * @param start 请求开始的回调
     * @param success status==200的回调
     * @param compelete 请求完成的回调，不论成功失败
     * @param exception status!=200的回调
     */
    post(url,param, header,start, success, compelete, exception)

    
        
     /**
     * 
     * @param url
     * @param param
     * @param header
     * @param start
     * @param success
     * @param compelete
     * @param exception
     */ 
      get(String url , HashMap param, HashMap header, final JSCallback start, final JSCallback success, final JSCallback compelete, final JSCallback exception)
             
```



