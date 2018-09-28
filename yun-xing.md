# 运行

如何看到实际开发的效果，我们强烈推荐使用webstorm开发weex

2018-09-28日开始，我们支持3端，web端和native 两端的编译运行方式不同

## native 运行方式

首先请下载开发包，[https://pan.baidu.com/s/16kJfMuyXX-Y\_yhm5fHt79Q](https://pan.baidu.com/s/16kJfMuyXX-Y_yhm5fHt79Q)，或者android studiod打开项目目录/platforms/android/weexplus，自己编译一个apk，如果你懂android的话

1. 用webstorm打开项目

2. 找到位于下方的终端选项卡，开启一个，输入npm install，回车

3. 上一步完毕之后，输入npm run native

4. 在开启一个控制台，输入weexplus start,

5. 如果你用的Android手机，请再开启一个控制台像下图所示那样操作

记得先把你的手机插上，确保开发者模式已打开，usb调试也打开了，如果是小米手机还要记得把usb安装也勾上，等运行完毕，就会看到界面，当然这时候你只能在手机上看到加载失败的界面，因为默认加载的地址是http:127.0.0.1:9999/index.js，怎么改变这个地址，点击设置-&gt;扫描二维码，把新地址变成二维码扫描一次即可，这个地址会被存起来，除非重新扫了码。ios的 运行`weexplus run ios 按提示操作即可`

web

