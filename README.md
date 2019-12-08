# WebStack-Plus
WebStack的魔改版

欢迎关注微信订阅号:GeekS356,跟进项目进度.

## 版本更新日志

### 静态 魔改版本
https://github.com/CrazyBoyM/WebStackPage.github.io

原作@viggo

1.加入了多元搜索框(基于@seogo编写的版本做了魔改)

2.加入了图标按需加载(懒加载 lazyload)

3.随便弄了个简单的天气(天气网)

4.右下角聊天室(Gitter WebStack room)

### Laravel 魔改版本
https://github.com/hui-ho/WebStack-Laravel

原作@hui-ho

1.加入了多元搜索框(基于@seogo编写的版本做了魔改)

2.加入了图标按需加载(懒加载 lazyload)

3.随便弄了个简单的天气(天气网的iframe)

4.右下角聊天室(Gitter WebStack room)

### typecho 版本
原作@seogo

因为@seogo大大没有开源这个版本到Github,所以暂不提供该版本的魔改

### wordpress 版本
因为wordpress过于臃肿,所以暂不提供该版本的魔改

有意向做的朋友可以issue里发下自己维护的WP魔改版本链接,会附于此处

## 魔改文档
(只记录功能相关,不记录界面样式的魔改)

### 搜索引擎
下载[search.js](https://github.com/CrazyBoyM/WebStackPage.github.io/tree/master/assets/js/search.js)和[search.css](https://github.com/CrazyBoyM/WebStackPage.github.io/blob/master/assets/css/search.css)两个文件,放入对应的/assets/js/和/assets/css/文件夹,然后在需要的页面引用即可.
```html
<link rel="stylesheet" href="../assets/css/search.css">
<script type="text/javascript" src="../assets/js/search.js"></script>
```
默认写了天气,不需要请自行打开search.js删除这行
```javascript
document.writeln(" <iframe width=\"100%\"  height=\"60\"  frameborder=\"0\" allowtransparency=\"true\" src=\"//i.tianqi.com/index.php?c=code&id=12&icon=1&num=5&site=12\"></iframe>");
```
### 懒加载
Demo:
```html
<script src="../assets/js/jquery-1.11.1.min.js"></script>
<script src="../assets/js/jquery.lazyload.js"></script>
<script type="text/javascript" charset="utf-8">
	      $(function() {
	          $("img").lazyload({ 
			  placeholder : "../assets/images/loading.png",
	                 effect: "fadeIn"
	           });  
	      });
</script>
 <img  data-original="原来src处的值" class="img-circle" width="40">
```
### 天气
天气网方案:

默认写在了search.js中,不需要请自行删除

单独插入:
```html
 <iframe width="100%"  height="60"  frameborder="0" allowtransparency="true" src="//i.tianqi.com/index.php?c=code&id=12&icon=1&num=5&site=12"></iframe>
```
### 聊天室
用Gitter的,可以自行更换其他方案

页尾插入
```html
<script>
  ((window.gitter = {}).chat = {}).options = {
   
    room: 'GeekS356/WebStack'
  };
</script>
<script src="https://cdn.bootcss.com/gitter-sidecar/1.3.3/sidecar.js" async defer></script>
```
