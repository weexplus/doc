# 快速开始 {#erguotou525gmailcom}

_Windows系统的用户建议使用_`Cmder`_或者_`git bash`_作为命令行工具_

1. 安装`Git`，已安装的请忽略

   最简单的安装方法就是直接安装[官网的安装包](https://git-scm.com/downloads)，至于其它的使用包管理或者源码安装的方法请自行搜索。

2. 安装`NodeJs`，已安装的请忽略

   最简单的安装方法就是直接安装[官网的安装包](https://nodejs.org/en/download/)，至于其它的使用包管理或者源码安装的方法请自行搜索。

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

   切换到你的工作目录，执行**\(windows下务必确保使用管理员模式打开的cmd\)**

   ```bash
   weexplus create my_projectt com.app.id appname 
   (3个参数：1.项目名称 2.appid 3.app名称)

   如果网速不好，老是下载失败的同学请直接前往 https://github.com/weexplus/boilerplate，
   下载压缩包格式的，下载完之后解压得到一个
   boilerplate-master 文件夹，cd到跟boilerplate-master平级的目录，
   运行weexplus rename project_name com.demo.id appname 
   即可更改名称
   ```

   按照提示完成项目创建。此时在当前目录下就会有一个名为`my_project`的目录，里面就是我们的项目源码。

6. 运行创建的项目

   在命令行中执行

```
  cd my_project

  npm install

  npm run weexplus

  weexplus run android
```



