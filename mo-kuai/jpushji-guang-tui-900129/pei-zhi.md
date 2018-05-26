# 配置

2端应用需要单独配置

你需要在config.json，填写notifyEntry 字段，此为接收通知的入口页面，请将逻辑写在该页面的onPageInit事件中

```js
<template>
    <div>


    </div>
</template>
<style>

</style>

<script>
    export default {

        data()
        {
            return {

            }
        },
        methods: {


        },
        created: function () {

            var globalEvent = weex.requireModule('globalEvent');
            globalEvent.addEventListener("onPageInit", function (param) {

                var t=weex.requireModule('modal')
                var navigator=weex.requireModule('navigator')
                //根据param变量实现自己的跳转逻辑
                navigator.pushParam('root:demo/onNotifyRecive.js',param)



            });

        },
    }
</script>
```



