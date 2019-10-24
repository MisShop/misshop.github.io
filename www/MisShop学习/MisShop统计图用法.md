一、MisShop统计图概述
说起统计图，我们首先想到的就是柱形图、折线图和饼图。MisShop的统计图除了支持这几种基本类型之外，还可以制作累积柱形图、面积图、散点图、雷达图、漏斗图、区域地图和基于百度地图的地理坐标点图和地理坐标线图。
MisShop的统计图具有以下特点：
1. 使用简单，一拖就得
2. 支持图表的各种配置参数：如标题、坐标轴、图例、图形等元素的颜色、字体、位置等。
统计图控件是一个比较特殊的区域控件，在统计图区域内部，必须按照要求使用统计图相关的子控件。不同的图表类型，都有不同的子控件的组合要求。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-4c8622425e39863e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

下面举一个例子来说明一下：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-43606946b6daa874.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我们看到整个统计图（区域）是从A1到D6的一个大区域，这里包含了标题、图例、工具栏、Y轴和统计图数据区这些子控件。而统计图数据区本身又是一个小的区域控件（从A3到D6），它里面又包含了X轴和柱状图序列组件。事实上，统计图数据区是唯一必须要有的子控件，其他的控件都是辅助性的可选子控件。而在统计图数据区内部，我们要求必须有一个X轴组件，而且必须放置在统计图数据区的第一行和第一列，而在第一行的其他剩余列，则必须是某一种数据序列子控件。从统计图数据区内部的第二行开始到最后一行，我们认为是具体的列向数据扩展，比如说第一列的第二行以下是X轴的具体数据， 其他列的第二行以下是对应列头的数据序列的具体数据。如下图所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-5cd8273ba97d95d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
二、MisShop统计图子组件
1. 统计图标题：
统计图标题是在统计图上绘制的一行说明性的文本文字。还可以配置副标题。通常我们需要配置标题的位置、颜色和字体信息。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-200523a2b405d5a7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
上图指示了如何配置标题组件的位置和字体大小，对于标题的文字颜色和背景色则可以统一使用Misshop设计器工具栏上的前景色和背景色快捷修改器来改变，当然，同时也支持用样式配置对话框中的文本颜色和控件背景色来改变。
2. 统计图图例：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-90ace77df3bc9540.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

