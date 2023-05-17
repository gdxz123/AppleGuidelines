# AppleGuidelines

[苹果官方通用审核条款](https://developer.apple.com/cn/app-store/review/guidelines/)

## 苹果AppleSotre审核潜规则总结（针对中国区）

### 苹果审核指南：

### 通用条款

- 被拒分两种类型，第一种是元数据被拒(Meta Data)，第二种是(Binary Data)；元数据主要iTunes connect上的应用资料填写问题，Binary Data主要是提审的包存在问题

- 有账号体系则需要有不依赖第三方的登录注册功能，目前要求有账号登录功能则一定要接入提供sigin with apple，且设计logo 文案都需要按照官方要求，这是为了保护用户数据隐私

```
Guideline 4.2.3 - Design - Minimum Functionality

We were required to install QQ before we could use your app. Apps should be able to run on launch, without requiring additional apps to be installed.Next StepsTo resolve this issue, please revise your app to ensure that users can use it upon launch. If your app requires authentication before use, please use methods that can authenticate users from within your app.

翻译:
我们必须先安装QQ，然后才能使用您的应用程序。应用程序应该能够在启动时运行，而不需要安装其他应用程序。下一步要解决此问题，请修改您的应用程序，以确保用户可以在启动时使用它。如果您的应用程序在使用前需要进行身份验证，请使用可以在应用程序中对用户进行身份验证的方法。(目前有账号登录功能都一定要接入提供sigin with apple)
```

- 有账号体系则需有用户隐私协议

- 不可使用苹果私有API，苹果私有API有工具可以进行代码检测。
```
Guideline 3.3.1

Applications may only use Documented APIs in manner prescribed by Apple and must not use or call any private APIs.

翻译:
应用程序只能按照苹果公司规定的方式使用文档化API，不得使用或调用任何私有API。
```

- 不支持ipv6网络访问，美国地区需要支持IPv6，需把审核地区设置成中国即可，这样审核会不要求IPV6，应该是因为IPV6在美国覆盖率很高，审核人员的网络可能就是IPV6，导致他体验不了APP，所以要求APP在IPV6覆盖率高的国家上架时要求支持，但中国地区不强制要求。
```
Guideline 2.1 - Performance - App Completeness

We discovered one or more bugs in your app when reviewed on iPad running iOS 12.0.0 on Wi-Fi connected to an IPv6 network.

翻译:
当我们在连接到IPv6网络的Wi-Fi上运行iOS 12.0.0的iPad上进行审查时，发现您的应用程序中有一个或多个错误。
```

- 版权问题，不要使用明显有版权争议的素材资源、如emoji、苹果logo、美国电影等 如：

[开发者注意 苹果禁止在App设计中使用emoji](https://www.feng.com/iPhone/news/2018-02-05/_696078.shtml)

[苹果审核版权与商标使用条款](https://www.apple.com/legal/intellectual-property/guidelinesfor3rdparties.html)

- APP提审图5.8寸的介绍页需要有刘海屏的设计
```
Guideline 2.3.3 - Performance - Accurate Metadata

Upon further review, your screenshot(s) for iPhone 5.8'' does not reflect the app in use on iPhoneX.

翻译:
经进一步审查，您的iPhone 5.8寸的屏幕截图并未反映是在iPhone X上正在使用的应用程序，一般就是刘海屏需要展示出来。
```
- 审核人员大部分用iPad进行审核，APP需要在ipad里正常使用，（可能iPad成本便宜而且屏幕大）
```
Guideline 2.4.1 - Performance - Hardware Compatibility

We noticed that your app did not run at iPhone resolution when reviewed on iPad running iOS 12.0.0. Please see attached screenshots for details.

翻译:
我们注意到，在运行iOS 12.0.0的iPad上查看时，您的应用程序没有以iPhone分辨率运行。有关详细信息，请参阅所附的屏幕截图。
```
- 有账号体系需要提供审核账号
```
Guideline 2.1 - Information Needed

We have started the review of your app, but we were unable to successfully register for an in-app account. In order for us to review your app, please provide a demo account so that we may fully assess your app's features.Specifically, we need a company name to log in.

翻译:
我们已开始审核您的应用，但无法成功注册应用内帐户。为了便于我们审核您的应用，请提供一个审核账户，以便我们全面评估您应用的功能。具体来说，你的应用需要一个公司名称才能登录(但是我们没有)。
```
- 保护未成年用户隐私，注意儿童隐私，在没有“家长明确同意”的情况下，禁止应用收集13岁以下儿童的个人资料

- 用户隐私数据收集弹框出现时，需要先调用App Tracking Transparency

  ```
  Guideline 5.1.2 - Legal - Privacy - Data Use and Sharing
  
  The app privacy information you provided in App Store Connect indicates you collect data in order to track the user, including Emails or Text Messages, User ID, Purchase History, Phone Number, Precise Location, Email Address, Name, and Coarse Location. However, you do not use App Tracking Transparency to request the user's permission before tracking their activity.
  Starting with iOS 14.5, apps on the App Store need to receive the user’s permission through the AppTrackingTransparency framework before collecting data used to track them. This requirement protects the privacy of App Store users.
  Next Steps
  Here are two ways to resolve this issue:
  - If you do not currently track, or decide to stop tracking, update your app privacy information in App Store Connect. You must have the Account Holder or Admin role to update app privacy information.
  - If you track users, you must implement App Tracking Transparency and request permission before collecting data used to track. When you resubmit, indicate in the Review Notes where the permission request is located.
  
  翻译：
  您在 App Store Connect 中提供的应用程序隐私信息表明您收集数据以跟踪用户，包括电子邮件或短信、用户 ID、购买历史、电话号码、精确位置、电子邮件地址、姓名和粗略位置。但是，在跟踪用户的活动之前，您不会使用 App Tracking Transparency 来请求用户的许可。
  从 iOS 14.5 开始，App Store 上的应用程序在收集用于跟踪它们的数据之前需要通过 AppTrackingTransparency 框架获得用户的许可。此要求保护 App Store 用户的隐私。
  下一步
  以下是解决此问题的两种方法：
  - 如果您当前不跟踪或决定停止跟踪，请在 App Store Connect 中更新您的应用程序隐私信息。您必须具有帐户持有人或管理员角色才能更新应用隐私信息。
  - 如果您跟踪用户，则必须实施 App Tracking Transparency 并在收集用于跟踪的数据之前请求许可。当您重新提交时，请在审查说明中指明权限请求所在的位置
  ```

  

- APP如果有下载比较大的资源，需要提前告知提醒用户下载内容大小

- 如果没有定位、后台播放等功能，不可开通相关权限，收集用户隐私信息；如果需要后台持续开启定位功能，则需要说明开启后台定位功能的理由跟增加电池寿命声明：“后台定位会导致电池寿命减少”
```
Guideline 2.16 
Multitasking Apps may only use background services for their intended purposes: VoIP, audio playback, location, task completion, local notifications, etc.

2.16 Details

Your app uses the Location Background mode but does not include the required "battery use" disclaimer in your Application Description.

翻译:
您的应用程序使用 Location Background 模式，但未在您的应用程序描述中包含所需的“电池使用”免责声明。

Next Steps

Please add the following disclaimer to your Application Description:

"Continued use of GPS running in the background can dramatically decrease battery life."
Since your iTunes Connect Application State is Metadata Rejected, we do NOT require a new binary. To revise the metadata, visit iTunes Connect to select your app and revise the desired metadata values. Once you’ve completed all changes, click the “Submit for Review” button at the top of the App Information page.

NOTE: Please be sure to make any metadata changes to all App Localizations by selecting each specific localization and making appropriate changes.) 
```

- APP功能太少，会给苹果委婉拒绝并提示用网页开发，解决方案是加入手机原生硬件相关功能，增大需要上APP的说服力，如相机来扫一扫，手机相册读取照片，等等
```
Guideline 4.2.2 - Design - Minimum Functionality
We noticed that your app only includes links, images, or content aggregated from the Internet with limited or no native iOS functionality. Although this content may be curated from the web specifically for your users, since it does not sufficiently differ from a mobile web browsing experience, it is not appropriate for the App Store.

翻译:
我们注意到您的应用程序仅包含从 Internet 聚合的链接、图像或内容，并且本地 iOS 功能有限或没有。尽管此内容可能是专门为您的用户从网络上精选出来的，但由于它与移动网络浏览体验没有太大区别，因此不适合 App Store。
```

- 应用不可出现预敬请期待、发布、试验、测试、test、beta、trial等不稳定版本字眼
```
Guideline 2.2 - Performance - Beta Testing

Your app appears to be a pre-release, test, or trial version with a limited feature set. Apps that are created for demonstration or trial purposes are not appropriate for the App Store.
Please see attached screenshots for details.
Next Steps
To resolve this issue, please complete, remove, or fully configure any partially implemented features. Additionally, remove all references to "demo," "trial," "beta," or "test" in your app description, app icon, screenshots, previews, release notes, and binary. 

翻译: 
您的应用程序似乎是预发布、测试或试用版，具有有限的功能集。为演示或试用目的创建的应用程序不适合应用商店。
有关详细信息，请参阅所附的屏幕截图。
接下来的步骤
若要解决此问题，请完成、删除或完全配置任何部分实现的功能。此外，请删除应用程序描述、应用程序图标、屏幕截图、预览、发布说明和二进制文件中对“演示”、“demo”、“试用版”、“trial”、“测试版”、“beta”、“test”或“测试”的所有引用。
```

- APP内不可自己检测更新或引导下载第三方APP，APP如果做了检测更新应该引导用户跳到App Store进行更新
```
Guideline 4.0 - Design

Your app includes an update button or alerts the user to update the app, but the update button or alert does not link directly to the app's page on the App Store.

翻译: 
您的应用包含更新按钮或提醒用户更新应用，但更新按钮或提醒并未直接链接到 App Store 中应用的页面。
```

- 目前审核人员主要在iPad上进行审核，即使app不兼容iPad也要保证app的UI交互在iPad上能正常进行
```
Guideline 2.4.1 - Performance - Hardware Compatibility

We noticed that your app did not run at iPhone resolution when reviewed on iPad running iOS 11.0.3. Please see attached screenshots for details.
Next Steps
To resolve this issue, please revise your app to ensure it runs as expected and displays properly at iPhone resolution on iPad. Even if your app was developed specifically for iPhone, users should still be able to use your app on iPad.)

翻译:
我们注意到，在运行 iOS 11.0.3 的 iPad 上审核时，您的应用程序无法以 iPhone 分辨率运行。有关详细信息，请参阅随附的屏幕截图。
```

- 要手机号验证码登录的APP，提审时，需要提供审核账号给审核人员，审核人员不会走注册账号的流程，避免审核人员信息泄漏

- 提审的APP要有一定的功能，如果都是H5页面，苹果会拒绝，要求你要网页做
```
Guideline 4.2.2 - Design - Minimum Functionality : 

We noticed that your app only includes links, images, or content aggregated from the Internet with limited or no native iOS functionality. Although this content may be curated from the web specifically for your users, since it does not sufficiently differ from a mobile web browsing experience, it is not appropriate for the App Store.

翻译: 
我们注意到，您的应用程序只包括链接、图像或从互联网聚合的内容，并且本地iOS功能有限或没有。尽管这些内容可能是专门为您的用户从网络上策划的，但由于它与移动网络浏览体验没有足够的区别，因此这个软件不适合App Stroe。

Guideline 4.2 - Design - Minimum Functionality 

Thank you for your resubmission and making the changes. We found that the usefulness of your app is limited by the miniaml amount of content or features it includes. Specifically, your app only provides a code contest without other account-based or iOS user interactive features.)

翻译: 
感谢您重新提交并做出更改。我们发现，您的应用程序的有用性受到其包含的内容或功能的微小数量的限制。具体来说，您的应用程序只提供代码竞赛，没有其他基于帐户系统或iOS用户交互功能。
```

- 存在功能的开关被发现，需要移除开关，或者修改代码变得更加隐秘，建议先移除开关，再慢慢加上
```
Specifically, this app still includes a network call which causes it to behave differently during review.  It would be appropriate to remove any review check related content found in the network traffic to ensure that all features and functions in the app are visible and fully accessible during review.

翻译:
具体来说，这个应用仍然包括一个网络请求调用来导致它在审核过程中表现不同。你最好删除这个网络请求调用和相关内容来保证APP的功能全都可见，并且可以完全访问。
```

- 需要用户开启相册、相机、定位等权限时，要在访问弹框里明确说明用途
```
Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage

We noticed that your app requests the user's consent to access their camera but does not clarify the use of this feature in permission modal alert. It would be appropriate to elaborate on why your app is scanning QR code and taking pictures.)

翻译: 
我们注意到您的应用程序请求用户同意访问他们的相机，但没有在权限模式警报中阐明此功能的使用。详细说明您的应用扫描二维码和拍照的原因是合适的。
```

- App名字、关键词不能涵盖其他著名应用的信息
```
Performance - 2.3.7

your app name to be displayed on the App Store includes keywords or descriptore, whitch are not appropriate for use in an app name. Specifically, the following words in your app name are considered keywords or descriptors: xxxxxxxx


翻译:
您要在 App Store 上显示的应用程序名称包含不适合在应用程序名称中使用的关键字或描述符。具体来说，您应用名称中的以下词被视为关键字或描述符: xxxxxxxx
```

- 信息缺失，导致审核人员有疑问的地方也会被拒，一般是用法的说明，我一般是画流程图跟录视频传到youtube回复他们。
```
Guideline 2.1 - Information Needed

We have started the review of your app, but we are not able to continue because we need additional information about your app.

翻译: 
我们已开始审核您的应用，但无法继续，因为我们需要有关您应用的更多信息。（苹果会列出需要提供什么信息）
```

- APP介绍页展示的功能要跟实际应用提供的功能一致
```
Guideline 2.3.3 – Performance – Accurate Metadata 

We noticed that your screenshots do not sufficiently reflect your app in use.Please see attached screenshots for details.

翻译: 
我们注意到您的屏幕截图不足以反映您正在使用的应用程序。有关详细信息，请参阅随附的屏幕截图。
```

- APP不可以必须使用邀请码才能注册，苹果要求App Store供应的APP是面向大众的。
```
Guideline 2.3 - Performance

Your app arbitrarily restrict users byrequiring invitation code to register, which is not allowed on the App Store.We’ve attached screenshot(s) for your reference.
Next Steps
Please revise your app to remove anyfunctionality that limits who can use the app.

翻译: 
您的应用程序通过要求邀请码注册来任意限制用户，这在应用程序商店是不允许的。我们附上截图供您参考。
下一步
请修改您的应用程序以删除任何限制谁可以使用该应用程序的功能。
```

- APP不可以必须使用邀请码、代码、私钥才能解锁某些功能，应该采用内购方式
```
Guideline 3.1.1 - Business - Payments - In-App Purchase

Your app unlocks or enables additional functionality with mechanisms such as promo codes, data transfer codes, license keys, augmented reality markers, or QR codes, which is not appropriate for the App Store.
邀请码
Next Steps
To resolve this issue, please remove this feature from your app.

翻译:
您的应用通过促销代码、数据传输代码、许可证密钥、增强现实标记或二维码等机制解锁或启用附加功能，这些机制不适用于 App Store。
邀请码
下一步
要解决此问题，请从您的应用中删除此功能。
```

- 可以使用户对App进行评论，但不允许诱导用户，比如语言、奖励诱导用户给好评。

错误：
1、亲，请给我们个五星好评呗～
2、写评论领钻石奖励

正确：
1、亲，请给我们个评价呗～
2、程序GG很幸苦，如果喜欢我们的话就去留个评价吧～


- 代码如果出现itms-services可能会触发2.5.2拒绝条款，因为审核人员怀疑你引导用户下载企业包
```
Guideline 2.5.2 - Performance - Software Requirements

During review, your app installed or launched executable code, which is not permitted on the App Store. Specifically, your app uses the itms-services URL scheme to install an app.

翻译: 
在审核期间，您的应用安装或启动了可执行代码，这是 App Store 不允许的。具体来说，您的应用程序使用 itms-services URL scheme来安装应用程序。(P.S: itms-services url scheme是安装企业包的技术)
```

- 邀请好友的功能不能涉及数字内容的奖励，这是苹果不接受的商业模式，因为这样的功能可以绕过苹果的内购的规定，而且容易用来刷榜。常见在邀请好友的运营功能上被拒。
```
Guideline 3.2.2 - Business - Other Business Model Issues - Unacceptable

We noticed that your app incentivizes referrals in order to sign up new users. While rewarding the invitation sender with points or other digital content is acceptable, the person receiving the invitation should not receive any rewards for downloading or registering an account to use your app.)

翻译: 
我们注意到您的应用会鼓励推荐以注册新用户。虽然用积分或其他数字内容奖励邀请发送者是可以接受的，但收到邀请的人不应因下载或注册帐户以使用您的应用程序而获得任何奖励。
```

- App名字那里不能增加使用副标题，如"-这个是副标题"，以前很多App这么使用，现在苹果增加了subtitle选项后就不给这么使用了。
```
Guideline 2.3.7 - Performance - Accurate Metadata

Your app name or subtitle to be displayed on the App Store includes keywords or descriptors, which are not appropriate for use in these metadata items. Specifically, the following words in your app name or subtitle are considered keywords or descriptors.

翻译: 
您要在 App Store 上显示的应用程序名称或副标题包含不适合在这些元数据项中使用的关键字或描述符。具体来说，您应用名称或副标题中的以下词被视为关键字或描述符
```

- 内购里，虚拟货币等消耗型项目需要使用App自己的用户系统id，非消耗型的项目就必须使用苹果的账户体系，使用uuid作为唯一识别码。
```
Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage

We noticed that your app requires users to register with personal information to purchase non account-based in-app purchase products, whitch does not comply with the App Store Review Guidelines.

翻译:
我们注意到，您的应用需要用户注册个人信息才能购买非账号内购商品，不符合《应用商店审核指南》。
```

- 存在内购功能，但内购功能不能直接使用"元"、“人民币”等真实货币的描述
```
Guideline 1.1.6 - Safety - Objectionable Content

We noticed that your app's in-app purchase products are labeled as 元, which could confuse and mislead users into believing they are purchasing a real currency.
Next Steps:
to avoid potential user confusion, please revise your app so that your in-app purchase product names or labels are distinct from any real-world currencies.

翻译: 
我们注意到您的应用程序的应用内购买产品被标记为元，这可能会混淆和误导用户，让他们相信他们购买的是真实货币。
下一步：
为避免潜在的用户混淆，请修改您的应用，使您的应用内购买产品名称或标签与任何现实世界的货币不同。
```

- 存在内购功能时，App提供的资料入网页、官网、等不能出现其他充值入口、内购政策、安卓等字眼。

- 企业包的打包脚本不能放到项目工程里，苹果识别到企业包的打包脚本会怀疑App是否对外分发

- App设计中展现的素材不应该有版权风险，典型的例子是使用微软雅黑字体，导致被字体公司告，会使App面临下架封号处理。https://baijiahao.baidu.com/s?id=1580761271561083959&wfr=spider&for=pc

- 1.3.4 违反政策通知：隐藏功能，移除隐藏的功能，过审了再慢慢加回
```
2. 3.1 - Hidden or undocumented features
3. 1.1 - In-App Purchase
Performance - 2.3.1 & Business - 3.1.1

Your app contains hidden features that enable users to purchase content by means other than in-app purchase API.

翻译:
您的应用包含隐藏功能，使用户能够通过应用内购买 API 以外的方式购买内容。
```

- 设计相关
```
Guideline 4.0 - Design:

We noticed an issue in your app that contributes to a lower quality user experience than Apple users expect:
- Your app and it's metadata has not been fully localized for its intended markets.

翻译:
我们注意到您的应用程序中存在导致用户体验质量低于 Apple 用户预期的问题：
- 您的应用及其元数据尚未针对其目标市场进行完全语言本地化。（就是没有提供上架市场的语言版本）
```

```
Guideline 4.3 - Design :

We noticed that your app icon is identical to the icons of other apps already submitted to the App Store.
Apps that use the same icon make it difficult for users to find apps and are considered a form of spam.
Next Steps
To resolve this issue, please revise your app icon to ensure it is unique and does not duplicate the icon of another app.
Please see attached screenshot for details.

翻译:
我们注意到您的应用程序图标与已提交到 App Store 的其他应用程序的图标相同。
使用相同图标的应用程序使用户难以找到应用程序，并被视为一种垃圾邮件。
下一步
要解决此问题，请修改您的应用程序图标以确保它是唯一的并且不会与其他应用程序的图标重复。
```
指责APP Icon存在抄袭，让换一个新的Icon。但是APP Icon是自己设计的，应该是被别的APP抄袭，所以回复Icon是自己设计的，并提供Icon文件的生成日期截图。第二天苹果回复
```
Hello,
Thank you for providing this information. 
We will continue the review, and will notify you if there are any further issues.
Best regards,
App Store Review
```
APP审核通过，并发布上线


- 准确元数据
```
Guideline 2.3.7 - Performance - Accurate Metadata

We noticed that your screenshots do not sufficiently reflect your app in use.
Specifically, your 6.5-inch iPhone screenshots do not display the app in the correct device frame.
Next Steps
To resolve this issue, please revise your screenshots to ensure that they accurately reflect the app in use on the supported devices. For iPhone, you need a set of 5.5-inch display screenshots and for iPad, you need a set for 12.9-inch display. This set will be scaled appropriately down to other device sizes when viewed on the App Store in each territory.
Note that 6.5-inch display assets for iPhone XS Max are optional, and can scale down to iPhone XR, iPhone XS, and iPhone X. Screenshots that include features like rounded corners or sensor housing should only be used for the 6.5-inch or 5.8-inch display.

翻译:
我们注意到您的屏幕截图不足以反映您正在使用的应用程序。
具体来说，您的 6.5 英寸 iPhone 屏幕截图未在正确的设备框架中显示该应用程序。
下一步
要解决此问题，请修改您的屏幕截图以确保它们准确反映在支持的设备上使用的应用程序。对于 iPhone，您需要一套 5.5 英寸显示屏的屏幕截图，对于 iPad，您需要一套用于 12.9 英寸显示屏的屏幕截图。在每个地区的 App Store 上查看时，此集合将适当缩小以适应其他设备尺寸。
请注意，iPhone XS Max 的 6.5 英寸显示屏资产是可选的，可以缩小到 iPhone XR、iPhone XS 和 iPhone X。包含圆角或传感器外壳等功能的屏幕截图只能用于 6.5 英寸或 5.8 英寸英寸显示屏。
```

```
Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage

We noticed that your app requests the user’s consent to access their photos but does not clarify the use of the photos in the applicable purpose string.

翻译:
我们注意到您的应用程序请求用户同意访问他们的照片，但没有在适用的目的字符串中阐明照片的用途。
```

APP需要使用权限时，需要说明权限的使用场景，而不只是简单说要这个权限，说清楚权限使用什么功能。


- UI兼容
```
Guideline 2.3 - Performance - Accurate Metadata

We were unable to install the app on iPad￼￼. The UIRequiredDeviceCapabilities key in the Info.plist is set in such a way that the app will not install on an iPad￼￼ .

翻译:
我们无法在 iPad 上安装应用程序￼￼。 Info.plist 中的 UIRequiredDeviceCapabilities 键设置为应用程序不会安装在 iPad 上￼￼。
```
这个问题有一些人遇到，但是我们实际测试时，在iPad真机是可以安装的，info.plist配置也没问题，后面我们拍了用testflight在iPad上安装的的视频并在解决方案中心回复，晚上时通过审核，怀疑是苹果自己的平台在安装时出现问题。回复模版：
Dear app review team:
Thank you for your patient work. 
We had tested our app on iPad and we had successfully installed the app on iPad. We recorded a video to show the installation process. The video url is xxxxx(youtube url).  Could you tell us the specific iPad model and system version which were unable to install our app. We will modify the app immediately. Thank you very much.
Best wishes for you.

- 无版权文件分享（侵权）
```
Guideline 5.2.3 - Legal - Intellectual Property

Your app falls into a category of apps that is often used for illegal file sharing. 

翻译:
您的应用属于经常用于非法文件共享的应用类别
```

- APP内包含博彩、暴力内容的元素，年龄需要在17+
```
In an effort to open up additional opportunities for developers, we’ve worked with the government of the Republic of Korea on making more apps available on the App Store in the Republic of Korea. And to ensure that our global age rating system continues to help make the App Store safe for kids, apps that feature Frequent/Intense Simulated Gambling will be rated 17+ in all countries and regions starting August 20, 2019. 
```

- APP有第三方登录功能时，也必须接入苹果登录
```
4.8 Sign in with Apple: Apps that exclusively use a third-party or social login service (such as Facebook Login, Google Sign-In, Sign in with Twitter, Sign In with LinkedIn, Login with Amazon, or WeChat Login) to set up or authenticate the user’s primary account with the app must also offer Sign in with Apple as an equivalent option.

翻译:
专门使用第三方或社交登录服务（例如 Facebook 登录、Google 登录、Twitter 登录、LinkedIn 登录、Amazon 登录或微信登录）来设置或验证用户主帐户的应用使用该应用程序还必须提供 Sign in with Apple 作为等效选项。
```

- 接入苹果登录，苹果登录按钮样式需要符合官方设计规范，需要在登录页面显示，不可隐藏到别的页面或者隐藏起来，设计跟位置需要跟其他第三方登录权重一样。
```
Guideline 4.0 - Design 

Your app offers Sign in with Apple as a login option but does not use the 
appropriate Sign in with Apple button design, placement, and/or user 
interface elements. Specifically:
- Sign in with Apple is not displayed in the app as an equivalent option 
for logging in. Sign in with Apple buttons should have a similar design as 
the buttons for other log in options, and the button should not be placed 
on separate pages or otherwise hidden. 
Next Steps
Please revise the Sign in with Apple buttons in your app so that they are 
compliant with the App Store Review Guidelines and the Sign in With 
Apple Human Interface Guidelines. 
Resources 
For information on implementing Sign in with Apple in your app:
- Review Displaying Sign in with Apple Buttons if your sign in process 
happens in a browser.
- Review the Sign in with Apple Human Interface Guidelines for an 
overview of design and formatting recommendations for Sign in with 
Apple.
Please see attached screenshot for details.
```

- 这个一般是因为账户存在违规操作，如刷榜、或者购买的开发者出问题（可能是卖卡方用同一张信用卡开通太多账号，有些账号违规导致牵连）
```
We are unable to continue this app's review because your Apple Developer Program account is currently under investigation for not following the App Store Review Guidelines' Developer Code of Conduct.
Inaccurately describing an app or service
-Misleading app content
-Engaging in inauthentic ratings and reviews manipulation
-Providing misleading customer support responses
-providing misleading responses in Resolution Center
-Engaging in misleading purchasing or bait-and-switch schemes
```

- 这个是因为产品的主要功能逻辑强依赖第三方软件，如微信小程序，这样的商业逻辑，苹果是不接受的。APP产品的主要功能逻辑需要不依赖第三方软件，不然会形成诱导用户下载第三方APP，这是苹果不允许的。
```
Guideline 3.2.2 - Business - Other Business Model Issues - Unacceptable

We noticed that your app includes an interface that displays or promotes mini programs for third-party apps, which is not appropriate for the App Store.

Next Steps
To resolve this issue, please remove any features in your app that promote programs for third-party apps.

翻译:
我们注意到您的应用程序包含显示或推广第三方应用程序小程序的界面，该界面不适合应用商店。
下一步
要解决此问题，请删除您应用中宣传第三方应用程序的所有功能。
```

- Testflight 公测分发时，如果短时间用户增长过快，很容易账户被苹果调查，需控制好用户数量

- 因为接入某些统计SDK，采集CAID导致审核被拒问题，可能是某些统计SDK因为某些原因被拉入黑名单，所以导致集成后被拒。
```
We found in our review that your app collects user and device information to create a unique identifier for the user's device. Apps that fingerprint the user's device in this way are in violation of the Apple Developer Program License Agreement and are not appropriate for the App Store.Specifically, your app uses algorithmically converted device and usage data to create a unique identifier in order to track the user. The device information collected by your app may include some of the following: sysctl, serviceSubscriberCellularProviders, NSFileSystemSize, isoCountryCode, and NSProcessInfo.

我们在审核中发现，您的应用会收集用户和设备信息以创建用户设备的唯一标识符。以这种方式对用户设备进行指纹识别的应用违反了 Apple 开发者计划许可协议，不适用于 App Store。具体而言，您的应用使用经过算法转换的设备和使用数据来创建唯一标识符，以便跟踪用户.您的应用程序收集的设备信息可能包括以下部分内容：sysctl、serviceSubscriberCellularProviders、NSFileSystemSize、isoCountryCode 和 NSProcessInfo。
```

```
We continue to find that your app collects user and device information to create a unique identifier for the user's device. Your app may be using some of the following API to create a unique identifier for the user's device: XX_FINGERPRINTING_METHODS_XX
```

- 直接去掉强制登录,或者在登录页面加入跳过按钮,我选择是去掉强制登录功能
```
Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage

We noticed that your app requires users to register with personal information to access non account-based features. Apps cannot require user registration prior to allowing access to app content and features that are not associated specifically to the user.

Next Steps

User registration that requires the sharing of personal information must be optional or tied to account-specific functionality. Additionally, the requested information must be relevant to the features.Please see attached screenshot for details.

翻译:
我们注意到您的应用要求用户注册个人信息才能访问非基于帐户的功能。在允许访问与用户无关的应用内容和功能之前，应用不能要求用户注册。
下一步
需要共享个人信息的用户注册必须是可选的或绑定到特定于帐户的功能。此外，所请求的信息必须与功能相关。有关详细信息，请参阅随附的屏幕截图。
```

- APP存在内购功能时，建议不要出现太大金额的充值，如果出现大金额充值，苹果会询问在哪些场景使用
```
Guideline 3.0 - Business 

We began our review, but we are unable to continue because we need additional information about your app.
Specifically, can you confirm that xxx USD is the intended price of your in-app purchase product, xxx⾦币? Additionally, please explain what factors led you to choose this pricing. Once we receive your confirmation, we will continue our review. If there's additional information you'd like to provide, please include it in your response to this message in Resolution Center.

翻译:
我们开始了审查，但我们无法继续，因为我们需要有关您的应用程序的其他信息。具体来说，您能否确认 xxx 美元是您的应用内购买产品，xxx⾦币？另外，请说明是什么因素导致您选择此定价。收到您的确认后，我们将继续审核。如果您还想提供其他信息，请将其包含在您在调解中心对此消息的回复。
```

### 少儿类

- 少儿类APP苹果控制得很严格，如果检测到代码使用一些数据收集SDK，或者去获取用户一些敏感数据，都很容易触发这个。要么移除获取数据的SDK，要么提升年龄等级
```
Guideline 1.3 - Safety - Kids Category

We noticed that your Kids Category app includes analytics, advertising and collects, transmits, or has the ability to share personal information or device information with third parties. 

翻译:
我们注意到您的儿童类别应用程序包含分析、广告并收集、传输或能够与第三方共享个人信息或设备信息。
```

### 直播类

- 被拒原因应该是 申请人在领取营业执照后3天内，必须将《网络文化经营许可证》和营业执照的复印件分别报受理申请的县（市、区）级文化行政部门、公安部门备案
```
5. 2.1 Legal: Intellectual Property - General
Guideline 5.2.1 - Legal - Intellectual Property

Your app facilitates, enables, or encourages live video chat or performance (网络直播/表演/秀场), but you haven’t provided the appropriate documentation for the services in your app.
Next Steps
To resolve this issue, please complete the following:
— Provide a copy of your filing record with the China Public Security Bureau (公安机关互联网备案信息). 
Resources
To provide documentation:
- Log in to App Store Connect
- Click on "My Apps"
- Select your app
- Click on the app version on the left side of the screen
- Scroll down to "App Review Information"
- Attach the scanned copy of your Internet Cultural Business License (网络文化经营许可证) in the "Attachment" section
- Click "Save"
Once this information is available, please reply to this message in Resolution Center, and we can continue with our review.
```


- APP打赏问题,不能直接红包打赏,提示信息不能直接显示红包内容,只能换成对等的虚拟物品进行打赏
```
Guideline 3.1.1 - Business - Payments - In-App Purchase

We noticed that your app allows users to "tip" the digital content creators in your app with a mechanism other than the in-app purchase API, which is not appropriate for the App Store.

Next Steps

To resolve this issue, please revise your app to use the in-app purchase API to pay for these sorts of transactions. Please note that while guideline 3.2.1(vii) of the App Store Review Guidelines allows individual users to give a monetary gift to another individual user without using in-app purchase, that gift must not be connected to or associated at any point in time with receiving digital content or services.

While the payment system that you have included may conduct the transaction outside of the app, if the purchasable content, functionality, or services are intended to be consumed within the app, they must be purchased through in-app purchase - unless it is of the type referenced in guideline 3.1.3 of the App Store Review Guidelines.
```

- 直播类APP年龄分级需要17+


### 社交类应用

- 图片社交、SNS、交友需要有拉黑举报功能

- 需要提供2个正常的审核账号
```
Guideline 2.1 - Information Need

Provide an active demo account and login information, plus any other hardware or resources that might be needed to review your app (e.g. a sample QR code)

翻译: 
提供有效的演示帐户和登录信息，以及审查您的应用程序可能需要的任何其他硬件或资源（例如示例二维码）
```

### 区块链应用

中国区

- 需要中心化的账号体系

### 金融类

- 理财类产品需要理财资质证明

- 名字跟开发者账号挂钩

### VPN类型

- 条款见：通用条款 —— 5.4 VPN App（https://developer.apple.com/cn/app-store/review/guidelines/）

- 中国要求所有VPN应用的开发商都需要获得VPN许可证（电信增值业务 VPN的牌照）见：https://zh.wikipedia.org/wiki/中国区App_Store下架VPN应用事件


### 彩票类

- 中国区彩票不给网上线上销售，动了别人的蛋糕

- 2018年多款彩票类应用直接不给更新

- 有抽奖、赌博的活动（凡APP涉及抽奖/比赛/彩票/赌博内容/奖品涉及苹果公司产品）需要限制年龄17+，并且声明活动跟苹果无关
```
Guideline 5.3.2 - Legal - Gaming, Gambling, and Lotteries

Your app includes a contest or sweepstakes, but it does not indicate the Apple is not involved in any way with the contest or sweepstakes. Also. it does not enforce an app age rating of 17+.)

翻译: 
您的应用程序包含竞赛或抽奖活动，但并不表示 Apple 未以任何方式参与竞赛或抽奖活动。还。它不会强制执行 17 岁以上的应用年龄评级。
```

### 商城
- APP商品如果是虚拟物品需要走苹果内购渠道

- APP内的虚拟商品不可购买后在第三方APP上使用

- APP商品如果是实物可走第三方支付渠道，如信用卡，微信、支付宝等支付渠道

### 登录相关
- 当用户使用sign with apple时，登录后不应该去获取用户的手机号、性别、出生年月等信息，需要保护用户的隐私安全。如果需要获取则要提供跳过选项。
```
Guideline 5.1.1 - Legal - Privacy - Data Collection and Storage

We noticed that your app requires users to register or log in to access features that are not account-based.  
Specifically, we were required to provide phone number after using Sign in with Apple.）

翻译:
我们注意到您的应用要求用户注册或登录才能访问非基于帐户的功能。
具体来说，我们需要在使用 Sign in with Apple 后提供电话号码。
```

### 硬件
- 提审硬件相关的软件，需要录制一个演示视频来展示所有功能的交互操作，并且把视频链接上传到youtube上，这样美国审核时能访问

- 演示视频里，一定要用真实的设备、苹果手机进行演示，不要使用模拟器

- 演示视频里一定要使用所有功能，让苹果了解各个功能的使用情况，登录前、登录后的功能

### 游戏
中国区

- 需要游戏著作权、版号、网文号

- 网游针对未成年防沉迷系统

- 如果APP有博彩类游戏，一定要声明活动与苹果无关，一般就是在活动页面注明本活动跟苹果公司无关
```
Guideline 5.3.2 - Legal - Gaming, Gambling, and Lotteries

Your app includes a contest or sweepstakes, but it does not indicate the Apple is not involved in any way with the contest or sweepstakes.

翻译:
游戏、赌博和彩票：您的应用程序包含竞赛或抽奖活动，但并不表示 Apple 未以任何方式参与竞赛或抽奖活动。
```

### 马甲包制作

- 需要修改：账号，IP，名字，包名，方法名，类名，图片名，图片md5
```
Guideline 4.3 - Design

We noticed that your app provides the same feature set as other apps submitted to the App Store; it simply varies in content or language, which is considered a form of spam.)

翻译:
我们注意到您的应用程序提供与提交到 App Store 的其他应用程序相同的功能集；它只是在内容或语言上有所不同，这被视为山寨的一种形式
```

### 惩罚相关

- 苹果对黄赌毒 0容忍，一经过发现，立刻下架，并有可能封号

- 如刷榜、虚假评论、版权纠纷、欺诈行为、企业分发等行为给发现后会给封号

- 遇到苹果的警告邮件，应保持冷静，同时提交申诉邮件，不要转走应用，苹果能追查到，严重时会连锁封号

- 苹果最近的惩罚采用连带制度，如果一个账号加入多个企业组织，很容易因为一个账号被封导致其他账号也一起遭殃。最好一个apple id归属一个组织，同时提审时尽量用不同IP跟机器
