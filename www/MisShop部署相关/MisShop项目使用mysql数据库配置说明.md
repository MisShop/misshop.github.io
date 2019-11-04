1、修改MisShop程序为mysql数据库支持：
  a、修改文件：
  如果是eclipse方式启动，则修改resources/app-ide-config.xml，resources/app-config.xml
 如果是安装包方式启动，则修改MisShop/WebRoot/WEB-INF/classes/app-ide-config.xml，MisShop/WebRoot/WEB-INF/classes/app-config.xml
如果是tomcat方式启动，则修改tomcat/webapps/misshop/WEB-INF/classes/app-ide-config.xml，tomcat/webapps/misshop/WEB-INF/classes/app-config.xml

b、修改内容：将h2改成mysql即可  
![images](http://www.misshop.com.cn/res/doc/sql1.png)       

2、复制mysql数据库连接文件：
a、修改文件：project/db.ini  
![images](http://www.misshop.com.cn/res/doc/sql2.png)       
  
  
b、修改内容：复制db_proto_mysql.ini的内容，覆盖project/db.ini中的内容 
  文件位置：WebRoot/WEB-INF/classes/proto/db_proto_mysql.ini  
  ![images](http://www.misshop.com.cn/res/doc/sql3.png)         
  
3、配置mysql数据库连接文件：
配置项目使用的数据库jdbc连接：url/user/password/schema/dsName  
![images](http://www.misshop.com.cn/res/doc/sql4.png)         



另注：以上修改文件，请不要使用windows自带记事本编辑，可能存在编码问题。
可使用notepad++/editplus等高级记事本编辑

