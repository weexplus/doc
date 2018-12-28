# device

设备信息

### api {#api}

```
//获取设备唯一标志（ios获取的是uuid，有可能在刷机后改变）
 deviceId()



//获取wifi mac
mac()



//打电话
tel(phone)


//开启浏览器打开一个地址
openUrl(phone)

```

### demo {#demo}

```javascript
var device=weex.requireModule('device')

var deviceId=device.deviceId();

var mac=device.mac();

device.tel('18088888888');

device.openUrl('https://wwww.baidu.com');

```



