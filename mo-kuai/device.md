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

```

### demo {#demo}

```javascript
var device=weex.requireModule('device')

var deviceId=device.deviceId();

var mac=device.mac();

env.tel('18088888888');


```



