# 热更新配置步骤

1. 准备更新包：

    将configs/weexplus.json jsVersion的值加一个版本
    运行：weexplus zip
    会生成一个app.zip在项目根目录下
    将app.zip丢到服务器上

2.数据库配置

```
  打开hotupdate表

  新增一条记录

  按字段要求填写

  url填写刚那个app.zip

  js_version填写为之前修改的值
```



