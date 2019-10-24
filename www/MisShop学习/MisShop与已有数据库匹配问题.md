场景：
MisShop匹配已经存在或者正在使用的数据库，如一个旧的管理系统，使用MisShop重新做，那么使用MisShop新建的项目，就需要匹配这个数据库，而不是新建数据库

目标：
MisShop的数据处理，是基于数据库中，所以在MIsShop中定义的数据表，以及字段，都应该是在对应的数据库中存在的。所以如果使用旧数据库，那么第一步，就应该是把数据库中的表与MisShop中定义的数据表同步起来

同步方式：
第一种：从数据库出发，往MisShop设计器中导入
优点：实现一键匹配
缺点：可能导入的信息不全
这种方式会导入数据表名/字段名/字段类型/复合主键/唯一性约束，并尝试导入外键关系。
但长度限制，必填，默认值等无法导入
1、点击菜单-->数据-->导入数据表。
系统会先去查询数据库，看看有哪些数据表，是MisShop设计器中没有的，显示出来。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-12454d6b003aeb9b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2、勾选需要导入到MisShop设计器中的表
3、点击导入选中表，系统会将这些表导入到MisShop中
4、查看设计器中数据表，修改必填/默认值等配置

第二种：从MisShop出发，配置为数据库相同
优点：对照着数据库的设计内容，可以将每一项配置的和数据库完全匹配。
缺点：需要在设计器中逐个配置，相当于新建数据库表定义

步骤：
1、勾选不同步数据库：这样在MisShop设计器中，修改数据表设计的时候，不会修改数据库。相当于单方面修改MisShop设计器中数据表
![image.png](https://upload-images.jianshu.io/upload_images/12920178-47842417f2637a94.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2、参考数据库中数据表定义，在MisShop中设计数据表
3、数据表设计完成后，勾选可选同步数据库
另注：
a、如果旧系统还在使用此数据库，那么可以不勾选，这样在MisShop中，操作设计表定义，就不会修改数据库，也就不会影响旧项目的使用
b、上面的控制，是数据库级别的同步控制。
在勾选为可选同步数据库后，在数据表设计中，也可用不勾选自动同步数据库，来去掉MisShop数据表设计与数据库中的关联关系。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-e293c8fa69470570.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


