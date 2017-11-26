# navigator

众所周知，在浏览器里，我们可以通过前进或者回退按钮来切换页面，iOS/Android 的navigator模块就是用来实现类似的效果的。除了前进、回退功能，该模块还允许我们指定在切换页面的时候是否应用动画效果。

### API

导航跳转

```js
注意：使用push，pushParam，pushFull打开的页面只能用back,backFull返回，使用present打开的页面，只能用dismiss关闭

/**
@param url 相对地址
*/
push(url)

/**
@param url 相对地址
@param param 参数
*/
pushParam(url,param )

/**
@param url 相对地址
@param param 参数
@param navbarVisibility 原生导航栏是否可见（已废弃）
@param callback 页面返回时的回调
@param animate 使用动画（android无效）
*/
pushFull(url,param,navbarVisibility,callback,animate)

/**
关闭当前页面，返回上一个页面，
*/
back()

/**
关闭当前页面，返回上一个页面，同时带上参数
@param param 带给上一个页面的参数
@param animate 是否使用动画，（android无效）
*/
backFull(param,animate)


/**
打开一个页面，动画是从下往上弹出来
*/
present()

/**
打开一个页面，动画是从下往上弹出来
@param url 相对地址
@param param 参数
@param navbarVisibility 原生导航栏是否可见（后面会废弃）
@param createnav 是否创建导航控制器，默认是（后面会废弃）
@param  callback 页面返回时的回调
@param  animate 使用动画（android无效）
*/
presentFull(url,param, navbarVisibility, createnav,callback,animate)

/**
关闭，present开头方法打开的页面
*/
dismiss()


/**
关闭，present开头方法打开的页面，同时带上参数
@param param 带给上一个页面的参数
@param animate 是否使用动画，（android无效）
*/
backFull(param,animate)




```

```

```



