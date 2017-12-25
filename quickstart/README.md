# 快速开始 {#erguotou525gmailcom}

_Windows系统的用户建议使用_`Cmder`_或者_`git bash`_作为命令行工具_

1. 安装`Git`，已安装的请忽略

   最简单的安装方法就是直接安装[官网的安装包](https://git-scm.com/downloads)，至于其它的使用包管理或者源码安装的方法请自行搜索。

2. 安装`NodeJs`，已安装的请忽略

   最简单的安装方法就是直接安装[官网的安装包]([https://nodejs.org/zh-cn/download)，至于其它的使用包管理或者源码安装的方法请自行搜索。

3. 安装`weex-toolkit`，已安装的请忽略

   ```bash
   npm install  weex-toolkit -g
   ```

4. 安装脚手架工具`weexplus`，已安装的请忽略

   使用命令行执行

   ```bash
   npm install weexplus -g
   ```

   weexplus工具为我们提供了很多常用的开发功能，后续会一一介绍。

5. 创建项目

   切换到你的工作目录，执行

   ```bash
   weexplus create my_project
   ```

   按照提示完成项目创建。此时在当前目录下就会有一个名为`my_project`的目录，里面就是我们的项目源码。

6. 运行创建的项目

   在命令行中执行

   ```bash
   cd my_project

   npm install

   npm run weexplus


   ```

   然后打开浏览器前往`http://localhost:9999`就可以看到项目运行的效果，使用playground扫描页面上的二维码可以在手机中查看运行效果。

7. 调试

   还是在命令行中执行

   ```bash
   npm run debug
   ```

   此时会打开调试设备列表页面，之后的操作和官网一样，具体调试方法请参考[官网说明](https://weex.apache.org/cn/guide/tools/toolkit.html#调试-Weex-页面)。



