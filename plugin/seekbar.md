#seekbar
首次使用请先weexplus plugin add seekbar
进度条，可以拖拽，因为weex对手势支持的不好，特此搬了一个原生的过来

###属性
| 属性 | 作用 |
| :--- | :--- |
| color | 颜色|
| progress | 进度|
| max | 最大值|
| min | 最小值|

###事件
| 名称 | 触发时机 |
| :--- | :--- |
| start | 开始执行拖拽时触发 |
| stop | 结束执行拖拽时触发 |
| change | 进度发生改变触发 |

###demo
```
<template>
    <div style="align-items: center">
        <head></head>
        <button text="ok" @click="show"></button>
        <seekbar @click="onstop" @start="onstart" @stop="onstop" @change="change" :max="total" :progress="progress"  style="width:600px;height: 100px;"  color="#238FFF"></seekbar>
        <text>{{v.value}}--{{total}}</text>
        <button text="seek" @click="seek"></button>
    </div>
</template>
<script>
    export default{
        props: {},
        data(){
            return {
                v:{},
                min:0,
                total:10000,
                progress:0,
                isPlaying:false,
            }
        },
        methods: {
            onstart(){
                let audio=weex.requireModule('audio')
                audio.pause()
                this.isPlaying=false
            },
            onstop(){
//                let audio=weex.requireModule('audio')
////                audio.play('https://sur.nhc55555.com/uploads/2019-04/10/00b38343269dd25980bfa9a77f1a1584.mp3')
////                audio.seek(this.v.value)
//                audio.seek(12000)
//                this.log('stop')
//                this.isPlaying=true
                this.seek()
            },
            seek(){
                let audio=weex.requireModule('audio')
                audio.seek(12000)
            },
            change(m){
                this.v=m
//                this.log(this.v)
//                this.progress=m.value

            },
            show(){
//              let pro=weex.requireModule('progress')
                this.isPlaying=true
              let audio=weex.requireModule('audio')
                audio.play('http://59.110.169.246/img/1.mp3')
                audio.setOnPlaying((res)=>{
                    this.total=res.total
//                    this.log(res)
                    if(this.isPlaying){
                        this.progress=res.current
                    }


                })
//                pro.show()
            },
            onLoad(p){

            }
        },
        created(){

        }
    }
</script>
<style scoped>

</style>
```
