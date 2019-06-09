# zoomImage\(图片查看器\)

放大查看图片
以插件形式提供
使用前请先 weexplus plugin add https://github.com/farwolf2010/zoomImage

### api

```javascript

/**param {index:0 初始化的位置，list:图片地址数组}
show(param)



```

### demo

```javascript
var zm=weex.requireModule('zoomImage')
let ary=[]
ary.push('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1547129965&di=c2fa406bcdbf7936cc44c45fc5087ea6&imgtype=jpg&er=1&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2Fb3119313b07eca807f814fc39b2397dda1448309.jpg')
ary.push('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1546535255449&di=995c494131e42718f4def87b09544598&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2F0b46f21fbe096b63b44a91cd06338744eaf8acd8.jpg')
ary.push('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1546535255449&di=8a21adb89f3a4eb8faf5a9bb3557f260&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2Fd1a20cf431adcbef1da6b62ba7af2edda3cc9f09.jpg')
let p={}
p.index=0
p.list=ary
zm.show(p)
```