# 调试

控制台 `weex debug`

此时会弹出浏览器，如下图

![](/assets/WechatIMG50.jpeg)假设此时你的原生环境已经没问题了，那么先安装一次app，假设你现在需要调试src/index.vue并且ip也是如上ip， 那么此时要调试的编译后的js地址就是[http://192.168.199.248:9999/index.js](http://192.168.199.248:9999/index.js),[http://192.168.199.248:9999](http://192.168.199.248:9999/index.js)/对应项目下的dist目录，src/index.vue编译后就会在dist下生成index.js，好了现在把[http://192.168.199.248:9999/index.js](http://192.168.199.248:9999/index.js)生成二维码，打开app，点击设置-&gt;扫描二维码，这时app内部就得到了debugip,然后设置-&gt;开启debug，如果顺利界面变成如下样子

