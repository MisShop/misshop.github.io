MisShop制作的软件系统最终都是以网页形式呈现给用户使用，用户和网页的交互都是依赖Javascript来进行数据的收集、整理、传输和反馈的。MisShop开发平台根据需要对常见的前端数据结构基于Javascript语言进行了封装，本文主要讲述了前端对键值对的封装细节和函数接口。
事实上每一个前端变量集都会在网页的javascript环境中对应一个javascript对象，那么一个键值对类型的前端变量集，它在Javasript环境中就会对应一个Map类型的Javascript对象。本文中所谈到的Map,是一个简称，包括这里说的Map类型，全名叫window.Mis.MapObj。如果我们需要在设计页面中用到键值对类型的前端数据集，就有必要了解一下Map类型所支持的函数接口； 另外，如果我们需要定制custom.js或者我们需要在某个控件的值改变事件或者某个按钮的点击事件中写一个复杂的逻辑脚本，就可能需要一个键值对或哈希表来帮忙进行数据的计算和处理，这时候就需要用到本文中的内容。
1. 创建一个Map
我们固然可以用javascript语言标准new window.Mis.MapObj来产生一个Map对象，但是这不是我们推荐的方法，因为在未来的升级版本里window.Mis.MapObj可能会消失，但是下面我们推荐的方法会一直存在
-window.Mis.Map.create()
上面的函数调用会产生一个新的Map对象，代表了一个空的键值对列表。
-window.Mis.Map.parse(str)
该函数调用会产生一个新的键值对列表，它接受一个**JSON格式**的字符串参数，并解析该字符串，将解析结果加入键值对列表并返回
示例
···
var map = window.Mis.Map.parse('{"name":"张三", "age":"18", "gendor": "女","tel":"13521345678","score":[100,80,90]}');
···
-window.Mis.Map.createByCells(keys,values)
这个函数用来将扩展前的单元格名对应的内容，组成扩展后的键值对。参数keys和values都是单元格的名字， 用户不大可能在Javascript环境中调用它，这个函数在生成页面内容的时候由系统自动调用，下面的截图中给出一个应用：
![image.png](https://upload-images.jianshu.io/upload_images/12920178-e560106481ee6767.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
在上图中，A1其实是一个扩展，代表了多个用户名，B1也随之扩展代表了相对应的多个部门值；随后定义的键值对变量集则收集了这两列值并形成了对应的键值对列表。
-window.Mis.Map.parseKVArr(keys,values)
参数keys和values分别是键的数组和值的数组， 函数调用后按次序形成一个键值对列表并返回。
```
var keys = ["name","age", "gendor"];
var values = ["张三",18, "女"];
var map = window.Mis.Map.parseKVArr(keys,values);
```
2. 向键值对列表添加新项
-put(k,v)
put是Map类型的成员函数，用来添加新的键值对。
示例：
```
var map = window.Mis.Map.create(); 
map.put("name","张三");
map.put("age",18);
```
3. 删除指定key对应的键值对
-remove(key)
示例
```
var map = window.Mis.Map.create(); 
map.put("name","张三");
map.put("age",18);
map.put("yearOfBirth",2001);
map.remove('age');
```
4. 获取指定Key的值
-get(key)
