# looper

文字轮播器

### Demo

```js
<template>

        <div   >
            <div title="相机"  style="height:100px"  append="tree">

            </div>
           <looper ref="looper" font-size="25" @click="ok" :data="items"  color="#eeeeee"  style="width: 300;height: 100;background-color: #0088fb">

           </looper>
            <text>{{index}}</text>


            <div style="width: 200;height: 100;background-color: #006ce7" @click="getindex"></div>

        </div>




</template>

<style>
.cl
{

    align-items: center;

}


</style>
 
<script>

    var head =require('./header.vue')


    export default {
        components:{head},
        data () {
            return {
               src:"",
                index:0,
                items:['2017年11月9日，网络设计平台app','2017年11月9日，网络设计平台app','2017年11月9日，网络设计平台app','2017年11月9日，网络设计平台app','2017年11月9日，网络设计平台app']
            }
        },
        methods: {
            ok()
            {
                this.$refs.looper.getIndex((res)=>{

                    this.index=res.index;
                });

            },
            getindex()
            {
               this.$refs.looper.getIndex((res)=>{

                   this.index=res.index;
               });
            },
            onchange(res)
            {
                this.index=res.index;
            },

           
           




            var globalEvent = weex.requireModule('globalEvent') ;

            globalEvent.addEventListener("onPageInit", function (e) {
                const nav = weex.requireModule('navbar');
                nav.setTitle('照相');
                nav.setBack(true);
                nav.setRightImage('img/scan.png',function(res){

                    var modal = weex.requireModule('modal') ;
                    modal.alert({message:"ok"})
                });
            });

        }
    }
</script>
```



