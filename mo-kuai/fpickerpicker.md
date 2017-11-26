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


 /**
*  选中某一列某一行
* @param c 列数
* @param row 行数
* 
*/
 select( c, row)
```

### Demo

```js
const data=require('./data.js')

export default {

    get(res)
    {
        var self=this;
        var picker=weex.requireModule("fpicker");
        var d=data.getAddressData();
        var l= d.list
        //务必调用此方法，此方法有初始化的功能，最多3列
        picker.setCount(3);
        picker.setItems1(this.toArray(l))
        picker.setItems2(this.toArray(l[0].children))
        picker.setTheme('#f9f9f9','#4c4c4c')

        var index1=0;
        var index2=0;
        var index3=0;
        //每个滚轮的change事件
        picker.setChange(function(e){

            index1=e.index;
            picker.setItems2(self.toArray(l[index1].children))
            picker.select(2,0);
            if(l[index1].children.length>0)
            {

                picker.setItems3(self.toArray(l[index1].children[0].children))

                picker.select(3,0);
            }
            else
            {
                picker.setItems3([])
            }

        },function(e){
            index2=e.index;
            if(l[index1].children[index2].children.length>0)
            {
                picker.setItems3(self.toArray(l[index1].children[index2].children))
                picker.select(3,0);
            }
            else
            {
                picker.setItems3([])
            }
        },function(e){
            index3=e.index;
        })
        //点击完成的事件
        picker.setDone(function(e){
            var p1= l[e.index1];
            var p2= l[e.index1].children[e.index2];
            var p3= l[e.index1].children[e.index2].children[e.index3];
            res(p1,p2,p3)

        });
        // picker.show()
        return picker;
    },

    toArray(list)
    {
        var p=[];
        for(let i=0;i<list.length;i++)
        {
            p.push(list[i].name);
        }
        return p;
    },


}
```



