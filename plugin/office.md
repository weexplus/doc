#audio
首次使用```weexplus plugin add https://github.com/farwolf2010/office ```
### api

 

#demo

```
<template>
    <div style="align-items: center;justify-content: center">
       <div  style="width: 700px;height: 1100px;background-color: #eeeeee">
           <office style="flex: 1" :src="src">
           </office>
       </div>
        <div style="flex-direction: row" >
            <button text="加载http" @click="loadhttp"></button>
            <button text="加载本地" @click="loadlocal"></button>
        </div>
    </div>
</template>
<script>
    export default{
        props: {},
        data(){
            return {
                src:''
            }
        },
        methods: {
            loadhttp(){

              this.src=  'http://59.110.169.246/img/1.docx'
            },
            loadlocal(){
                let url='http://59.110.169.246/img/book.pdf'
                let net=weex.requireModule('net')
                net.download(url,(res)=>{
                    this.log(res)
                },(res)=>{
                    this.log(res)
                    this.src=res.path
                },()=>{

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