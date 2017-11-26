# progress

一个简单的无状态进度指示器

### API

```js
/**
  * 显示
  */
 show()

 /**
  * @param txt 加载的文字
  */
 showFull(txt)


/**
 *关闭
 */
 dismiss()
```

### Demo

```js
 post()
    {
         var self=this;
        self.back="";
        const net = weex.requireModule('net');
        const progress = weex.requireModule('progress');        
        net.post('http://121.40.81.1:9080/edu/getBanners.do',{a:"1",b:"2"},{},function(){
            //start
            progress.show()
        },function(e){
            //success

        },function(e){
          //exception

        },function(){
            //compelete
            progress.dismiss()
        });


    },
```



