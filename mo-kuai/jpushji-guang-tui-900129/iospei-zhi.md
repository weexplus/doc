# ios配置

1.配置ios推送证书，详细请参考极光的档案：传送门[https://docs.jiguang.cn/jpush/client/iOS/ios\_cer\_guide/](https://docs.jiguang.cn/jpush/client/iOS/ios_cer_guide/)

将极光的appkey填到如下位置（需要你配置好证书后才会有appKey）![](/assets/1790357F-CF01-41FA-8F29-30C5D6AD68E8.png)

如何配置极光的ios推送证书

选中你的appid,点击下方的edit

![](/assets/A8E5A0E1-C717-4E4A-AEA6-31149E748494.png)点击下图所示2处，按提示继续

![](/assets/B62A446F-B88B-43FF-A344-6B62168A2429.png)然后再点击证书面板，如下图，会多出2条推送证书，下载下来，安装

![](/assets/F791FA01-86C7-4530-9997-528886CB35DF.png)不过下载下来的是cer文件，我们需要的是p12文件，这时候你需要打开钥匙串，选中刚才的证书，右键导出，同时设置密码，记住此密码，这样就能导出p12文件了

![](/assets/C2DF2BFE-3D91-4A43-8225-579B0AE2F407.png)然后在极光后台上传这2个文件，点保存之后，如果得到下图就是配置好了![](/assets/0B9F10BB-A083-4722-8CA2-8694F7E3C608.png)

