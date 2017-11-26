# progress

一个简单的无状态进度指示器

### API

```
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
```



