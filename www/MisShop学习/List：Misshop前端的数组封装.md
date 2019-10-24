MisShop制作的软件系统最终都是以网页形式呈现给用户使用，用户和网页的交互都是依赖Javascript来进行数据的收集、整理、传输和反馈的。MisShop开发平台根据需要对常见的前端数据结构基于Javascript语言进行了封装，本文主要讲述了前端对数组的封装细节和函数接口。
在讲述之前，首先谈一下我们为什么需要了解这些内容，以及我们可能会在什么地方用到本文提到的内容。
在[https://www.jianshu.com/p/1b775f80fedb](https://www.jianshu.com/p/1b775f80fedb)
这篇文章中，我们谈到过后端变量集和前端变量集，事实上每一个前端变量集都会在网页的javascript环境中对应一个javascript对象，那么一个数组类型的前端变量集，它在Javasript环境中就会对应一个List类型的Javascript对象。本文中所谈到的List,是一个简称，包括这里说的List类型，全名叫window.Mis.ListObj。如果我们需要在设计页面中用到数组类型的前端数据集，就有必要了解一下List类型所支持的函数接口； 另外，如果我们需要定制custom.js或者我们需要在某个控件的值改变事件或者某个按钮的点击事件中写一个复杂的逻辑脚本，就可能需要一个数组来帮忙进行数据的计算和处理，这时候就需要用到本文中的内容。
1. 创建一个List
我们固然可以用javascript语言标准new window.Mis.ListObj来产生一个List对象，但是这不是我们推荐的方法，因为在未来的升级版本里window.Mis.ListObj可能会消失，但是下面我们推荐的方法会一直存在
-window.Mis.List.create()
上面的函数调用会产生一个新的List对象，代表了一个空的数组。
-window.Mis.List.parse(str)
上面的函数接受一个用逗号作为分隔符的字符串参数，调用后会产生一个新的List对象，这个List对象的内部数组是解析了字符串参数后的数组，通常不为空。示例：window.Mis.List.parse('1,2,3,4,5') 或者window.Mis.List.parse('[1,2,3,4,5]')。
再如window.Mis.List.parse(’张三,李四,王五’), 也可以是满足JSON格式数组语法的复杂字符串，如
```
window.Mis.List.parse('[{"名字":"张三", "性别":"男", "电话":"13521345678"}, {"名字":"李四", "性别":"男", "电话":"13621345678"}, {"名字":"王五", "性别":"女", "电话":"13721345678"} ]’)
```
2. 向数组中添加元素
一旦创建了List，就可以向其中添加元素了，我们有必要补充一点，MisShop的List是不支持重复元素的，所以不要添加相同的内容。
-add( v )
add方法是List类型的成员方法，接受一个参数，调用成功后这个参数会作为新的数组元素追加到数组中。
示例：
```
var lst = window.Mis.List.create(); lst.add(1); lst.add(2);
var lst2 = window.Mis.List.parse('张三, 李四'); lst2.add("王五")
```
3. 从数组中删除元素
-remove( v )
remove方法是List类型的成员方法，接受一个参数v，调用成功后数组中值为v的元素被删除。
示例：
```
var lst2 = window.Mis.List.parse('张三, 李四'); lst2.add("王五");lst2.remove("李四")
```
4. 按索引获取元素值
-get(index)
get方法是List类型的成员方法，接受一个参数index，调用成功后返回数组中索引为index的元素。
示例：
```
var lst2 = window.Mis.List.parse('张三, 李四'); 
console.log(lst2.get(1));//输出'李四'
```
5. 获取数组的大小
-size()
调用后返回数组的大小
```
var lst =window.Mis.List.parse('[1,2,3,4,5]'); console.log(lst.size()); //输出5
```
6. 判断是否存在某个值
-contains(v)
接受一个参数v, 如果数组中包含该值则返回true， 如果不包含则返回false
示例：
```
var lst2 = window.Mis.List.parse('A, B，AB，O'); if(!lst2.contains('RH'))lst2.add('RH');
```
7. 转为字符串
-toString()
将数组内容转为用[]包裹并用逗号分隔的字符串
```
var lst = window.Mis.List.create(); lst.add(1); lst.add(2);console.log(lst.toString())//输出[1,2]
```
8. 转为JSON字符串
-toJson()
将数组内容转为JSON格式的字符串, 对于元素为字符串类型或者复合结构类型的数组，推荐用这个函数而不是上面的函数。
9.判断两个数组是否严格相等
-equals(list2)
接受一个参数list2, 这个参数必须也是一个List类型才能进行比较，如果数组大小和数组内容都依次相同则返回true，否则返回false
示例：
```
var lst = window.Mis.List.create(); lst.add(1); lst.add(2);
var lst2 = window.Mis.List.parse('[1,2]');
console.log(lst.equals(lst2);//输出true
```
