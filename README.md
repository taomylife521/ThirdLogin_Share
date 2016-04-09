# ThirdLogin_Share


微信,qq,新浪微博的分享与登录集成

此项目仅供参考，之前的代码很烂，有时间会进行重构。


##配置

	//APPid
	public class Const {
	    public static final String QQ_APP_ID = "***";
	    public static final String WEI_CHAT_APP_ID = "***";
	    public static final String WEI_CHAT_APP_SECRET = "***";
	    public static final String SINA_APP_KEY = "***";


	//你的正式签名
 	signingConfigs {
        debug {
            keyAlias '***'
            keyPassword '***'
            storeFile file('***')
            storePassword '***'
        }
    }

}





##代码



		初始化AppID
	    ThirdDataProvieder.initQQ(Const.QQ_APP_ID);
        ThirdDataProvieder.initWechat(Const.WEI_CHAT_APP_ID, Const.WEI_CHAT_APP_SECRET);
        ThirdDataProvieder.initWeibo(Const.SINA_APP_KEY);
		
		mQqShareManager = new QQShareManager(this);
        mQqLoginManager = new QQLoginManager(this);
        mWeiChatShareManager = new WeiChatShareManager(this);
        mWeiChatLoginManager = new WeiChatLoginManager(this);
        mWeiboShareManager = new SinaShareManager(this);
        mWeiboLoginManager = new SinaLoginManager(this);

		//qq登录
		 mQqLoginManager.login(new QQLoginCallBack() {
            @Override
            public void onComplete(QQLoginInfo userInfo) {
                Log.d("MainActivity", "userInfo:" + userInfo);
            }

            @Override
            public void onError() {
                Log.d("MainActivity", "onError:");
            }

            @Override
            public void onCancel() {
                Log.d("MainActivity", "onCancel:");
            }
        });
		//qq分享
		    public void qqZoneShare(View view) {
		        qShare(QQShareManager.QZONE);
		
		    }
		
		    public void qqShare(View view) {
		
		        qShare(QQShareManager.QQ);
		
		    }

		//其他类似


## 截图

![](imgs/01.png)
![](imgs/02.png)
![](imgs/03.png)
![](imgs/04.png)
![](imgs/05.png)
![](imgs/06.png)
![](imgs/07.png)
![](imgs/08.png)
![](imgs/09.png)
![](imgs/10.png)
