#shot
**首次使用请执行```weexplus plugin add https://github.com/farwolf2010/shot```**

截图功能，传入ref，即可得到组件的截图
##api
```
/**ref 组件的id
** callback 回调，返回值:({path:'图片路径'})
**/
shot(ref,callback)
```

##demo
```
<template>
    <div ref="root" style="align-items: center;justify-content: center">
        <text ref="txt">{{src}}</text>
        <button ref="btn" text="截屏" @click="shot"></button>
        <image  ref="img" :src="src" style="width: 200px;height: 400px;background-color: red">

        </image>
    </div>
</template>
<script>
    export default{
        data(){
            return {
                src:''
            }
        },
        props: {},
        methods: {
            shot(){
                let shot=weex.requireModule('shot')
                shot.shot(this.$refs.btn,(p)=>{
                    this.src=p.path
                })
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
