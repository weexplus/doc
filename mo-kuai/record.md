# record

录音组件
首次使用请先执行：weexplus plugin add record

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
                text:''
            }
        },
        methods: {
            onLoad(){

            },
            start(){
                let record=weex.requireModule('record')
                record.start({channel:'mono',quality:'low'})
            },
            pause(){
                let record=weex.requireModule('record')
                record.pause()
            },
            stop(){
                let record=weex.requireModule('record')
                record.stop((res)=>{
                    this.text=res
                })
            },
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