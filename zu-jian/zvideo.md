#player
首次使用```weexplus plugin add zvideo```

视频播放器（支持多种格式，支持全屏,支持手势调节音量进度亮度）

##事件
| 属性 | 作用 |
| :--- | :--- |
| onStart | 开始播放 |
| onPlaying | 播放中 |
| onPause | 暂停播放 |
| onCompletion | 播放完毕 |
##属性
| 属性 | 作用 |
| :--- | :--- |
| src | 播放地址 |
| autoPlay | 是否自动播放|
| title | 标题|

##方法
| 属性 | 作用 |
| :--- | :--- |
| play() | 播放|
| pause() | 暂停|
| seek(sec) | 播放到某一时间（单位毫秒）|
| fullScreen() | 全屏|
| quitFullScreen() | 退出全屏|

##demo
```
<template>
    <div>
        <player @onPlaying="start" img="root:img/logo.png" ref="video" style="width:750px;height:400px;background-color: black" title="xxxxx" auto-play="false"   src="http://mp4.vjshi.com/2013-07-25/2013072519392517096.mp4">

        </player>
        <div style="flex: 1;align-items: center;justify-content: center">
            <text>{{text}}</text>
            <button text="播放" @click="play"></button>
            <button text="暂停" @click="pause" style="margin-top: 20px"></button>
            <button text="全屏" @click="full" style="margin-top: 20px"></button>
            <button text="seek" @click="seek" style="margin-top: 20px"></button>
        </div>
    </div>
</template>
<script>

    export default{
        components: {},
        data(){
            return {
                text:''
            }
        },
        props: {},
        methods: {
            start(p){
                this.text=p.percent
            },
            play(){
                this.$refs.video.play()
            },
            pause(){
                this.$refs.video.pause()
            },
            full(){
                this.$refs.video.fullScreen()
//                this.$refs.video.toggleFullScreen()
            },
            seek(){
                this.$refs.video.seek(10)
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
