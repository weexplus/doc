# pref

持久存储，即使app关闭之后也会存在，类似于cookie,android基于sharerefrence，Ios基于NSUserDefaults

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
          var pref=weex.requireModule("pref")
          pref.setString('key',this.text);
          var modal=weex.requireModule("modal")
          modal.toast({message:'存储成功'});

      },

      getString()
      {
          var pref=weex.requireModule("pref")
          var s= pref.get('key');
          var modal=weex.requireModule("modal")
          modal.toast({message:'存储成功的值'+s});
      },
      remove()
        {
            var pref=weex.requireModule("pref")
            pref.remove('key')
            pref.remove('objkey')
            var s= pref.get('key');
            var modal=weex.requireModule("modal")
            modal.toast({message:'删除成功：'+s});
        },
      saveObj()
      {
          var pref=weex.requireModule("pref")
          var obj={};
          obj.a=1;
          obj.b=2;
          pref.setObj('objkey',obj);
          var modal=weex.requireModule("modal")
          modal.toast({message:'存储成功'});
      },

      getObj()
      {
          var pref=weex.requireModule("pref")
          var p=  pref.getObj('objkey');
          this.data=p;
//              var modal=weex.requireModule("modal")
//              modal.toast({message:p});
      },
```



