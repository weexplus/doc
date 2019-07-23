#sysShare
**首次使用请执行```weexplus plugin add https://github.com/farwolf2010/sysShare```**

调用系统分享功能，可以分享到微信，优点是不用去微信审核
##api
```
/**
**  param: {type:('txt','image'),content:'连接地址或图片路径'}
**/
share(param)
```

##demo
```
<template>
    <div ref="root" style="align-items: center;justify-content: center">

        <button ref="btn" text="分享链接" @click="shareText"></button>
        <button ref="btn" text="分享图片" @click="shareImage"></button>

    </div>
</template>
<script>
    export default{
        data(){
            return {}
        },
        props: {},
        methods: {
            shareText(){
                let sys=weex.requireModule('sysShare')
//                sys.share({type:'image',image:'http://www.pc-fly.com/uploads/allimg/160416/1U05E217_1.jpg'})
                sys.share({type:'txt',content:'http://share.atoxchain.io/#/h5/invite.js/thomasxing'})
            },
            shareImage(){
                const photo = weex.requireModule('photo');
                photo.openPhoto(500,800,'#000000','#ffffff','#ffffff',(e)=>{
                    let sys=weex.requireModule('sysShare')
                    sys.share({type:'image',image:e.path})

                });
//                let sys=weex.requireModule('sysShare')
//                sys.share({type:'image',image:'http://www.pc-fly.com/uploads/allimg/160416/1U05E217_1.jpg'})
//                sys.share({type:'txt',content:'http://share.atoxchain.io/#/h5/invite.js/thomasxing'})
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
