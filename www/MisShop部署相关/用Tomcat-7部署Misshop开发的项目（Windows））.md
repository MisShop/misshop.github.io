首先需要在服务器上安装JDK 7或者JRE 7。安装完之后再安装Tomcat的windows服务版本，可以去[https://tomcat.apache.org/download-70.cgi](https://tomcat.apache.org/download-70.cgi)找到相关的安装包：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-5f7ee59b71aa312a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
装完Tomcat之后，需要如下配置：
1. tomcat安装目录下的conf目录下的Server.xml:
修改其中的HTTP对应的Connector的端口和字符集编码：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-bf2d693d19f1b75e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. 运行tomcat安装目录下的bin目录下的Tomcat7w.exe，然后修改Java标签页的Java Options: 需要添加-Dfile.encoding="UTF-8", 如下图所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-5f30d246436d76ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 拷贝Eclipse里或者Misshop安装包下的WebRoot目录(到Tomcat安装目录下的webapps目录下，并改名为misshop（下面称之为代码包目录）
4. 修改代码包目录下的WEB-INF目录下的classes目录下的config.ini, 使得WEB_ROOT_DIR指向代码包目录（例如d:\tomcat7\webapps\misshop）；修改project值，使其指向开发好的项目所在的目录。
5. 修改和config.ini相同目录下的log4j.properties，将其中的logs/****.log改为具体的全路径目录，如下图所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-ad3d69100e8ec361.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

6. 重启Tomcat服务 （从桌面右下角的tomcat服务监控器发起）
