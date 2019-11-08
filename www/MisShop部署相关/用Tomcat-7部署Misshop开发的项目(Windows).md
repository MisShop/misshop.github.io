0、	下载tomcat：https://tomcat.apache.org/download-70.cgi
MisShop默认使用tomcat7
下载版本和本地JAVA_HOME配置的版本必须一致，JAVA_HOME可配置为MisShop/java/jre。默认是64位的  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop0.png)    



1、解压tomcat，tomcat的路径中不能使用空格
	路径如：D:\tomcat-7.0.72_x86  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop1.png)    



2、配置tomcat的端口和编码：
	conf/server.xml  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop2.png)    



3、使用文本编辑器打开server.xml文件
	默认端口为8080，为访问网址中的的端口号，可以改成80，这样访问时候，因为浏览器默认的端口号为80，就不需要添加端口号,
	添加编码为utf-8，因为misshop默认使用UTF-8，此项必须配置，  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop3.png)    



4、复制安装目录下的WebRoot到webapps下，如  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop4.png)    



5、此WebRoot为访问网址中的contextName，可以修改为misshop  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop5.png)    



6、复制工程到misshop/WEB-INF/下，  




7、配置config.ini
	在/webapps/misshop/WEB-INF/classes	/config.ini
	使用文本编辑器打开：
	修改WEB_ROOT_DIR为项目根目录
	修改project为工程根目录  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop7.png)    



8、修改log4j.properties
	在/webapps/misshop/WEB-INF/classes	/log4j.properties
	使用文本编辑器打开：将内部的logs文件夹指定到指定位置，一般指定到tomcat的logs文件夹中，搜索：=logs/，如：替换为： =D:/tomcat-7.0.72_x86/logs/
此文件夹必须存在，如果不存在，请先创建文件夹  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop8.png)    



9、如果不是h2数据库，修改app-ide-config.xml/app-config.xml
	在/webapps/misshop/WEB-INF/classes	/ app-config.xml
	如项目为oralce数据的时候，修改为 oralce:  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop9.png)    



10、如果启动时不同步数据库，或者禁止同步数据库，修改report4config.xml
	在/webapps/misshop/WEB-INF/classes	/ report4config.xml
	修改文件的<OPTIONS>标签的属性
		设置：bCanSyncToDb="false" 禁止同步数据库
			  bSyncWhenStart="false" 启动时不同步数据库  
![images](http://www.misshop.com.cn/res/doc/tomcat7_mishop10.png)    



11、启动：
	windows下：bin/startup.bat
	linux下：bin/startup.sh
12、浏览器上访问网址：
	http://localhost/misshop

