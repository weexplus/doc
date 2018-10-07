# notify

基于原生的通知组件，你不需要持有目标组件的引用，即可通信，android基于eventbus实现，ios基于系统的notification实现

### API

```js
/**注册
*/
regist(key,callback)

/**
发送
*/
send(key,param)


/**
 发送给原生
*/
sendNative(key,param)

/**
设置图标上的数字
*/
setNumber(number)
```

### Demo

```js
send()
{
    var p={};
    p.v1='v1'
    var notify=weex.requireModule("notify")
    notify.send('key',p)
}


//写在其它页面created即可
created:function(){

     const notify = weex.requireModule('notify');
     notify.regist("key",function (res) {
          var v= res.v1;
      });  


   }
```



