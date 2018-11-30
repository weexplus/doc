# 打包

项目打包整体分为两步

1. 编译js\(weex-builder src dist \) 打压缩格式请加上--min\(weex-builder src dist --min\)
2. 将dist目录下的输出物copy到原生项目下，android是assets目录，ios是app目录
3. 原生打包



