# fpicker

picker组件，最多三列，可简单定制外观

### API

```js
注意:setCount必须第一个调用，以初始化picker

设置picker有几列
/**
* @param count 列数
*/
setCount(count)


设置第一列的数据
/**
* @param list 数据
*/
setItems1(list)

设置第二列的数据
/**
* @param list 数据
*/
setItems2(list)


设置第三列的数据
/**
* @param list 数据
*/
setItems3(list)


设置主题色
/**
* @param bgcolor 背景色
* @param btncolor 按钮文字颜色
*/
 setTheme( bgcolor, btncolor)



/*
* 显示picker
*/
 show()

  用户选中项目时调用此方法设置的回调
 /**
  * 回调
  * @param callback
  */
 setDone(callback)
 
 
 
 三个滚轮滚动时触发的回调，可在此设置关联关系
   /**
   * 
   * @param change1
   * @param change2
   * @param change3
   */
 setChange( change1, change2, change3)
 
 

```



