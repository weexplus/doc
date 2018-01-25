# font

添加新字体组件，请将字体丢在src/font文件下，在运行npm run weexplus 之后，会自动同步到dist/font下，路径支持本地也支持远程

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



