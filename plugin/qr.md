# qr\(二维码\)
**首次使用请执行weexplus plugin add https://github.com/farwolf2010/qr**

一个相机组件，只用来识别二维码，条形码，和module下的qr不一样，这个方便自定义扫描的界面，更为灵活

### api

```


/** 开始扫描
scan(callback)


/** 停止扫描
stop()

 
```

### demo

```
<template>
    <div>
        <text>{{text}}</text>

        <qr ref="qr" style="position: absolute;top: 0;left: 0;right: 0;bottom: 0">

        </qr>
        <div  style="position: absolute;top: 0;left: 0;right: 0;bottom: 0;background-color: transparent;">
           <!--<button @click="start"></button>-->
           <!--<button @click="stop"></button>-->
            <div style="width: 750px;flex: 1;background-color: rgba(0,0,0,0.3)"></div>
            <div style="height: 450px;flex-direction: row">
                <div style="width: 150px;background-color: rgba(0,0,0,0.3)">

                </div>
                <div style="flex: 1"></div>
                <div style="width: 150px;background-color: rgba(0,0,0,0.3)">

                </div>
            </div>
            <div style="width: 750px;flex:1;background-color: rgba(0,0,0,0.3)"></div>

        </div>

    </div>
</template>
<script>

    export default{
        components: { },
        data(){
            return {
                text:''
            }
        },
        props: {},
        methods: {
            start(){

            },
            stop(){

            },
            onLoad(p){

            }
        },
        mounted(){
          this.$refs.qr.scan((res)=>{
             this.text=res.res
              this.toast(this.text)

          })
        },
        created(){

        }
    }
</script>
<style scoped>

</style>
```