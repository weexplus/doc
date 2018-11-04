# keyboard

此module用于键盘控制

# api

```js
/**设置键盘状态（只android有效）
/**mode adjust_nothing,adjust_pan,adjust_resize
setKeyboardMode(mode)


/**是否启用自动控制（只ios有效）
enableAutoContorl(enble)

/**监听键盘弹出收起事件，事件参数胡返回键盘高度(show({height:}))
setKeyboardContorl(JSCallback show, JSCallback hide)
```

### demo

```js
let keyboard=weex.requireModule('keyboard')

//ios下根据回调参数调整页面布局，避免被遮挡
keyboard.enableAutoContorl(false)
keyboard.setKeyboardContorl((p)=>{
//键盘弹出
    let keyboardheight=p.height
    this.show(p.height);
},(p)=>{
//键盘收起

})
```



