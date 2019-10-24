1、eclipse上创建普通工程，非web工程，JDK支持使用5/6/7：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-098517dd576845f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


2、在MisShopPlus下，创建资源包pics/resources：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-f5d836c06ed8eaea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


3、解压pics.zip并复制内容到pics资源包中：
  链接: https://pan.baidu.com/s/1uPves_Y1lpTFYRmENlm9Ew 提取码: 7n6k 
      解压resources.zip并复制内容到resources资源包中：
链接: https://pan.baidu.com/s/1jwnFo5e-tJ6NEk9FfgBd5A 提取码: mcby
![image.png](https://upload-images.jianshu.io/upload_images/12920178-7dee0c0e33853cef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


4、复制安装目录下的/MisShop/WebRoot文件夹到MisShopPlus下：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-c54e6a446deae95e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5、配置eclipse中的classpath:
  设定buildpath的classes目录：为MisShopPlus/WebRoot/WEB-INF/classes
![image.png](https://upload-images.jianshu.io/upload_images/12920178-07073ace29d85790.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  将MisShopPlus/WebRoot/WEB-INF/lib下的jar添加进来
![image.png](https://upload-images.jianshu.io/upload_images/12920178-3cef87d76376e8b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

6、配置工程：resources/config.ini:
其中:WEB_ROOT_DIR为工程的MisShopPlus/WebRoot文件夹绝对位置
![image.png](https://upload-images.jianshu.io/upload_images/12920178-09a6f494042f347a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

project为当前项目绝对位置
![image.png](https://upload-images.jianshu.io/upload_images/12920178-21d6cfd58d4e62c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


7、添加logs文件夹：在MisShopPlus下添加文件夹logs
![image.png](https://upload-images.jianshu.io/upload_images/12920178-57e6ab336f020b70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


8、启动MisShop设计器：
搜索EmbeddTomcat.class
![image.png](https://upload-images.jianshu.io/upload_images/12920178-75f5e8108f5000ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在EmbeddTomcat.class上，右键选择Run As-->Java Application，即可启动

另注：以上修改文件，请不要使用windows自带记事本编辑，可能存在编码问题。
可使用notepad++/editplus等高级记事本编辑

