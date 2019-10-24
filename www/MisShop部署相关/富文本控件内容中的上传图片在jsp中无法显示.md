这个原因是由于网站的jsp网页没有直接放在webroot下造成的。
目前的支持方式是：
打开jsp源代码，翻到最下面找到</body>标签，然后把下面的函数复制到</body>前面，函数调用传递的第二个参数是jsp相对于webroot的路径相对关系。
```javascript

<script>
function patchDataImage(parentId, prefix){
	var parent = null;
	if(parentId){
		parent = $('#'+parentId);
	}else{
		parent = $(document);
	}
	if(parent && parent.length>0){
		var imgs = parent.find('img');
		imgs.filter(function(){
			return 0===$(this).attr('src').indexOf('data/attachment');
		}).each(function(){
			$(this).attr('src', prefix+$(this).attr('src'));
		});
	}
}

patchDataImage(undefined, '../../');
</script>
```
