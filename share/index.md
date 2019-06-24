#分享
**首次使用请执行weexplus plugin add https://github.com/farwolf2010/umshare**

该分享为友盟分享，包含微信，qq，微博



配置步骤
1.请先在友盟申请appkey

```javascript
let umshare=weex.requireModule('umshare')
umshare.initUM({appkey:'你的友盟appkey',channel:'自己定义的渠道号')
//初始化微信
 umshare.initWechat({appkey:'微信appkey',appSecret:'微信appSecret')
 
 //初始化QQ
 umshare.initQQ({appkey:'QQappkey',appSecret:'QQ appSecret')
 
 //初始化新浪微博
 umshare.initSina({appkey:'新浪微博appkey',appSecret:'新浪微博appSecret',redirectUrl:'自己的回调网站')
 
 //调用分2种，可以用友盟自己的分享面板，或者自定义面板，单个分享
 
 //调用友盟分享面板
  umshare.openShareBox({platforms:['wechat-chat','wechat-timeline','qq','sina'],title:'标题',content:'内容',shareType:'类型（text，image，textimage，music，video，miniProgram）',url:'图片，音乐，视频，地址',path:'小程序地址',userName:'小程序username'})
 
 //自己设置个button，单个分享
 umshare.share({platform:'分享平台'（如下值中选一个：'wechat-chat','wechat-timeline','qq','sina'）,title:'标题',content:'内容',shareType:'类型（text，image，textimage，music，video，miniProgram）',url:'图片，音乐，视频，地址',path:'小程序地址',userName:'小程序username'})
 
 
 
 
 
 

```


