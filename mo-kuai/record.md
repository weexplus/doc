# record

录音组件
首次使用请先执行：weexplus plugin add https://github.com/farwolf2010/record

### API


```
   /**
     * 开始
     * @param param  {channel:'mono',quality:'low','high'}

      */
    show(param)


    /**
    *暂停
    */
     pause()
     
      /**
    *停止
    */
     stop(callback)
```

### DEMO

``` javascript
 <template>
    <div style="align-items: center;justify-content: center">
        <video style="width: 500px;height: 300px;background-color: red" auto-play="true" :src="src"></video>
        <button @click="start" text="start" style="margin-top: 20px"></button>
        <button @click="pause" text="pause" style="margin-top: 20px"></button>
        <button @click="stop" text="stop" style="margin-top: 20px"></button>
        <text>{{text}}</text>
    </div>
</template>
<script>
    export default{
        props: {},
        data () {
            return {
                text:'',
                src:''
            }
        },
        methods: {
            onLoad(){

            },
            start(){

//                    let audio=weex.requireModule('audio')
//                    audio.play('http://192.168.0.102:8890/js/1.wav')
//                return
                let record=weex.requireModule('record')
                record.start({channel:'mono',quality:'high'})
            },
            pause(){
                let record=weex.requireModule('record')
                record.pause()
            },
            stop(){
                let record=weex.requireModule('record')
                record.stop((res)=>{
                    this.text=res
                    this.src=res.path
//                    this.upload(this.src)
//                   let audio=weex.requireModule('audio')
//                    audio.play(this.src)
                })
            },
            upload(pathx){
                var param={};
                var header={
                };
                var path={};
                path.file=pathx;
                var net=weex.requireModule("net");
                var process=weex.requireModule("process");
                net.postFile('http://59.110.169.246/movie/imgupload.do',param,header,path,()=>{
                    //start
//                        process.show()
                },(e)=>{
                    //succcess
                    var modal=weex.requireModule("modal")
                    modal.toast({message:'上传成功！'})
                },()=>{
                    //compelete
//                        process.dismiss()
                },()=>{
                    //exception
                    var modal=weex.requireModule("modal")
                    modal.toast({message:'上传异常！'})
                })
            }
        },
        mounted () {

        },
        created () {

        }
    }
</script>
<style scoped>
</style>

```