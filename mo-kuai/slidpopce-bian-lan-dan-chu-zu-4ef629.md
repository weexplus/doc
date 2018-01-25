# slidpop

侧边栏弹出组件，方便把弹出层代码剥离成单独的文件

### API

```
   /**
     * 打开
     * @param url 弹出页面的js地址（支持root:写法）
     * @param param 参数
     * @param delt 宽度或者高度
     * @param offset  边距
     * @param side 从那一边出来(left,top,right,bottom)
     */
   public void show(String url, HashMap param,float delt,HashMap offset,String side)


    /**
    *关闭
    */
    public  void dismiss()
```

### Demo

```
 open()
 {
     var pop=weex.requireModule("slidpop")
     pop.show('page1.js',{},600,{},'bottom')
 }

 close()
 {
    var pop=weex.requireModule("slidpop")
    pop.dismiss();
 }
```



