#audio
首次使用```weexplus plugin add audio ```
### api

```
/**
播放
url（支持root:）
**/
play(url)

 /**
暂停
**/
pause()

/**
 停止播放
**/
stop()


/**
快进
msec（毫秒数）
**/
seek(msec)

/**
是否正在播放，同步返回true,false
**/
isPlay()

/**
调整音量
volume（0-100）
**/
volume(volume)

/**
循环播放
loop（是否循环播放：true,false）
**/
loop(loop)

/**
设置开始播放的回调
**/
setOnStartPlay(callback)

/**
设置正在播放的回调
callback(res) res:{current:毫秒数,total:总毫秒数，percent：播放进度}
**/
setOnPlaying(callback)

/**
设置播放结束的回调
**/
setOnCompletion(callback)


/**
设置错误的回调
**/
setOnError(callback)
 
```



#demo

```
<template>
    <div style="align-items: center;justify-content: center">
        <text style="color: #000000">{{p}}</text>
        <button text="播放" @click="play"></button>
        <button text="暂停" @click="pause" style="margin-top: 20px"></button>
        <button text="停止" @click="stop" style="margin-top: 20px"></button>
        <button text="seek" @click="seek" style="margin-top: 20px"></button>
        <!--<button text="暂停" @click="play" style="margin-top: 20px"></button>-->

    </div>
</template>
<script>
    export default{
        data(){
            return {
                p:''
            }
        },
        props: {},
        methods: {
            play(){
                let audio=weex.requireModule('audio')
                audio.play('http://59.110.169.246/img/1.mp3')
            },
            pause(){
                let audio=weex.requireModule('audio')
                audio.pause()
            },
            stop(){
                let audio=weex.requireModule('audio')
                audio.stop()
            },
            seek(){
                let audio=weex.requireModule('audio')
                audio.seek(112160)
            },
            onLoad(p){
                let audio=weex.requireModule('audio')
                audio.setOnPlaying((res)=>{
                    this.p=res;
                })
                audio.setOnCompletion((res)=>{
                    this.p='播放完毕';
                })
            },

        },
        created(){

        }
    }
</script>
<style scoped>

</style>
```