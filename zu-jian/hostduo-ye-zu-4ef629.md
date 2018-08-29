# host

一个多页面隐藏切换的组件，比如tab组件，会把内部的元素作为子页面，子页面填充满

| 属性 | 作用 |
| :--- | :--- |
| index | 当前显示那一页 |

# 事件

| 名称 | 触发时机 |
| :--- | :--- |
| load | 子元素加载完毕触发（注意：必须写在第一级子元素上） |
| show | 子元素显示时触发\(注意：必须写在第一级子元素上\) |

# Demo

```js
<template>
    <div style="flex: 1;background-color: #ffffff">

        <host style="flex: 1"   @change="onchange" :index="index">
            <!--<child style="background-color: red;display: flex">-->
            <div @load="load" @show="show" style="position: absolute;left: 0;top: 0;right: 0;bottom: 0;background-color: red;">
                <div style="flex: 1;background-color: #0085ee;justify-content: center;align-items: center">
                    <text style="font-size: 55">页面1</text>
                    <text>目前必须用2层div包裹才能保证填充满</text>
                    <text>第一层的样式必须是position: absolute;left: 0;top: 0;right: 0;bottom: 0;</text>
                    <text>第二层的样式必须是flex:1</text>
                </div>
            </div>
            <div style="position: absolute;left: 0;top: 0;right: 0;bottom: 0;background-color: red;">
                <div style="flex: 1;background-color: #0085ee;justify-content: center;align-items: center">
                    <text style="font-size: 55">页面2</text>
                    <text>目前必须用2层div包裹才能保证填充满</text>
                    <text>第一层的样式必须是position: absolute;left: 0;top: 0;right: 0;bottom: 0;</text>
                    <text>第二层的样式必须是flex:1</text>
                </div>
            </div>
            <div style="position: absolute;left: 0;top: 0;right: 0;bottom: 0;background-color: red;">
                <div style="flex: 1;background-color: #0085ee;justify-content: center;align-items: center">
                    <text style="font-size: 55">页面3</text>
                    <text>目前必须用2层div包裹才能保证填充满</text>
                    <text>第一层的样式必须是position: absolute;left: 0;top: 0;right: 0;bottom: 0;</text>
                    <text>第二层的样式必须是flex:1</text>
                </div>
            </div>
            <div style="position: absolute;left: 0;top: 0;right: 0;bottom: 0;background-color: red;">
                <div style="flex: 1;background-color: #0085ee;justify-content: center;align-items: center">
                    <text style="font-size: 55">页面4</text>
                    <text>目前必须用2层div包裹才能保证填充满</text>
                    <text>第一层的样式必须是position: absolute;left: 0;top: 0;right: 0;bottom: 0;</text>
                    <text>第二层的样式必须是flex:1</text>
                </div>
            </div>
        </host>

        <div style="height: 100;width: 750;position: absolute;bottom: 0;left: 0;right: 0;flex-direction: row;background-color: #0088fb">
            <div  @click="change(0)" style="flex: 1;align-items: center;justify-content: center">
                <text>推荐</text>
            </div>
            <div @click="change(1)" style="flex: 1;align-items: center;justify-content: center">
                <text>电视剧</text>
            </div>
            <div @click="change(2)" style="flex: 1;align-items: center;justify-content: center">
                <text>电影</text>
            </div>
            <div @click="change(3)" style="flex: 1;align-items: center;justify-content: center">
                <text>收藏</text>
            </div>
        </div>
        <!--<prerender src="home.js"></prerender>-->

        <!--<prerender src="app/busi/tab/serial.js"></prerender>-->
        <!--<a href="demo/pagedemo.js" style="width: 100;height: 100;background-color: red;justify-content: center;align-items: center"><text>跳转</text></a>-->
    </div>

</template>

<style>


</style>

<script>


    export default {
        components:{},
        data(){
           return {
             logoUrl: 'http://img1.vued.vanthink.cn/vued08aa73a9ab65dcbd360ec54659ada97c.png',
             target: 'World',
             index:0,

           }
        },
        methods: {
           onchange(p){
             this.toast(p.index)
           },
            update: function (e) {
                this.target = 'Weex'
                console.log('target:', this.target)
            },
            change(i)
            {
                this.index=i;

            },
            show()
            {
                var modal=weex.requireModule("modal")
                var p=weex.config.env.osVersion
//              p=p.replace('.', "")
//          p=p.replace(/./g,"");
                p= p.replace(/\./g,'')
                modal.alert({message:p})
            }
        }
        ,


        created:function(){


            var globalEvent = weex.requireModule('globalEvent') ;
            var self=this;
            globalEvent.addEventListener("onPageInit", function (e) {


                const page = weex.requireModule('page');
                page.closeSplash();



            });

        },
    }
</script>
```



