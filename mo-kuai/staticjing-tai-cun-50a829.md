# static

用于存储全局变量，只要app不被杀死就会存在，用于存储登录后的user最合适了

### API

```js
  /**
  * 存储对象
  * @param key
  * @param value
  */
 set(key,value)

 /**
* 获取对象
* @param key
*/
 get(String key)

 /**
* 存储字符串
* @param key
* @param value
*/
setString(key,value)

/**
* 获取字符串
* @param key
*/
getString(String key)
```

### Demo

```js
   saveString()
          {
              var pref=weex.requireModule("static")
              pref.setString('key',11111);
              var modal=weex.requireModule("modal")
              modal.toast({message:'存储成功'});
          },

          getString()
          {
              var pref=weex.requireModule("static")
              var s= pref.getString('key');
              var modal=weex.requireModule("modal")
              modal.toast({message:'存储成功的值:'+s});
          },
          
          saveObj()
          {
              var pref=weex.requireModule("static")
              var obj={};
              obj.a=1;
              obj.b=2;
              obj.c=3;
              pref.set('objkey',obj);
              var modal=weex.requireModule("modal")
              modal.toast({message:'存储成功'});
              this.getObj();
          },

          getObj()
          {
              var pref=weex.requireModule("static")
              var p=  pref.get('objkey');
              this.data=p;
          },
```



