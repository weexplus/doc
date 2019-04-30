#log
 打印日志,将日志打印在weexplus start控制台,已在初始化模板的mixin/main.js中加入了一个log方法，大家直接用this.log(msg,level)就行了
 
 ### API
 ```
 //param(msg:要打印的内容，level(日志级别error（红色）,warn（黄色）,info（黑色）)))
 
  log(param)
 ```
 
 ### demo
 ```
  let log=weex.requireModule('log')
  
  log.log({msg:'这是一条日志',level:'error'})
 ```