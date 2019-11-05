在使用MisShop开发项目的过程中，难免会出现数据问题，这时可使用数据表的编辑数据功能预览数据，也可更直接去使用数据库工具查看实际数据库中数据。
MisShop常用数据库，包括H2、Mysql、Oracle、SQLServer

1、MisShop默认使用H2数据库：
H2是文件数据库，也就是这个数据库只有一个文件，这个文件就是一个完整的数据库。
MisShop的项目中，数据库默认为project/data/dms.h2.db文件  
 ![images](http://www.misshop.com.cn/res/doc/gj1.png)    
 
可使用：H2 Database，
下载地址：http://www.greenxf.com/soft/211994.html
这个是个简单的网页版数据库工具，基于JDK的，所以机器上必须安装有JDK或者JRE，配置有JAVA_HOME。如果机器上未单独安装JDK，也可配置JAVA_HOME到MisShop自带的JRE。
配置JAVA_HOME(Win7示例)：开始->计算器->右键->属性->高级系统配置->环境变量->系统变量->新建：变量名：JAVA_HOME ， 变量值：D:\MisShop\java\jre ->选中Path ->编辑：在最前添加：%JAVA_HOME%\bin; ->确定
H2数据工具启动方式：双击安装目录下的bin/h2.bat，弹出浏览器  
 ![images](http://www.misshop.com.cn/res/doc/gj2.png)    
 
  
   ![images](http://www.misshop.com.cn/res/doc/gj3.png)    
   

JDBC URL：jdbc:h2:E:\worklocation_misshop\A36\data/dms;DATABASE_TO_UPPER=FALSE;MODE=MYSQL;AUTO_SERVER=TRUE;EARLY_FILTER=TRUE;
其中选中的部分为H2数据库文件的绝对位置(不带后缀)，替换下，然后点击Connect即可连接H2数据库  
 ![images](http://www.misshop.com.cn/res/doc/gj4.png)    
 

连接成功后，即可执行sql语句操作，查看以及修改数据
2、Mysql数据库，可使用多种数据库工具，常用的有Navicat。
下载地址：https://www.navicat.com.cn/download/navicat-premium
安装成功后，双击navicat.exe即可访问  
 ![images](http://www.misshop.com.cn/res/doc/gj5.png)    
 

点击连接，选择Mysql，输入mysql连接配置项  
 ![images](http://www.misshop.com.cn/res/doc/gj6.png)    
 
点击确定，连接成功后，即可操作  
 ![images](http://www.misshop.com.cn/res/doc/gj7.png)    
 3、Oracle数据库，可使用多种数据库工具，常用的有Navicat，
使用Navicat连接数据库的时候，需要在客户端，也就是安装Navicat的机器上，要安装Oracle client：instantclient_11_2.zip
下载地址：https://www.oracle.com/technetwork/cn/database/features/instant-client/index-092699-zhs.html  
 ![images](http://www.misshop.com.cn/res/doc/gj8.png)    
 
直接解压后，配置navicat中oci为instantclient安装目录中的oci。
navicat中菜单：工具->选项->OCI->OCI library(oci.dll)，选择instantclient/oci.dll  
 ![images](http://www.misshop.com.cn/res/doc/gj9.png)      
 
此时就可以新建oracle连接了：  
 ![images](http://www.misshop.com.cn/res/doc/gj10.png)    
 