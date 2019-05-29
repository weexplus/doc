
# weex-amap
<img width="320" src="https://img.alicdn.com/tps/TB19sYlPFXXXXaRaXXXXXXXXXXX-600-450.png" />


## 首次使用请执行:
 ```weexplus plugin add https://github.com/farwolf2010/amap```
申请完apiKey之后，请在按如下方式初始化
```
     <weex-amap style="flex: 1;background-color: red" :sdkKey="{ios:'05df62dbb56a7257048679f5618cb63d','android':'1edf8a80f0e423233c0b2db26398238b'}" :center="point.position" >
        </weex-amap>
```


### 快速开始

编辑你的weex文件

``` we
<template>
    <div style=" background-color: #00B4FF">
        <weex-amap style="flex: 1;background-color: red" :sdkKey="{ios:'05df62dbb56a7257048679f5618cb63d','android':'1edf8a80f0e423233c0b2db26398238b'}" :center="point.position" >
            <weex-amap-marker :position="point.position" :title="point.title"></weex-amap-marker>
        </weex-amap>
        <button @click="init"></button>
    </div>
</template>
<script>
    export default{
        data(){
            return {
                pos:[125.487, 40.00003],
                point: {
                    position: [112,36],
                    title: 'this is a marker'
                }
            }
        },
        props: {},
        methods: {


        },
        created(){
            this.init()
        }
    }
</script>
<style scoped>

</style>
```

### API

#### weex-amap 属性

| 属性        | 类型         | Demo  | 描述  |
| ------------- |:-------------:| -----:|----------:|
| sdkKey   | object | {ios:'xxx',android: 'xxx',h5: 'xxx'} | 指定开发者的 SDK 密匙 
| scale   | boolean | true | 设置比例尺功能是否可用 
| center     | array | [116.487, 40.00003] | 传入地理位置坐标[x,y] 默认为当前定位位置 |
| zoom      | number    |  合法值范围 [3,19] | 缩放级别 |
| compass      | boolean    |  true | 是否允许显示指南针 |
| zoomEnable | boolean  | true | 是否允许缩放
| marker |  array | [`{position:[116,12]}]` |  点标记物的属性
| geolocation  | boolean | true | 是否显示当前位置
| zoomPosition  | String | center|bottom | 设置缩放按钮的位置
| gestures  | String | ["zoom","rotate","tilt","scroll"] | 设置允许对地图做哪些手势操作
| myLocationEnabled  | boolean | true | 定位按钮是否显示
| showMyLocation  | boolean | true | 是否显示当前位置
| customEnabled  | boolean | true | 是否开启自定义地图样式
| setMapCustomEnable  | String | {"android":"/data/custom_map"} |设置自定义地图资源文件的路径
| indoorswitch  | boolean | false |设置室内地图楼层切换控件是否可见


**建议你前往[高德开发者社区](http://lbs.amap.com/)申明你对应产品的Key，保证地图正常工作**

#### weex-amap 事件    
**zoomchange**
用户缩放地图时触发该事件    
事件格式    
```json
{
  "targetCoordinate" : "缩放后的位置",
  "zoom" : "目标可视区域的缩放级别。",
  "tilt" : "目标可视区域的倾斜度，以角度为单位。",
  "bearing" : "可视区域指向的方向，以角度为单位，从正北向逆时针方向计算，从0 度到360 度。",
  "isAbroad" : "该位置是否在国内（此属性不是精确计算，不能用于边界区域）",
  "scalePerPixel" : "Weex中一像素对应实际距离的长度（单位米）",
  "visibleRegion" : "可视区域的范围"
}
```  
**dragend**    
用户拖动地图时触发该事件



#### weex-amap-marker 属性    

| 属性        | 类型         | Demo  | 描述  |
| ------------- |:-------------:| -----:|----------:|
| position     | array | [116.487, 40.00003] | 传入地理位置坐标[x,y] 默认为当前定位位置 |
| icon | string     |    some_icon_url | 图标的url地址 |
| title | string   |   'this is a marker' | 坐标点的名称 |
| hideCallout | boolean   |   true | 设置marker是否可点击 |
| open | boolean   |   true | 是否显示InfoWindow |

#### weex-amap-marker 事件
**click**    
点击marker时触发

#### weex-amap-info-window 属性    

| 属性        | 类型         | 描述  |
| ------------- |:-------------:| -----:|
| open     | boolean | 是否显示InfoWindow |
| position     | String | InfoWindow位置 |
| offset     | String | InfoWindow偏移量 |

#### weex-amap-circle 属性
| 属性        | 类型         | 描述  |
| ------------- |:-------------:| -----:|
| center     | String | 中心点 |
| strokeColor     | String | 描边颜色 |
| fillColor     | String | 填充颜色 |
| strokeWidth     | float | 描边宽度 |
| radius     | float | 半径 |

#### weex-amap-polygon 属性    

| 属性        | 类型         | 描述  |
| ------------- |:-------------:| -----:|
| path     | String | 路径 |
| strokeColor     | String | 描边颜色 |
| fillColor     | String | 填充颜色 |
| strokeWidth     | float | 描边宽度 |

#### weex-amap-polyline 属性    

| 属性        | 类型         | 描述  |
| ------------- |:-------------:| -----:|
| path     | String | 路径 |
| strokeColor     | String | 描边颜色 |
| strokeStyle     | String | 描边样式，可为dashed或空 |
| strokeWidth     | float | 描边宽度 |

#### Amap 模块

#####  getUserLocation(completeFunc,errorFunc)

+ completeFunc 定位成功后的回调函数，返回的数据:
```
{ 
  data:{
    position: []
  },
  result: 'success' 
}
```

#####  getLineDistance(posA, posB, callback)

+ 获取两点间的直线距离

#####  polygonContainsMarker(position, id, callback)

+ 判断点是否在合围范围内

 

一款高德地图weex插件，当前版本支持定位，缩放等地图常用操作。   

请配合[高德地图开发文档](http://lbs.amap.com/api/android-sdk/summary/)使用该插件    
<img src="https://img.alicdn.com/tps/TB1c5BKQXXXXXckXpXXXXXXXXXX-367-633.gif "> 



### 集成插件

如何将地图插件集成到自己的项目呢，请参考[weexpack文档说明](https://github.com/weexteam/weex-pack/tree/dev#5现有应用集成插件--组件容器)
