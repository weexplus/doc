# 图片使用

项目中使用的所有图片请放在src/img文件夹下，在开启 weexplus start之后，对此文件夹的任何操作都会自动同步到dist/img下，真正使用的是dist/img下的图片，如果没有同步过去，请重新运行下weexplus start

![](/assets/WechatIMG56.png)

### 代码如何写

第一种

以相对路径来写

```
<image src="../img/back.png"></image>
```

 

第二种

以绝对路径来写,root:代表根目录，当你的vue是组件的时候，这时候机算相对路径是以宿主的路径来计算的，会造成错误，这时候必须用这种写法

```
<image src="root:img/back.png"></image>
```



