# 运行

如何看到实际开发的效果，我们强烈推荐使用webstorm开发weex

2018-09-28日开始，我们支持3端，web端和native 两端的编译运行方式不同

## native 运行方式

首先请下载开发包，一个apk,[https://pan.baidu.com/s/16kJfMuyXX-Y\_yhm5fHt79Q](https://pan.baidu.com/s/16kJfMuyXX-Y_yhm5fHt79Q)，或者android studiod打开项目目录/platforms/android/weexplus，自己编译一个apk，如果你懂android的话，之后安装好开发包

**确保机器安装了chrome**

1. 用webstorm打开项目

2. 找到位于下方的终端选项卡，开启一个，输入npm install，回车

3. 上一步完毕之后，输入npm run native

4. 在开启一个控制台，输入weexplus start ，此时回弹出浏览器，在上面选中一个js文件，注意这步很重要，然打开安装好的开发包,点击设置-&gt;扫描二维码，扫描浏览器上的二维码，即可在开发包里看到效果

5. 




