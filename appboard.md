# appBoard

weex默认采用的分包模式，即一个页面一个vue，这样做的缺点是，共有的js会被添加进每一个vue里面假设有100个页面，共有js的体积是100kb，那么最终编译的体积是`100x100=10000kb`,现在采用appboard，共有js有native拼接引入，如此一来，共有js不再编译到每一个vue里面，最终体积变成了`100x1=100kb`

使用方法：

在config/weexplus.json中有appAboard字段，采用root:写法指定共有js路径，root:代表src,比如src/index.js，则写成root:index.js,这样在调试的时候加载的是dist/index.js，最终打包后加载的是assets/app/index.js

在此index.js写的东西，将自动在vue中引入

