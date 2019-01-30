# nim
云信聊天组件

##1.初始化
   根目录下依次执行
   
   ```
   weexplus plugin add NIMKit
   ```
   ```
    weexplus plugin add nim
   ```
   
##2.配置和使用 
   申请appkey
   [https://app.yunxin.163.com/index#/create]()
   ![](/assets/yunxin.png)
   获取到appkey之后使用appkey和appsecret在云信那注册账号
   以下为服务端注册代码（java）
   
   ```java
   
    public static void main(String[] args) throws Exception{
        DefaultHttpClient httpClient = new DefaultHttpClient();
        String url = "https://api.netease.im/nimserver/user/create.action";
        HttpPost httpPost = new HttpPost(url);

        String appKey = "你的appkey";
        String appSecret = "你的appSecret";
        String nonce =  "z11";
        String curTime = String.valueOf((new Date()).getTime() / 1000L);
        String checkSum = CheckSumBuilder.getCheckSum(appSecret, nonce ,curTime);//参考 计算CheckSum的java代码

        // 设置请求的header
        httpPost.addHeader("AppKey", appKey);
        httpPost.addHeader("Nonce", nonce);
        httpPost.addHeader("CurTime", curTime);
        httpPost.addHeader("CheckSum", checkSum);
        httpPost.addHeader("Content-Type", "application/x-www-form-urlencoded;charset=utf-8");

        // 设置请求的参数
        List<NameValuePair> nvps = new ArrayList<NameValuePair>();
        nvps.add(new BasicNameValuePair("accid", "336"));//这个就是云信的账户id，打开对话靠的就是这个336
        
        httpPost.setEntity(new UrlEncodedFormEntity(nvps, "utf-8"));

        // 执行请求
        HttpResponse response = httpClient.execute(httpPost);

        // 打印执行结果
        System.out.println(EntityUtils.toString(response.getEntity(), "utf-8"));
    }
   ```
   
   前端代码 打开某一用户的对话界面
   
   ```javascript 
   登录并打开对话界面
     gotoChart(item){
                let nim=weex.requireModule('nim')

                nim.regist({appKey:你的云信appkey})
                nim.login({account:accid,token:注册云信id后返回的token},(res)=>{
                    if(res.err==0){
                        nim.openP2P({account:目标用户的accid, navBarBgColor:'#000000',theme:'white'})
                    }else{
                        this.toast('云信登录失败！'+res.err)
                    }
                })
                
            }
   ```
   
   ```
   最近联系人列表
    nim.recent((items)=>{
                       
                    })
   ```
   ##api
   
```js

regist({appKey:你的云信appKey})

login({account:注册的云信id（accid), token:云信token})

recent((items)=>{
 //返回最近联系人列表
})

openP2P({account:目标用户的accid,navBarBgColor:标题栏背景颜色,theme:标题栏文字颜色('white','black'可选)})
```
  