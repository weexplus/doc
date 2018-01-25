# font

添加新字体组件

### **Api**

```
    /**
     * @param name 自定义字体名称
     * @param url 路径,支持root:写法
     */ 
  public void addFont(String name, String url)
```

### Demo

```
  var font=weex.requireModule("font");
  font.addFont('erp','root:font/agriculture.ttf')
  
```



