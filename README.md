# AppleGuidelines

[苹果官方通用审核条款](https://developer.apple.com/cn/app-store/review/guidelines/)

## 苹果AppleSotre审核潜规则总结（针对中国区）

### 苹果审核指南：

### 通用条款

0、被拒分两种类型，第一种是元数据被拒(Meta Data)，第二种是(Binary Data)；元数据主要iTunes connect上的应用资料填写问题，Binary Data主要是提审的包存在问题

1、有账号体系则需要有不依赖第三方的登录注册功能

(Guideline 4.2.3 - Design - Minimum Functionality:
We were required to install QQ before we could use your app. Apps should be able to run on launch, without requiring additional apps to be installed.Next StepsTo resolve this issue, please revise your app to ensure that users can use it upon launch. If your app requires authentication before use, please use methods that can authenticate users from within your app.)

2、有账号体系则需有用户隐私协议

3、不可使用苹果私有API

(Guideline 3.3.1 - Applications may only use Documented APIs in manner prescribed by Apple and must not use or call any private APIs.)

4、不支持ipv6网络访问，美国地区需要支持iPv6，需把审核地区设置成中国即可

(Guideline 2.1 - Performance - App Completeness : We discovered one or more bugs in your app when reviewed on iPad running iOS 12.0.0 on Wi-Fi connected to an IPv6 network.)

5、版权问题，不要使用明显有版权争议的素材资源、如emoji、苹果logo、美国电影等 如：

[开发者注意 苹果禁止在App设计中使用emoji](https://www.feng.com/iPhone/news/2018-02-05/_696078.shtml)

[苹果审核版权与商标使用条款](https://www.apple.com/legal/intellectual-property/guidelinesfor3rdparties.html)

6、APP提审图iphoneX的介绍页需要有刘海

(Guideline 2.3.3 Performance - Accurate Metadata : Upon further review, your screenshot(s) for iPhone 5.8'' does not reflect the app in use on iPhoneX.)

7、审核人员大部分用iPad进行审核，APP需要在ipad里正常使用，（可能iPad成本便宜而且屏幕大）

(Guideline 2.4.1 - Performance - Hardware Compatibility : We noticed that your app did not run at iPhone resolution when reviewed on iPad running iOS 12.0.0. Please see attached screenshots for details.)

8、有账号体系需要提供审核账号

(Guideline 2.1 - Information Needed : We have started the review of your app, but we were unable to successfully register for an in-app account. In order for us to review your app, please provide a demo account so that we may fully assess your app's features.Specifically, we need a company name to log in.)

9、保护未成年用户隐私

10、APP如果有下载比较大的资源，需要告知提醒用户下载内容大小

11、如果没有定位、后台播放等功能，不可开通相关权限，收集用户隐私信息；如果需要后台持续开启定位功能，则需要说明开启后台定位功能的理由跟增加电池寿命声明：“后台定位会导致电池寿命减少”

(Guideline 2.16 - Multitasking Apps may only use background services for their intended purposes: VoIP, audio playback, location, task completion, local notifications, etc.

2.16 Details

Your app uses the Location Background mode but does not include the required "battery use" disclaimer in your Application Description.

Next Steps

Please add the following disclaimer to your Application Description:

"Continued use of GPS running in the background can dramatically decrease battery life."
Since your iTunes Connect Application State is Metadata Rejected, we do NOT require a new binary. To revise the metadata, visit iTunes Connect to select your app and revise the desired metadata values. Once you’ve completed all changes, click the “Submit for Review” button at the top of the App Information page.

NOTE: Please be sure to make any metadata changes to all App Localizations by selecting each specific localization and making appropriate changes.)
 
12、APP功能太少，会给苹果委婉拒绝并提示用网页开发

13、应用不可出现预敬请期待、发布、试验、测试、test、beta、trial等不稳定版本字眼

(Guideline 2.2 - Performance - Beta Testing : 
Your app appears to be a pre-release, test, or trial version with a limited feature set. Apps that are created for demonstration or trial purposes are not appropriate for the App Store.
Please see attached screenshots for details.
Next Steps
To resolve this issue, please complete, remove, or fully configure any partially implemented features. Additionally, remove all references to "demo," "trial," "beta," or "test" in your app description, app icon, screenshots, previews, release notes, and binary. )

14、APP内不可自己检测更新或引导下载第三方APP,APP如果做了检测更新应该引导用户跳到appstore进行更新

(Guideline 4.0 - Design : Your app includes an update button or alerts the user to update the app, but the update button or alert does not link directly to the app's page on the App Store.)

15、目前审核人员主要在iPad上进行审核，即使app不兼容iPad也要保证app的UI交互在iPad上能正常进行

(Guideline 2.4.1 - Performance - Hardware Compatibility
We noticed that your app did not run at iPhone resolution when reviewed on iPad running iOS 11.0.3. Please see attached screenshots for details.
Next Steps
To resolve this issue, please revise your app to ensure it runs as expected and displays properly at iPhone resolution on iPad. Even if your app was developed specifically for iPhone, users should still be able to use your app on iPad.)

16、要手机号验证码登录的APP，提审时，需要提供审核账号给审核人员，审核人员不会注册账号

17、提审的APP要有一定的功能，如果都是H5页面，苹果会拒绝，要求你要网页做

(Guideline 4.2.2 - Design - Minimum Functionality : We noticed that your app only includes links, images, or content aggregated from the Internet with limited or no native iOS functionality. Although this content may be curated from the web specifically for your users, since it does not sufficiently differ from a mobile web browsing experience, it is not appropriate for the App Store.)

(Guideline 4.2 - Design - Minimum Functionality : Thank you for your resubmission and making the changes. We found that the usefulness of your app is limited by the miniaml amount of content or features it includes. Specifically, your app only provides a code contest without other account-based or iOS user interactive features.)

18、需要用户开启相册、相机、定位等权限时，要在访问弹框里明确说明用途

(Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage : We noticed that your app requests the user's consent to access their camera but does not clarify the use of this feature in permission modal alert. It would be appropriate to elaborate on why your app is scanning QR code and taking pictures.)

19、App名字、关键词不能涵盖其他著名应用的信息

(Performance - 2.3.7 : your app name to be displayed on the App Store includes keywords or descriptore, whitch are not appropriate for use in an app name. Specifically, the following words in your app name are considered keywords or descriptors:)

20、信息缺失，导致审核人员有疑问的地方也会被拒

(Guideline 2.1 - Information Needed : We have started the review of your app, but we are not able to continue because we need additional information about your app.)

21、APP介绍页展示的功能要跟实际应用提供的功能一致

(Guideline 2.3.3 – Performance – Accurate Metadata :  We noticed that your screenshots do not sufficiently reflect your app in use.Please see attached screenshots for details.)

22、APP不可以必须使用邀请码才能注册

(Guideline 2.3 - Performance : Your app arbitrarily restrict users byrequiring invitation code to register, which is not allowed on the App Store.We’ve attached screenshot(s) for your reference.
Next Steps
Please revise your app to remove anyfunctionality that limits who can use the app.)

23、APP不可以必须使用邀请码、代码、私钥才能解锁某些功能，应该采用内购方式

(Guideline 3.1.1 - Business - Payments - In-App Purchase
Your app unlocks or enables additional functionality with mechanisms such as promo codes, data transfer codes, license keys, augmented reality markers, or QR codes, which is not appropriate for the App Store.
邀请码
Next Steps
To resolve this issue, please remove this feature from your app.)

24、可以使用户对App进行评论，但不允许诱导用户，比如语言、奖励诱导用户给好评。

错误：
1、亲，请给我们个五星好评呗～
2、写评论领钻石奖励

正确：
1、亲，请给我们个评价呗～
2、程序GG很幸苦，如果喜欢我们的话就去留个评价吧～

25、邀请好友的功能不能涉及数字内容的奖励，这是苹果不接受的商业模式，因为这样的功能可以绕过苹果的内购的规定。常见在邀请好友的运营功能上被拒。

(Guideline 3.2.2 - Business - Other Business Model Issues - Unacceptable : 
We noticed that your app incentivizes referrals in order to sign up new users. While rewarding the invitation sender with points or other digital content is acceptable, the person receiving the invitation should not receive any rewards for downloading or registering an account to use your app.

26、App名字那里不能增加使用副标题，如"-这个是副标题"，以前很多App这么使用，现在苹果增加了subtitle选项后就不给这么使用了。

(Guideline 2.3.7 - Performance - Accurate Metadata : Your app name or subtitle to be displayed on the App Store includes keywords or descriptors, which are not appropriate for use in these metadata items. Specifically, the following words in your app name or subtitle are considered keywords or descriptors.)

27、内购里，虚拟货币等消耗型项目需要使用App自己的用户系统id，非消耗型的项目就必须使用苹果的账户体系，使用uuid作为唯一识别码。

(Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage : 
We noticed that your app requires users to register with personal information to purchase non account-based in-app purchase products, whitch does not comply with the App Store Review Guidelines.)

28、存在内购功能，但内购功能不能直接使用"元"、“人民币”等真实货币的描述

(Guideline 1.1.6 - Safety - Objectionable Content : 
We noticed that your app's in-app purchase products are labeled as 元, which could confuse and mislead users into believing they are purchasing a real currency.
Next Steps:
to avoid potential user confusion, please revise your app so that your in-app purchase product names or labels are distinct from any real-world currencies.)

29、存在内购功能时，App提供的资料入网页、官网、等不能出现其他充值入口、内购政策、安卓等字眼。


### 社交类应用

1、图片社交、SNS、交友需要有拉黑举报功能

2、需要提供2个正常的审核账号
(Guideline 2.1 - Information Need : Provide an active demo account and login information, plus any other hardware or resources that might be needed to review your app (e.g. a sample QR code))

### 区块链应用

中国区

1、需要中心化的账号体系

### 金融类

1、理财类产品需要理财资质证明

2、名字跟开发者账号挂钩

### 彩票类

1、中国区彩票不给网上线上销售，动了别人的蛋糕

2、2018年多款彩票类应用直接不给更新

3、有抽奖、赌博的活动（凡APP涉及抽奖/比赛/彩票/赌博内容/奖品涉及苹果公司产品）需要限制年龄17+，并且声明活动跟苹果无关

(Guideline 5.3.2 - Legal - Gaming, Gambling, and Lotteries : Your app includes a contest or sweepstakes, but it does not indicate the Apple is not involved in any way with the contest or sweepstakes. Also. it does not enforce an app age rating of 17+.)

### 商城
1、APP商品如果是虚拟物品需要走苹果内购渠道

2、APP内的虚拟商品不可购买后在第三方APP上使用

3、APP商品如果是实物可走第三方支付渠道，如信用卡，微信、支付宝等支付渠道

### 游戏
中国区

1、需要游戏著作权、版号、网文号

2、网游针对未成年防沉迷系统

3、如果APP有博彩类游戏，一定要声明活动与苹果无关

(Guideline 5.3.2 - Legal - Gaming, Gambling, and Lotteries : Your app includes a contest or sweepstakes, but it does not indicate the Apple is not involved in any way with the contest or sweepstakes.)

### 马甲包制作

1、需要修改：账号，IP，名字，包名，方法名，类名，图片名，图片md5

(Guideline 4.3 - Design : We noticed that your app provides the same feature set as other apps submitted to the App Store; it simply varies in content or language, which is considered a form of spam.)

### 惩罚相关

1、苹果对黄赌毒 0容忍，一经过发现，立刻下架，并有可能封号

2、如刷榜、虚假评论、版权纠纷、欺诈行为、企业分发等行为给发现后会给封号

3、遇到苹果的警告邮件，应保持冷静，同时提交申诉邮件，不要转走应用，苹果能追查到

4、苹果最近的惩罚采用连带制度，如果一个账号加入多个企业组织，很容易因为一个账号被封导致其他账号也一起遭殃。最好一个apple id归属一个组织，同时提审时尽量用不同IP跟机器
