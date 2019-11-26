# 我的HTML模板
```html
<!doctype html>          /* 感叹号！，无空格*/   
<html>              
<head>
    <meta charset="utf-8">   
    <title>网页标签</title>
    <style>
        body{
            background-color: white;
            color: #ff0000;
            }
        #bar{}          /*对id名为bar的元素定义样式*/      /**/
        #bar.foo1{}     /*对 id 名为 bar 且 class 名为 foo1 的元素定义样式*/
        #bar,.foo1{}    /*对 id 名为 bar 和 所有 class 名为 foo1 的元素定义样式*/
        p.foo1{}        /*对所有段落中 foo1 类元素定义样式*/
        .foo1,.foo2{}   /*对所有 foo1、foo2 类元素定义样式*/
        div a{}         /*对所有 div 中所有 a 元素定义样式*/   /*空格表示包含关系*/
        div p a{}       /*对所有 div 所有段落中 a 元素定义样式*/
    </style>
</head>
<body>
    <h1 id="bar" class="foo1 foo2">   一级标题    </h1>
    <p class="foo1 foo2" title="鼠标位于段落上时的说明或将要链接的网址">     段落    </p>
    <p class="foo1" title="鼠标位于段落上时的说明或将要链接的网址">     段落    </p>
    <div>
        <p> 
            <a href="#">  </a>
        </p>
        <h3>
            <a href="#">  </a>
        </h3>
    </div> 
    <a href="链接url">   链接名字    </a>
    <img src="图片url" alt="未显示图片时的说明">
    <!--<img>的 src 和 alt 属性必不可少，有必要的话可以为它加上 title 属性说明图片或链接到新URL -->
</body>
</html>
```
---
*     知识补充：

1. Web服务器存储并提供由html和CSS创建的网页，浏览器获取网页并根据html和CSS显示网页的内容

2. 通过HTML，我们利用标记来标识内容提供结构。匹配标记以及它们包围的内容称为 __*元素*__

3. ../表示返回上级目录，用/表示父、子文件夹的关系

4. 短引用用`<q>`，长引用用`<blockquote>`，`<q>`元素的文本内嵌于段落或标题中，`<blockquote>`元素的文本自成一段且缩进，前后各有一个换行

5. 块元素通常用作web页面的主要构建模块，内联元素往往用来标记小段内容，例：
   - 块元素：`<h1> <a> <ul> <li> <ol> <blockquote> <p>`
   - 内联元素：`<em> <a> <img> <q>`

## 构建列表

通常将列表与段落隔开，例：
```html
   <p>四季之景大不同</p>
    <ul>(/<ol>)
        <li>春暖花开</li>
        <li>夏日炎炎</li>
        <li>秋高气爽</li>
        <li>冬雪皑皑</li>
    </ul>(/</ol>)
```

Web服务中，从根目录返回的默认文件通常命名为“index.html”或“default.htm”

相对路径只用来链接同一网站内的页面，而URL通常用来链接其他网站。

Web服务器的默认端口为80，出现的其他端口（如8000）可能为测试服务器。

浏览器从计算机本地读取文件时会使用file协议，例如。文件URL“file:///chapter4/starbuzz/index.html”(3个“/”)

### 使用id属性为`<a>`创建目标，链接到标题或段落...等特定元素

1.为元素创建标记，例：

`<h2 id="chai">Chai Tea $2.15</h2>`

2.构建`<a>`元素，指向目标元素

`<a href="index.html#chai">`

__id 一定要以字母开头__，后面可以是任意字母、数字、横线、下划线、冒号或点号，__但不能加空格__，以免有的服务器识别错误

### 链接到新窗口
给链接加`target="_blank"`属性即可

`http(s)://starbuzzcoffee.com/index.html`
`..协议 ......... 网站名 ........绝对路径`

### 图像格式的选择

|类别|JPEG|PNG|GIF|
|---|---|----|----|
|适用对象|照片和复杂图像使用|单色图像、logo、和几何图形使用|单色图像、logo、和几何图形使用|
|颜色种类|1600万|上百万种（PNG-8/24/32）|256种|
|格式损失|有|无|无|
|透明度|不支持|支持|支持|
|文件大小|比较小|一般比相应的JPEG大，比相应的GIF可能大/小|往往比相应的JPEG大|
|动画|不支持|不支持|支持|

### 样式表

通常会创建后缀名为“.css” 的样式表文件，为web页面的“.html”文件提供样式规则，“.css” 样式表文件只包含CSS,不能包含HTML，不能有`<style>`标记。在HTML中用`<link>`元素链接到外部样式表，例（记样式表文件为loung.css）：
`<link type="text/css" rel="stylesheet" href="loung.css">`

HTML5中，不再需要 type= "text/css" 这个属性

### 特定性冲突

若有两个及以上的选择器有相同的特定性而冲突，则依样式表文件中规则的顺序取最后者，例：
段落属于三个类：
`<p class="greentea raspberry blueberry">`
```css
p{color:black;}
.greentea{color:green;}
p.greentea{color:green;}
p.respberry{color:blue;}
p.blueberry{color:purple;}
```





























