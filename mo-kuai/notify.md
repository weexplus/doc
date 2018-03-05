# navigator

众所周知，在浏览器里，我们可以通过前进或者回退按钮来切换页面，iOS/Android 的navigator模块就是用来实现类似的效果的。除了前进、回退功能，该模块还允许我们指定在切换页面的时候是否应用动画效果。

### API

导航跳转

```js
注意：使用push，pushParam，pushFull打开的页面只能用back,backFull返回，使用present打开的页面，只能用dismiss关闭
     push打头的方法和present方法打头的方法区别是动画效果不一样，push是由右往左打开一个页面，present是由下往上打开

/**
@param url 相对地址（支持root:写法）
*/
push(url)

/**
@param url 相对地址（支持root:写法）
@param param 参数
*/
pushParam(url,param )


/**
@param parameters (url：'地址',param:'参数',animate:'是否使用动画',isPortrait:'是否是竖屏')
@param callback 页面返回时的回调
*/
pushFull(parameters,callback)

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
@param url 相对地址（支持root:写法）
@param param 参数
@param createnav 是否创建导航控制器，默认是（后面会废弃）
@param  callback 页面返回时的回调
@param  animate 使用动画（android无效）
*/
presentFull(parameters,callback)

/**
关闭，present开头方法打开的页面
*/
dismiss()


/**
关闭，present开头方法打开的页面，同时带上参数
@param param 带给上一个页面的参数
@param animate 是否使用动画，（android无效）
*/
dismissFull(param,animate)
```

获取参数

```js
注意：此方法只有写在onPageInit里面才能有效获取
/**
 获取上一个页面传递来的参数，
*/
param()
```

定页返回

```js
如果你打开的了多个页面，现在希望越过中间的页面，返回第一个或其它页面，这里的方法将帮你做到

/**
 返回指定id的页面，id由setPageId方法设定
*/

backTo(id)


/**
设置当前页的id
*/
setPageId(id)

/**
将此页面及这个页面之后打开的页面纳入一个堆栈,
*/
setRoot(id)

现在来说一下怎么达到效果，假设有A->B->C三个页面，现在希望从C直接回到A
1.在A的onPageInit中调用setRoot('A'),setPageId('A')
2.在C中backTo('A')
```

## Demo

```js
  /**推入式跳转
  push()
  {
      var nav = weex.requireModule('navigator') ;
      //相对路径写法，也可以root:绝对路径
      nav.push('page1.js')
  }

  /**带参数推入式跳转
  pushWidthParam()
  {
   var self=this;
   var nav = weex.requireModule('navigator') ;
   var param={};
   param.a='value1'
   nav.pushParam('page1.js',param);
   //或者
   nav.pushFull({
                    url: 'navlanscape.js',
                    param: {a: '这是传过来的值'},
                    animate:true,
                    isPortrait:false
                }, (e) => {
                    if (e != undefined)
                        self.callbackdata = e.ok;
                })
  }

  /**弹出式跳转
  present(){
    var self=this;
    var nav = weex.requireModule('navigator') ;
    nav.present('page1.js')
    //或者
    nav.presentFull({
        url: 'navlanscape.js',
        param: {a: '这是传过来的值'},
        animate:true,
        isPortrait:false
        }, (e) => {
        if (e != undefined)
        self.callbackdata = e.ok;
        })
  },


  /**获取参数
  created:function(){

          var self=this;
          var globalEvent = weex.requireModule('globalEvent') ;
          globalEvent.addEventListener("onPageInit", function (e) {


              var navigator = weex.requireModule('navigator') ;
              var param=navigator.param();



          });
      }
```



