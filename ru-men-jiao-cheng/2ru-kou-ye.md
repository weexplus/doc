# 入口页设置

修改configs/weexplus.json  entery 字段

地址可以是网络地址，也可以是本地地址

### 加载顺序：

在debug=true的状态下，app启动会优先加载上次扫码的地址，如果没有才会加载entry指定的地址

在debug=false的状态下，app启动智慧加载entry指定的地址

重点说明：entry指定的页面不是真正的首页，这个页面只是用来写跳转逻辑的过渡页面

