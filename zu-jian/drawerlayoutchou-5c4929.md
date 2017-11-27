# drawerlayout

抽屉组件

| 属性 | 作用 |
| :--- | :--- |
| src | 主页面地址 |
| slidSrc | 侧滑页面地址 |

### Demo

```
<template>
<drawerlayout
ref="drawer"
slid_src="userNav.js"
src="farmWork.js"
>

</drawerlayout>
</template>

<style>
.header {
width: 750px;
}
/*back按钮*/
.siftL {
position: absolute;
left: 0;
top: 40px;
width: 80px;
height: 80px;
z-index: 1000;
}

.icon-navR {
width: 80px;
height: 80px;
z-index: 1000;
}

.
.active {
background-color: blue;
}

.item {
margin-top: 1;
height: 180;
align-items: center;
background-color: #ffffff;
}

.item:active {
background-color: #e2e2e2;
}

.farmImage {
width: 60px;
height: 60px;
margin-bottom: 10px;
}

.text {
font-size: 28px;
color: #7f7f7f;
}
</style>
<script>
var head = require('../component/header.vue');
var flist = require('../component/flist.vue');
export default {
components: {head, flist},
data(){
return {
items: [
{"id":0,"url": "../img/crop1.png", "name": "玉米"},
{"id":1,"url": "../img/crop2.png", "name": "马铃薯"},
{"id":2,"url": "../img/crop3.png", "name": "大豆"},
{"id":3,"url": "../img/crop4.png", "name": "水稻"},
{"id":4,"url": "../img/crop5.png", "name": "小麦"},
{"id":5,"url": "../img/crop6.png", "name": "花生"},
{"id":6,"url": "../img/crop7.png", "name": "大豆"},
{"id":7,"url": "../img/crop8.png", "name": "谷子"},
{"id":8,"url": "../img/crop9.png", "name": "牧草"},
],

}
},
methods: {

crop_detail(item){
var nav=weex.requireModule('navigator')
nav.pushParam('cropList.js',item);

},
refresh: function () {

},

}
,
created: function () {

var notify=weex.requireModule("notify")
notify.regist('toggle',()=>{
this.$refs.drawer.toggle()
})

var globalEvent = weex.requireModule('globalEvent');
globalEvent.addEventListener("onPageInit", function(e) {

notify.sendNative('entry',{})

});
}
}
</script>
```



