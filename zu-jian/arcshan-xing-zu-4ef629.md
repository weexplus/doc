# arc

扇形组件

| 属性 | 作用 |
| :--- | :--- |
| start | 起始度数 |
| angle | 角度 |
| color | 颜色 |

# Demo

```js
<template>
    <div :style="{'width':diameter,'height':diameter}"   style="align-items: center;justify-content: center;">
        <arc class="fill" :style="{'width':diameter,'height':diameter}" start="270" angle="360" color="#bdbdbd" ></arc>
        <arc class="fill" :style="{'width':diameter,'height':diameter}" start="270" :angle="percent/100*360" :color="circleColor"  ></arc>
        <div :style="{'width':diameter-circleWidth,'height':diameter-circleWidth}"  style="align-items: center;justify-content: center;">
            <arc  class="fill"  start="270" angle="360" color="#ffffff"  ></arc>
            <text  :style="{'color':circleColor,'font-size':fontSize}">{{percent}}%</text>
        </div>
    </div>
</template>

<style>
.fill
{
    position: absolute;
    left: 0;
    top:0;
    right:0;
    bottom: 0;
}
</style>

<script>
 export default{
     props:{
         fontSize:{
            default :38
         },
          diameter:{
              default:120
          },
         circleWidth:
         {
             default:20
         },
         circleColor:
         {
             default:"#000000"
         },
         percent:{
             default:10
         }

     }
 }
</script>
```



