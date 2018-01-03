# centerpop

从中间弹出的组件，方便把弹出层代码剥离成单独的文件

### API

```
   /**
     * 打开
     * @param url 弹出页面的js地址
     * @param style (内置参数：width,height)
     * @param param 传递的参数
     * @param clickDismiss  点击遮罩层是否消失
     */
    public void show(String url, HashMap style, HashMap param, Boolean clickDismiss)


    /**
    *关闭
    */
    public  void dismiss()
```

### Demo

```
 open()
 {
     var pop=weex.requireModule("centerpop")
     pop.show('center.js',{width:500,height:700},{},true);
 }

 close()
 {
    var pop=weex.requireModule("slidpop")
    pop.dismiss();
 }
```



