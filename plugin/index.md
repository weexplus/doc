#插件化
 随着功能的增加，将所有的第三方模块都加进核心包显然是不合理的，因为你不见得需要。所以为了控制包的体积，引入了插件化的机制
 
** 插件的添加命令是：```weexplus plugin add xxxx``` **

** 插件的删除命令是：```weexplus plugin remove xxxx``` **

执行完命令，显示成功之后，需要重新打包，方可生效