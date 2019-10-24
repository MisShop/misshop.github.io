场景：使用MisShop设计器开发的系统，需要在浏览器上看到最终的效果。

访问方式：
PC端导航树页面：index.jsp
用于PC端，访问页面，可以访问所有有权限的页面
![image.png](https://upload-images.jianshu.io/upload_images/12920178-b9687717cf4e1a6f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Mobile端导航树页面：mobile.jsp
用户Mobile端，以左侧边导航树的方式，访问页面，可以访问mobile模块下，所有有权限的页面
![image.png](https://upload-images.jianshu.io/upload_images/12920178-21b1a60ef2f6c6e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Mobile端Tab导航页面：mobile.tab.jsp
用户Mobile端，以底部菜单的方式，访问页面，可以访问mobile模块下，所有有权限的页面
![image.png](https://upload-images.jianshu.io/upload_images/12920178-1ac6e8f06acbd416.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

登录方式：
1、访问login.jsp会跳转到index.jsp
2、访问mobile/login.html会跳转到mobile.jsp
3、访问mobile/login.html?indexJspName=mobile.tab.jsp会跳转到mobile.tab.jsp
4、从设计器中点击浏览按钮，mobile模块下页面，会跳转到mobile.jsp，其他页面会跳转到index.jsp

PC中浏览器中，模拟mobile浏览器：
在浏览器中，点击F12或者点击设置中的开发者工具，调出浏览器自带的开发者工具。点击开发者工具的左上角的手机图标，即可在PC端浏览器中模拟手机浏览器效果
![image.png](https://upload-images.jianshu.io/upload_images/12920178-c104e9fe9a266cb7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




