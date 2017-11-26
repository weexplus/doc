# photo

用于获取拍照和相册读取照片

### API

```js
默认的选择器，包含了相册和相机入口

/**
* @param width 照片宽度
* @param height 照片高度
* @param themeColor 相册选择页的背景色
* @param titleColor 相册选择页的标题文字颜色
* @param cancelColor 相册选择页的取消文字颜色
* @param callback 回调，返回图片地址
*/
open( width, height , themeColor, titleColor,  cancelColor,  callback)

单独打开相册
/**
* @param width 照片宽度
* @param height 照片高度
* @param themeColor 相册选择页的背景色
* @param titleColor 相册选择页的标题文字颜色
* @param cancelColor 相册选择页的取消文字颜色
* @param callback 回调，返回图片地址
*/
 openPhoto(  width,  height,  themeColor,  titleColor,cancelColor, callback )

单独打开相机
/**
 * 
 * @param width 照片宽度
 * @param height 照片高度
 * @param themeColor 选择页的主题色
 * @param callback 回调，返回图片地址
 */
  openCamera( width, height, themeColor,  callback )
```

## Demo

```js
一般这个组件都是配合上传一起使用


 openPhoto()
    {
        var self=this;
        const photo = weex.requireModule('photo');
        photo.openPhoto(500,800,'#000000','#ffffff','#ffffff',function(e){
    
            self.src=e.path;
            var param={};
            var header={};
            var path={};
            var net=weex.requireModule("net");
            net.postFile('http://xxx/upload',{//param
    
            },{
                // header
            },{         
               file:e.path},()=>{
                //start
            },(e)=>{
                //succcess
                var modal=weex.requireModule("modal")
                modal.toast({message:'上传成功！'})
            },()=>{
                //compelete
    
            },()=>{
                //exception
                var modal=weex.requireModule("modal")
                modal.toast({message:'上传异常！'})
            })
    
        });
    },
```