统计图图例通常用颜色块+数据序列名称的方式指示图形中的颜色的含义。可以通过点击图例项，使得对应的数据序列产生隐藏和出现的功能。图例项的颜色是由对应的数据序列组件决定的。我们通常需要配置的是图例的位置和字体，当然也可以更精细地控制图例项之间的距离等细节。如果想要给整个图例区域设置背景色，则可以统一使用Misshop设计器工具栏上的背景色快捷修改器来改变; 当然，同时也支持用样式配置对话框中的控件背景色来改变。
3. 统计图工具栏：
统计图工具栏是一组针对统计图的预制功能按钮，包括了区域缩放、表格视图、柱状/线性切换、操作还原以及保存为图像功能。
如果我们需要在统计图上陈列这些功能的全部或其中一部分时，则加入统计图工具栏子组件。工具栏可以水平放置，也可以垂直放置。这些功能按钮每一个都是可选的。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-73f4123de4a3b545.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
如果需要修改图标的颜色，则需要修改样式配置对话框中的文字颜色。
4. Y轴
统计图的Y轴组件也比较特别。如果系统找不到Y轴组件，系统就会自动产生一个。所以很多时候不需要加入，除非有以下四个需求：
a. 显示Y轴名称
b. 需要隐藏Y轴（比如饼图或雷达图）
c. 需要显示或隐藏Y轴分隔线
d. Y轴不是数值，需要配置Y轴类型。
当需要隐藏Y轴的时候，我们需要在设计器中设置Y轴的可视为“否”
![image.png](https://upload-images.jianshu.io/upload_images/12920178-99249fd9160e757c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
5. 色标
![image.png](https://upload-images.jianshu.io/upload_images/12920178-2080e8f249979714.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

色标用来定义数据和颜色的映射关系，加入色标组件后，统计图会根据数据值的大小来决定绘制项的颜色。
色标的类型分为连续色标和离散色标。连续色标需要定义以下四个关键属性：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-2da304ce0e657fe7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
那么统计图绘制时会根据当前值的大小在色标定义中线性插值产生出对应的颜色。如果要映射到多段颜色上，目前的做法是在色标底色或者色标高色中输入逗号分隔的多个颜色，如'red,white,blue'。
对于离散色标，需要定义离散数据范围：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-3de7d20483785628.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
其中的gt代表大于，lt代表小于，lte代表小于等于。
6. 地理坐标系统
地理坐标系统用来定义地图信息，例如地理区域范围，是否用百度地图，是否支持缩放平移等信息。凡是系统数据需要指定经纬度的地图统计图，都需要向统计图（区域）组件中添加地理坐标系统组件。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-a18372d58ff40f64.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在没有采用百度地图的情况下，通过修改该组件的背景色或样式配置中的控件背景色来控制地图的基本颜色。采用百度地图则不应该设置任何背景值。也可以通过该组件修改地图边界的颜色和宽度，如下：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-1e650a15d9281ea5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

7. 柱状图系列
代表柱状图中的一个数据系列，它的值和X轴值形成了X-Y数据对。举个例子，如果X轴是学生名字，柱状图系列下是对应的语文成绩，那么就会形成了X轴是学生名字，Y轴是语文成绩的柱状图；如果还要同时对比数学成绩，就需要再添加一个柱状图系列的列头。
我们常常要配置柱状图的填充色，修改方法就是修改对应柱状图序列的样式配置对话框里的控件背景色。
可以配置柱状图的宽度，参考下图红色框内的配置项：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-d86eb439e2bdc5c3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

8. 线图系列
代表折线图中的一个数据系列，它的值和X轴值形成了X-Y数据对。举个例子，如果X轴是学生名字，线图系列下是对应的语文成绩，那么就会形成了（X学生名字，Y语文成绩）的数据点连接折线；如果还要同时对比数学成绩，就需要再添加一个线图系列的列头，就会分别形成语文成绩折线和数学成绩折线两条折线。
折线颜色可以通过线图序列的样式配置对话框里的控件背景色进行修改。
9. 饼图系列
饼图里通常用来进行百分比对比。饼图系列下面的值需要的是原始值而不是百分比值。
修改饼图中各部分的颜色需要修改对应的X轴数据的样式配置对话框里的控件背景色。
饼图的常用配置项还有内外半径：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-e526bd6dd2dbc2d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

10. 系列
暂时把不常用的**漏斗图**和**雷达图**用系列组件来控制。漏斗图和饼图从概念上是一致的，都是用面积来表达数据的大小。而雷达图可以认为是线图的X轴弯曲变形的表现。
11. 地图系列
地图系列表述的是地理区域所对应的值，比如说，各省份销量数据，每个省份（地理区域）对应一个值，再比如说，北京市各区流动人口数，每个区对应一个值。MisShop目前的版本仅支持全国各省和北京各区。使用了地图系列的统计图如下所示：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-e441ff48ee9aa988.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
和地理坐标系统组件对比一下，虽然都可以出现地图，但是地图系列的功能比较单一，优点是不需要指定经纬度数据，只要X轴数据给区域名称即可。事实上，应用了地图系列的统计图底层实现会自动产生内部的一个地理坐标系统组件。
可以
12. 坐标系列及散点系列
坐标系列就是经度系列或者纬度系列。在地图散点图应用中，地理坐标组件和坐标系列以及散点系列是三位一体，一个也不能少。地理坐标组件是放在统计图数据区之外的，而坐标系列和散点系列则是统计图数据区的列头。我们要求坐标系列在X轴系列和散点系列之间，也就是说，X轴是第一列，经度是第二列，纬度是第三列，第四列往后是散点系列，也就是业务数据。散点的颜色通常需要色标组件来配合定义。
13. X轴
X轴是强制要求存在的组件，必须放在统计图数据区内部的第一行第一列。
14. 统计图数据区
统计图数据区是强制要求存在的统计图子组件，这个组件内部定义了统计图的数据部分。
三、统计图一览
1. 柱状图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-5a0d3149cb006bf1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2.堆积柱状图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-79f2ff93e02ad05d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
分别在两个柱状图系列的配置对话框里将“是否堆积”设为“是“，则产生本图效果。堆积图利于分析个体汇总数据。
3. 折线图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-1a80a73ee27dca77.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4. 面积图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-eab1b6f8e3f927d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
将两个系列的是否堆积和是否面积均设为“是”，则得到堆积面积图
5.饼图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-5d21c33937575dc1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
饼图只能有一个饼图系列。
6. 漏斗图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-bbacef69de1c6b20.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
漏斗图只能有一个系列。
7.雷达图
![image.png](https://upload-images.jianshu.io/upload_images/12920178-a50fadb211d2af3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
雷达图其实就是折线图的变形
8. 地图1
![image.png](https://upload-images.jianshu.io/upload_images/12920178-ba00ddb6c431248b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
9.地图2
![image.png](https://upload-images.jianshu.io/upload_images/12920178-3e649e4215cff7fd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
10. 地图3
![image.png](https://upload-images.jianshu.io/upload_images/12920178-05253cd06a9933b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
四、关于鼠标Tooltip提示
统计图上的Tooltip通常都是要显示系列名称，有时候还需要显示系列的值，特殊情况下，需要显示多个值。
不管哪种统计图，缺省都是有Tooltip提示的。如果缺省的Tooltip不能满足需求的话，就需要自定义Tooltip的格式化参数：
位置在整个统计图（区域）控件的属性配置页，如下：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-18409c603336ffe3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个格式化Tooltip的输入可以是一个字符串模板，也可以是一个javascript ES6函数。绝大多数情况下，用字符串模板就够用了。
说明如下：
模板变量有 `{a}`, `{b}`，`{c}`，`{d}`，`{e}`，分别表示系列名，数据名，数据值等。 有时候会有多个系列的数据，此时可以通过 `{a0}`, `{a1}`, `{a2}` 这种后面加索引的方式表示系列的索引。 不同图表类型下的 `{a}`，`{b}`，`{c}`，`{d}` 含义不一样。 其中变量`{a}`, `{b}`, `{c}`, `{d}`在不同图表类型下代表数据含义为：

*   折线（区域）图、柱状（条形）图、K线图 : `{a}`（系列名称），`{b}`（类目值），`{c}`（数值）, `{d}`（无）

*   散点图（气泡）图 : `{a}`（系列名称），`{b}`（数据名称），`{c}`（数值数组）, `{d}`（无）

*   地图 : `{a}`（系列名称），`{b}`（区域名称），`{c}`（合并数值）, `{d}`（无）

*   饼图、仪表盘、漏斗图: `{a}`（系列名称），`{b}`（数据项名称），`{c}`（数值）, `{d}`（百分比）
事实上，"{b}:{c}"是最最常用的一个格式化Tooltip参数值。
MisShop统计图中百度地图示例给出了一个ES6函数式格式化Tooltip，仅供参考：
"{(param)=>{return param.name + \' :<br/>降雨量:    <font color=\"orange\">\' + param.value[2] +\' </font><br/> 报警内容:   \'+param.value[3] ;};}"
效果如下：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-ab7c2f7d99cd5db2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们可以看出这个函数接受一个参数，这个参数携带了一行散点数据的所有信息。同时我们也看到换行和指定文本颜色都是可以通过html语法来控制的。其实不只是函数返回值，字符串模板中也同样可以掺杂html标签。
五、关于标签格式化
是否显示标签以及标签的格式化都是在各种系列的控件配置里。
![image.png](https://upload-images.jianshu.io/upload_images/12920178-ebba435320ac8d19.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

目前仅支持字符串模板，语法和变量如下：
标签字符串模板 模板变量有：

{a}：系列名。
{b}：数据名。
{c}：数据值。
{@xxx}：数据中名为'xxx'的维度的值，如{@product}表示名为'product'` 的维度的值。
{@[n]}：数据中维度n的值，如{@[3]}` 表示维度 3 的值，从 0 开始计数。
示例如上图所示："{b}:{@[2]}"。
六、关于统计图点击后的链接
目前仅支持散点图、地理坐标散点图、饼图及漏斗图。操作方法是将X轴下Data的控件从默认改为链接控件。
