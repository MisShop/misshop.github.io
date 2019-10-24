1、修改MisShop程序为oracle数据库支持：
  a、修改文件：
  如果是eclipse方式启动，则修改resources/app-ide-config.xml，resources/app-config.xml
 如果是安装包方式启动，则修改MisShop/WebRoot/WEB-INF/classes/app-ide-config.xml，MisShop/WebRoot/WEB-INF/classes/app-config.xml
如果是tomcat方式启动，则修改tomcat/webapps/misshop/WEB-INF/classes/app-ide-config.xml，tomcat/webapps/misshop/WEB-INF/classes/app-config.xml

b、修改内容：将h2改成oracle即可
![image.png](https://upload-images.jianshu.io/upload_images/12920178-ce5bbb671b0bbe5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


2、复制oracle数据库连接文件：
a、修改文件：project/db.ini
![image.png](https://upload-images.jianshu.io/upload_images/12920178-71c8bf339e3b1d97.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
b、修改内容：复制db_proto_oracle.ini的内容，覆盖project/db.ini中的内容 
  文件位置：WebRoot/WEB-INF/classes/proto/db_proto_oracle.ini
![image.png](https://upload-images.jianshu.io/upload_images/12920178-a9f5affb515aeea8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


3、配置oracle数据库连接文件：
配置项目使用的数据库jdbc连接：url/user/password/schema/dsName
![image.png](https://upload-images.jianshu.io/upload_images/12920178-c36304d9c16879e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

另注：以上修改文件，请不要使用windows自带记事本编辑，可能存在编码问题。
可使用notepad++/editplus等高级记事本编辑

