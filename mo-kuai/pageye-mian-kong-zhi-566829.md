# page

页面控制器

## api

```js
/**重新渲染本页面
reload()



/**启用双击退出
doubleBack()



/**是否拦截返回键（针对android）
enableBackKey(enbale)


/**拦截返回键触发的回调
setBackKeyCallback(callback)


/**退出应用（android有效）
exit()
```

# Demo

```js
var page=weex.requireModule("page")
page.reload();
page.doubleBack();

page.enableBackKey(false);
page.setBackKeyCallback(()=>{
 page.enableBackKey(true);

})

page.exit();
```



