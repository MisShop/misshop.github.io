前提条件，需要一台拥有域名的服务器来部署Misshop项目，下面以demo.misshop.com.cn这个域名为例（注意这个域名已经映射了IP地址，是123.57.246.120）。
1. 登录微信公众号管理后台( mp.weixin.qq.com)
2. 左侧菜单中：开发-->基本配置，找到下方的服务器配置，进行如下配置：
![images](http://www.misshop.com.cn/res/doc/pzwx1.png)

![images](http://www.misshop.com.cn/res/doc/pzwx2.png)

3. 左侧菜单中：设置--公众号设置，进去后选择中间的标签“功能设置”，做出配置如下，注意不要加http://
![images](http://www.misshop.com.cn/res/doc/pzwx3.png)
4. 配置自定义菜单：左侧菜单中：功能-->自定义菜单，在自定义菜单的链接地址中用如下格式输入：https://open.weixin.qq.com/connect/oauth2/authorize?appid=wxc35b3e4743602389&redirect_uri=http://demo.misshop.com.cn/misshop/wxMenuServlet&response_type=code&scope=snsapi_base&state=1#wechat_redirect ，这里需要变化的是appid的值（在公众号开发>基本配置中有），redirect_uri中的域名部分（准备好的域名），以及state的值，每个菜单给一个不同的state值，从1开始。
![images](http://www.misshop.com.cn/res/doc/pzwx4.png)
5.配置IP白名单：
如上图所示，请将部署Misshop的服务器的公网IP配置为公众号的IP白名单成员。

6. 配置Misshop项目中的公众号信息：
![images](http://www.misshop.com.cn/res/doc/pzwx5.png)
其中的Appid和AppSecret从下面的公众号管理页面获取：
![images](http://www.misshop.com.cn/res/doc/pzwx6.png)
7.配置公众号菜单对应的页面：
同样在微信公众号配置页的下方，分别对应之前state的值，配置不同的页面路径：这个页面路径需要以page开头后面加上设计器中的路径，页面不需要加扩展名，如下图所示：
![images](http://www.misshop.com.cn/res/doc/pzwx7.png)
由于是移动端页面，通常页面位于page/mobile/下，但是展示类的不需要登录就能访问的页面是在page/免登录模块/下。




