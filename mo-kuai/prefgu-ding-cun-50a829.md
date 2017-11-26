# pref

持久存储，即使app关闭之后也会存在，类似于cookie

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

Demo

