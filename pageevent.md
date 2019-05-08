# 页面事件
所有的事件都已globalevent的形式向外发送

```
//android+ ios
/**param 上一个页面传递过来的参数
onPageInit(param)

//android 页面显示的时候触发
onResume

//ios 页面开始显示的时候触发
viewWillAppear

//ios 页面即将消失的时候触发
viewWillDisappear

```

以上事件都已在appboard中做了js层的封装，只要要在methods定义如下方法，自动就能接收事件
```
method:{
	onLoad(param){
	
	}
	onResume(){
	
	}
	viewWillAppear(){
	
	}
	viewWillDisappear(){
	
	}
}

```



