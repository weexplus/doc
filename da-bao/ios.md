# ios打包

1. 请确认weexplus start正在运行
2. 修改configs/weexplus.json debug=false  关闭debug模式  showerror=false 关闭报错提示

      此时会自动同步到原生项目目录中去

3. 在项目根目录运行weexplus copy \(将dist目录下的内容copy到 ios 项目下的assets文件夹\)

4. 双击（项目目录/platforms/ios/项目名/项目名.xcworkspace），如果不存在，请现在（项目目录/platforms/ios/项目名）目录下运行 pod install

5. 插上手机，选中手机，点击run ，如下图，这样是直接安装到手机里

6. ![](/assets/1526093134213.jpg)

7.打正式包（需要有开发者），然后按要求下一步就行，说的很简单，附上一个详细文档[https://www.jianshu.com/p/cea762105f7c](https://www.jianshu.com/p/cea762105f7c)

![](/assets/1526093317148.jpg)

