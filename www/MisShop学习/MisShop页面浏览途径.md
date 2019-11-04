场景：使用MisShop设计器开发的系统，需要在浏览器上看到最终的效果。

访问方式：
PC端导航树页面：index.jsp
用于PC端，访问页面，可以访问所有有权限的页面  
![images](http://www.misshop.com.cn/res/doc/ll1.png) 

Mobile端导航树页面：mobile.jsp
用户Mobile端，以左侧边导航树的方式，访问页面，可以访问mobile模块下，所有有权限的页面  
![images](http://www.misshop.com.cn/res/doc/ll2.png) 

Mobile端Tab导航页面：mobile.tab.jsp
用户Mobile端，以底部菜单的方式，访问页面，可以访问mobile模块下，所有有权限的页面  
![images](http://www.misshop.com.cn/res/doc/ll3.png) 


登录方式：
1、访问login.jsp会跳转到index.jsp
2、访问mobile/login.html会跳转到mobile.jsp
3、访问mobile/login.html?indexJspName=mobile.tab.jsp会跳转到mobile.tab.jsp
4、从设计器中点击浏览按钮，mobile模块下页面，会跳转到mobile.jsp，其他页面会跳转到index.jsp

PC中浏览器中，模拟mobile浏览器：
在浏览器中，点击F12或者点击设置中的开发者工具，调出浏览器自带的开发者工具。点击开发者工具的左上角的手机图标，即可在PC端浏览器中模拟手机浏览器效果  
![images](http://www.misshop.com.cn/res/doc/ll4.png) 





