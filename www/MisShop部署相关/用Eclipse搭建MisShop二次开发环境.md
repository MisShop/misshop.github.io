1、eclipse上创建普通工程，非web工程，JDK支持使用5/6/7：  
![images](http://www.misshop.com.cn/res/doc/hj1.png)  



2、在MisShopPlus下，创建资源包pics/resources：  
![images](http://www.misshop.com.cn/res/doc/hj2.png)  



3、解压pics.zip并复制内容到pics资源包中：
  链接: https://pan.baidu.com/s/1uPves_Y1lpTFYRmENlm9Ew 提取码: 7n6k 
      解压resources.zip并复制内容到resources资源包中：
链接: https://pan.baidu.com/s/1jwnFo5e-tJ6NEk9FfgBd5A 提取码: mcby  
![images](http://www.misshop.com.cn/res/doc/hj3.png)  



4、复制安装目录下的/MisShop/WebRoot文件夹到MisShopPlus下：  
![images](http://www.misshop.com.cn/res/doc/hj4.png)  


5、配置eclipse中的classpath:
  设定buildpath的classes目录：为MisShopPlus/WebRoot/WEB-INF/classes  
  ![images](http://www.misshop.com.cn/res/doc/hj5.png)  


  将MisShopPlus/WebRoot/WEB-INF/lib下的jar添加进来  
  ![images](http://www.misshop.com.cn/res/doc/hj6.png)  


6、配置工程：resources/config.ini:
其中:WEB_ROOT_DIR为工程的MisShopPlus/WebRoot文件夹绝对位置  
![images](http://www.misshop.com.cn/res/doc/hj7.png)  


project为当前项目绝对位置  
![images](http://www.misshop.com.cn/res/doc/hj8.png)  



7、添加logs文件夹：在MisShopPlus下添加文件夹logs  
![images](http://www.misshop.com.cn/res/doc/hj9.png)  



8、启动MisShop设计器：
搜索EmbeddTomcat.class  
![images](http://www.misshop.com.cn/res/doc/hj10.png)  

在EmbeddTomcat.class上，右键选择Run As-->Java Application，即可启动

另注：以上修改文件，请不要使用windows自带记事本编辑，可能存在编码问题。
可使用notepad++/editplus等高级记事本编辑

