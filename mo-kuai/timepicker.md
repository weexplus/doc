# timepicker
**首次使用请执行weexplus plugin add timepicker,然后重新打包才生效**

时间选择器，支持年月日时分一起选

![](https://bmfe.github.io/eros-docs/zh-cn/image/qbmDatePicker.gif)
### api

```
  let dateTimePicker=weex.requireModule('timepicker')
                dateTimePicker.open({
                    value: '',//必选,选中的值，格式为yyyy-MM-dd HH:mm;当value为空,默认选中当前时间;当value不为空时为返回值
                    max: '',//可选，日期最大值,默认2099-12-31 23:59
                    min: '',//可选，日期最小值,默认1900-12-31 00:00
                    title: '',//可选，标题的文案，默认为空
                    titleColor: '',//可选，默认为空,title不为空时有效，颜色值（#313131）
                    confirmTitle: '', //确认按钮的文案,默认值（完成）
                    confirmTitleColor: '', //确认按钮的文字颜色，默认值(#00b4ff)
                    cancelTitle: '', //取消按钮的文案,默认值（取消）
                    cancelTitleColor: '', //取消按钮的文字颜色,默认值(#313131)
                },(res) =>{//回调
                    //返回字段
                    //result{string}：success,cancel
                    //data {string}：格式为yyyy-MM-dd HH:mm
                    if(res.result === "success"){
                        //业务逻辑
                         this.text=res
                    }else{
                        //业务逻辑
                    }
                });
```

 