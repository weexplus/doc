# 运行

如何看到实际开发的效果，我们强烈推荐使用webstorm开发weex

2018-09-28日开始，我们支持3端，web端和native 两端的编译运行方式不同

## native 运行方式

**首次运行前 请先执行 npm install，将相关依赖安装**
首先请下载开发包，一个apk,[https://pan.baidu.com/s/1jBSCXvNBWLahKNo97iwhVA](https://pan.baidu.com/s/1jBSCXvNBWLahKNo97iwhVA)，或者android studiod打开:**项目名称/platforms/android/项目名称**，自己编译一个apk，如果你懂android的话，之后安装好开发包

**确保机器安装了chrome**

1. 用webstorm打开项目

2. 找到位于下方的终端选项卡，开启一个，输入npm install，回车

3. 上一步完毕之后，输入npm run native

4. 在开启一个控制台，输入weexplus start ，此时会弹出浏览器，在上面选中一个js文件，注意这步很重要，然打开安装好的开发包,点击设置-&gt;扫描二维码，扫描浏览器上的二维码，即可在开发包里看到效果

## web版运行方式

1.开启一个控制台 运行weexplus start

2.再开启一个控制台，运行npm run web

以上操作都要在项目根目录执行

