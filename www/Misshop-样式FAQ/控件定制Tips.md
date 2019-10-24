MisShop平台可以以配置的方式自己来定义控件的样式模板，配置完之后，所有页面的该类型控件以及后续新建页面里的相应控件都会具有这种样式。下面以日历选择控件为例说明：
从安装包或项目代码中找到日历选择控件对应的配置文件calendar.txt，我们可以看到有这样一行配置：
````
"wiseClassStr": "width/width-full"
````
这样一个配置就能将页面的日历选择控件的缺省宽度都设为100%宽，因为width-full就是系统之中的css定义中的一个样式名字，这个样式可以将页面元素的宽度设为100%。
那么如何能得到一个合法的样式值呢？可以先用设计器的样式配置对话框将对应控件配置好，然后查看样式配置属性的值，这个值（可以是多个样式的组合）就是wiseClassStr的合法值。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-855af7e22cea8818.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

