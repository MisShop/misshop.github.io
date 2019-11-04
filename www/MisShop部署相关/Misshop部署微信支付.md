Misshop支持在微信公众号里进行微信支付。
首先微信公众号需要是服务号而不是订阅号，同时需要已完成企业认证（https://mp.weixin.qq.com）； 然后需要
1. 开通微信支付, （建议用微信公众号的超级管理员）登录公众号后，点击左侧微信支付菜单：
![images](http://www.misshop.com.cn/res/doc/BSWX1.png)
按照步骤接入微信支付后，在https://pay.weixin.qq.com网站上就建立了微信商户账号，而刚才这个登录微信公众号的微信账号就成为了微信商户账号的超级管理员。开通过程需要审核，时间大于1天。
2. 关联微信公众号和微信支付账号：
查看如图的页面：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-9f8aa94247b672ee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在该页面发起关联申请。待审核通过则该步骤完成。

关联成功如下所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-2f250b908fd12ee8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3. 配置微信公众号（请参考[https://www.jianshu.com/p/09984d7129b2](Misshope配置微信公众号)
）
4.配置微信支付
4.1 支付授权目录：浏览器进入微信商户平台（pay.weixin.qq.com），设置路径：产品中心-->开发配置，添加Misshop项目的域名作为授权目录，举例如下：http://demo.misshop.com.cn/或者http://demo.misshop.com.cn/misshop/（推荐）
![image.png](https://upload-images.jianshu.io/upload_images/12920178-85599251d55df631.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
注意事项，1.这个目录必须以/结尾； 2. 这个目录建议精确到支付页面路径（在MisShop平台就是mobile.jsp）的父级目录（对于MisShop平台就是到project.mis文件中的contextName/为止）。

4.2 安装API证书： 浏览器进入微信商户平台（pay.weixin.qq.com），设置路径：帐户中心-->API安全，按照提示下载证书安装工具，生成证书并下载备用。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-fb620c3b96971afc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](https://upload-images.jianshu.io/upload_images/12920178-115bf2f338ec8f98.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.3 设置API密钥：同样在帐户中心-->API安全页面，按照提示设置API密钥。
5. 部署微信支付信息到Misshop项目
部署过程要求每个商户都提供3个信息，商户ID,API密钥和证书文件。其中商户ID就是商户号，从商户平台或者已关联商户表格中都可以查到。Misshop把这些敏感的信息做了一套部署规范：
      a. 建立一个名叫ShopsConf的文件夹
      b. 每个商户在ShopsConf下建立一个文件夹，这个文件夹的名字就是商户的名字或简称，下面将该文件夹称之为商户文件夹。
      c. 把之前下载好的证书压缩包里面一个扩展名为p12的证书文件复制到对应商户的商户文件夹里面。
      d. 在商户文件夹下，再建立一个ini文件， 这个ini文件的名字和商户文件夹的名字一致。例如，商户文件夹的名字叫“昌盛商贸”，那个这个ini的文件名就是"昌盛商贸.ini"。
      e. 这个ini文件里面包含3个信息，分别是上述的商户ID、上述的商户的API密钥，以及一个叫accessToken的配置。Misshop平台访问这些敏感信息是通过传入商户的名字来匹配查找的，但是传入商户名字的同时要求再传一个口令，这个口令必须和ini文件里accessToken的配置值完全一致才能获取到商户的商户ID,API密钥及API安全证书。ini文件内容如下所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-46e7efbcf93b18b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

ini文件里必须包含这三个键accessToken, mchId还有apiKey，以及对应的值。
        f. 将ShopsConf文件夹挪到WebRoot文件夹的祖父文件夹下面，这样的部署结构是从安全角度考虑，同时又保证了这些支付所需信息的可访问性。为什么不放到WebRoot的父文件夹下与WebRoot同级呢 ，这个原因是由于如果采用tomcat方式部署Misshop项目的情况，就会出现ShopsConf位于webapps目录下，tomcat会认为它是一个Web项目从而报错。
6. 使用微信支付控件
![image.png](https://upload-images.jianshu.io/upload_images/12920178-302cdcbabc2aeaac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
7. 配置微信支付控件
![image.png](https://upload-images.jianshu.io/upload_images/12920178-6bec91c672bedc68.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这里的订单号需要保证唯一性，另外金额是以分为单位的，所以通常需要乘以100。
8. 支付成功之后的订单状态回置
![image.png](https://upload-images.jianshu.io/upload_images/12920178-7dca112203d0c4df.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在这个页面配置回调页面，这个页面必须是一个具有保存按钮的订单状态修改raq, 这个页面接收两个参数orderid和wxopenid,分别代表订单号和购买者的微信ID，微信支付成功后，系统接收到微信支付平台的支付成功通知并自动保存这个回调页面，从而实现订单状态的更新。
