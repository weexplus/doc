# 入口页设置

请将src/native/entry.vue中的root:index.js 换成你自己的首页，（有关root:写参考文档）
如下图

 ![](/assets/11.png)
 
 这样在debug=false（正式包，记得改完要重新打包）之后就能正确跳转了。

 **但是在debug=true的时候，不会按这个地址跳转，debug=true的时候，会优先加载上次扫码之后保存的地址，如果没有则会加载debugEntry指定的地址，如果是模拟器使用，则直接改debugEntry地址就行了（因为模拟器没法扫码）**


