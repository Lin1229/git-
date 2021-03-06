#   HTML 学习笔记

-----

## 1.html基础(HyperText Markup Language)
> 1. \<!DOCTYPE html>  声明为html5文档 (不区分大小写)
> 2. 标签：由<>尖括号包围关键词，分为开始标签 <标签> 和结束标签 </标签>
> 3. 元素：<开始标签>  内容   </结束标签>
> 4. 保存html文件时使用.htm或.html扩展名

## 2.元素
> 1. 元素以**开始标签**起始，以**结束标签**终止
> 2. 某些元素为**空元素**，在**开始标签**中终止
> 3. \<body>...</body> 定义html文档主体
> 4. \<html>...</html> 定义整个html文档

## 3.属性
> 1. html元素可以设置**属性**，一般描述在**开始标签**中
> 2. 属性可以在元素中**附加信息**，一般以值对形式出现 name="value"
> 3. 属性值应使用双引号包裹，但值中带有双引号时使用单引号包裹 ，如name='John"ShotGun"Nelson'
> 4. 适用于大多数元素的属性
> ```
> 1.class   为元素定义一个或多个类名
> 2.id      定义元素唯一id
> 3.style   规定元素行内样式
> 4.title   描述元素额外信息
> ```

## 4.标题
> 1. 通过\<h1>~\<h6>定义标题 (\<h1>定义最大标题，\<h6>定义最小标题)
> 2. \<hr> 创建分割线  无结束标签
> 3. 使用\<!-- message -->插入注释，增加可读性

## 5. 段落
> 1. \<p> 定义一个段落
> 2. \<br> 在不产生新段落的情况下换行
> 3. html中所有连续的空格和换行都会被算作一个空格

## 6. 文本
> 1.文本格式化标签
> ```
> 1.<b>             定义粗体文字
> 2.<strong>        定义加重语气
> 3.<i>             定义斜体文字
> 4.<em>            定义着重文字
> 5.<small>         定义小号文字
> 6.<sub>           定义下标字
> 7.<sup>           定义上标字
> 8.<ins>           定义插入字（下划线）
> 9.<del>           定义删除字
> ```
> 2.计算机输出标签
> ```
> 1.<code>           定义计算机代码
> 2.<kbd>            定义键盘码
> 3.<samp>           定义计算机代码样本
> 4.<var>            定义变量
> 5.<pre>            定义预格式文本(格式与源码中一致，不忽略空格)
> ```
> 3.引文引用及标签定义
> ```
> 1.<abbr>              定义缩写 <abbr title="mesage"> 缩写 </abbr>
> 2.<address>           定义地址 
> 3.<bdo>               定义文字方向 <bdo dir ="rtl"> 文字 </bdo>   (rtl:right to left    ltr:left to right)
> 4.<blockquote>        定义长引用
> 5.<q>                 定义短引用
> 6.<cite>              定义引用  定义作品标题
> 7.<dfn>               定义一个定义项目（对文本进行格式化）
> ```

## 7. 链接

> 1. 通过\<a>设置**超文本链接**，可以是文字也可以是图片，点击跳转到新文档或当前文档的某个位置
> 2. \<a href="url"> 链接文本 \</a>  href属性描述链接目标
> 3. \<a href="url" target="_blank" > 链接文本 \</a> 在新窗口打开链接
> 4. id属性可用于创建一个书签标记
> ```
> 1.在HTML文档中插入ID:
> <a id="tips">有用的提示部分</a>  
> 2.在HTML文档中创建一个链接到"有用的提示部分(id="tips"）"：
> <a href="#tips">访问有用的提示部分</a>  
> 3.从另一个页面创建一个链接到"有用的提示部分(id="tips"）"：
> <a href="https://www.runoob.com/html/html-links.html#tips"> 访问有用的提示部分</a> 
> ```
>
> 

## 8.头部
> 1. \<head> 元素包含了所有头部标签元素，可以插入某些元素标签，如
> ```
> <title>, <style>, <meta>, <link>, <script>, <noscript> 和 <base>。
> ```
> 2. \<title> 定义html文档标题，一个html文档必须具有title
> ```
> 1.定义了浏览器工具栏的标题
> 2.定义了添加到收藏夹时的标题
> ```
> 3. \<base> 指定所有链接的地址
> ```
> <base href="//www.runoob.com/images/" target="_blank">  指定所有链接的默认地址以及target属性
> ```
> 3. \<link> 定义文档与外部资源之间的关系,通常用于引用外部css样式文件
> ```
> <head>
> <link rel="stylesheet" type="text/css" href="mystyle.css">
> </head>
> ```
> 4. \<style> 定义html文档样式文件引用地址
> ```
> <head>
> <style type="text/css">
> body {background-color:yellow}设置背景颜色为黄色
> p {color:blue}段落颜色为蓝色
> </style>
> </head>
> ```
> 5. \<meta>标签描述基本元数据，不在页面上显示
> ```
> <meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">  定义关键词
> <meta name="description" content="免费 Web & 编程 教程">              定义描述内容
> <meta name="author" content="Runoob">                               定义网页作者
> <meta http-equiv="refresh" content="30">                            每30s刷新网页
> ```

## 9.CSS

> 1.**CSS**(Cascading Style Sheets) 用于渲染html元素标签的样式
> 2.CSS可以用以下方式添加到html中
>
> ```
> 1.内联样式：在html元素中使用style属性
> <p style="color:blue;margin-left:20px;">这是一个段落。</p>  改变段落的颜色和左边距
> 
> 2.内部样式表：在html文档头部使用style
> <head>
> <style type="text/css">
> body {background-color:yellow;}
> p {color:blue;}
> </style>
> </head>
> 
> 3.外部引用：使用外部css文件
> <head>
> <link rel="stylesheet" type="text/css" href="mystyle.css">
> </head>
> ```
> ### 实例
> 1. **背景颜色**
> * style="background-color：yellow；" 定义元素的背景颜色
> 2. **字体颜色大小**
> * style="font-family：arial；color：red；font-size：20px；" font-family字体，color字体颜色，font-size字体大小
> 3. **对齐方式**
> * style="text-align:center;"  居中对齐

## 10.图像

> 1. 使用\<img> 定义一个图像，为空标签，无闭合标签
> 2. \<img src="url" alt="some_text">
> * url为图片地址
> * alt为图片文本，当图片无法显示时将显示文本
> 3. \<img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228"> 指定图像高度和宽度

## 11.表格
> 1.由\<table> 标签定义表格\<tr>定义行 \<td>定义表格内数据 \<th>定义表头 \<caption>定义标题
> 如：
>
> ```
> <table border="1">        border="1"定义边框，数字为边框厚度，0为无边框
> <caption> 标题 </caption>        定义表格标题
> <tr>                            表头
> <th>Header 1</th>
> <th>Header 2</th>
> </tr>
> <tr>                            第一行
> <td>row 1, cell 1</td>
> <td>row 1, cell 2</td>
> </tr>
> <tr>                            第二行
> <td>row 2, cell 1</td>
> <td>row 2, cell 2</td>
> </tr>
> </table>
> ```
> <table border="1">      
> <caption> 标题 </caption>        
> <tr>                            
> <th>Header 1</th>
> <th>Header 2</th>
> </tr>
> <tr>                          
> <td>row 1, cell 1</td>
> <td>row 1, cell 2</td>
> </tr>
> <tr>                            
> <td>row 2, cell 1</td>
> <td>row 2, cell 2</td>
> </tr>
> </table>
> 2. 通过 colspan="" 和rowspan="" 元素定义跨行跨列单元格可以使用在\<th>或\<td>中
>
> ```
> <table border="1">
> <tr>
> <th>Name</th>                          
> <th colspan="2">Telephone</th>
> </tr>
> <tr>
> <td rowspan="2">Bill Gates</td>
> <td>555 77 854</td>
> <td>555 77 855</td>
> </tr>
> <tr>
> <td>555 77 854</td>
> <td>555 77 855</td>
> </tr>   
> </table>
> ```
> <table border="1">
> <tr>
> <th>Name</th>
> <th colspan="2">Telephone</th>
> </tr>
> <tr>
> <td rowspan="2">Bill Gates</td>
> <td>555 77 854</td>
> <td>555 77 855</td>
> </tr>
> <tr>
> <td>555 77 854</td>
> <td>555 77 855</td>
> </tr>   
> </table>
> 3. 表格内可以使用其他标签，如表格，段落，列表等
> 4. cellspacing="10" 设置单元格间距  cellpadding="10" 设置单元格边距

## 12. 列表

> 1.使用 \<ul> 创建无需列表 \<ol> 创建有序列表 \<li> 定义列表项
>
> ```
> <ol>
> <li>Coffee</li>
> <li>Milk</li>
> </ol>
> <ul>
> <li>Coffee</li>
> <li>Milk</li>
> </ul>
> ```
> <ol>                     
> <li>Coffee</li>
> <li>Milk</li>
> </ol>
> <ul>
> <li>Coffee</li>
> <li>Milk</li>
> </ul>
> 2. 不同类型的有序列表和无需列表（使用CSS）
> 
> ```
> <ol type="A"> 大写字母列表
> <ol type="a"> 小写字母列表
> <ol type="I"> 罗马数字列表
> <ol type="i"> 小写罗马数字列表
> <ul style="list-style-type:disc"> 圆点列表
> <ul style="list-style-type:circle"> 圆圈列表
> <ul style="list-style-type:square"> 正方形列表
> ```
> 3. 使用\<dl>标签创建自定义列表，\<dt>为列表项，\<dd>为列表项的定义
> ```
> <dl>
> <dt>Coffee</dt>
> <dd>- black hot drink</dd>
> <dt>Milk</dt>
> <dd>- white cold drink</dd>
> </dl>
> ```
> <dl>
> <dt>Coffee</dt>
> <dd>- black hot drink</dd>
> <dt>Milk</dt>
> <dd>- white cold drink</dd>
> </dl>

## 13.区块

> 1. 大多数html元素被定义为块级元素或内联元素
> * 大部分块级元素显示时会以新行开始，如\<h1>, \<p>,\<ul>, \<table>
> * 内联元素则不会以新行开始，如\<b>, \<td>, \<a>,\<img>
> 2. \<div>是块级元素，可组合其他html元素，无特定含义，与CSS一起使用可以设置大块内容的样式
>
> ```
> <div style="color:#0000FF">  
> <h3>这是一个在 div 元素中的标题。</h3> 
> <p>这是一个在 div 元素中的文本。</p> 
> </div>
> ```
> <div style="color:#0000FF">  
> <h3>这是一个在 div 元素中的标题。</h3>  
> <p>这是一个在 div 元素中的文本。</p> 
> </div>
>
>
> 3. \<span>元素是内联元素，可作为文本容器，同样无特殊意义，与CSS一起使用可以设置部分文本样式
>
> ```
> <p>我的母亲有 <span style="color:blue">蓝色</span> 的眼睛。</p>
> ```
> <p>我的母亲有 <font color="blue">蓝色</font> 的眼睛。</p>

## 14.布局

> 1. 使用\<div>元素来创造多个列，使用CSS来对元素定位
> ```
> <div id="menu" style="background-color:#FFD700;height:200px;width:100px;float:left;">
> <b>菜单</b><br>
> HTML<br>
> CSS<br>
> JavaScript
> </div>
> ```

## 15. 表单

> 1. 表单元素\<form>允许用户输入内容，通常使用的标签为输入标签\<input>，输入类型由以下属性定义
>
> * 文本域 \<input type="text">，输入字母数字等
>
> ```
> <form>
> First name: <input type="text" name="firstname"><br>
> Last name: <input type="text" name="lastname">
> </form>
> ```
> * 密码字段 \<input type="password">，字符将不会明文显示
>
> * 单选按钮 \<input type="radio">   单选
>
> * 复选按钮 \<input type="checkbox"> 多选
>
> * 提交按钮 \<input type="submit"> 将表单内容传送到另一个文件，action定义目标文件名
>
> ```
> <form name="input" action="html_form_action.php" method="get">
> Username: <input type="text" name="user">
> <input type="submit" value="Submit">
> </form>
> ```
> 2. \<select>下拉列表  \<option>定义可用选项，\<optgroup>将相关选项组合在一起
>
> ```
> <form action="">
> <select name="cars">
> <optgroup label="Swedish Cars">
> <option value="volvo">Volvo</option>
> <option value="saab">Saab</option>
> </optgroup>
> <option value="fiat" selected>Fiat</option>                    selected表示预选值
> <option value="audi">Audi</option>
> </select>
> </form>
> ```
> 3. \<testarea> 定义一个文本域，用于多行输入
>
> ```
> <textarea rows="10" cols="30">
> 我是一个文本框。
> </textarea>
> ```
> 4. \<label> 定义input元素的标签，点击文本时会自动跳转到相关的表单控件上
>
> ```
> <label for="male">Male</label>         for属性规定label与哪个表单绑定，指向表单id
> <input type="radio" name="sex" id="male" value="male">
> ```
> 5. \<fieldset> 对表单进行分组，\<legend>设置分组标题，
> ```
> <form>
>   <fieldset>
>     <legend>Personalia:</legend>
>     Name: <input type="text"><br>
>     Email: <input type="text"><br>
>     Date of birth: <input type="text">
>   </fieldset>
> </form>
> ```
> 6. \<botton> 定义一个按钮，与input按钮不同的是，botton可以放置内容，如文本或图像
> ```
> <button type="button" onclick="alert('你好，世界!')">点我!</button>
> ```

## 16. 框架

> 1. 通过使用\<iframe>可以在同一个窗口显示多个页面
>
>    ```
>    <iframe src="URL"></iframe> src指向网页地址
>    <iframe src="demo_iframe.htm" width="200" height="200"></iframe>   设置长宽
>    <iframe src="demo_iframe.htm" frameborder="0"></iframe>           设置边框
>    ```
>
> 2. 显示目标页面
>
>    ```
>    <iframe src="demo_iframe.htm" name="iframe_a"></iframe>
>    <p><a href="http://www.runoob.com" target="iframe_a">RUNOOB.COM</a></p>
>    target指向iframe_a，点击时会在iframe框架中显示目标网页
>    ```

## 17. 颜色

> 1. html颜色由一个十六进制符号表示，这个符号由红绿蓝颜色的值组成(RGB)。
> 2. 每种颜色最小值为0（十六进制#00），最大为255（十六进制#FF）
>
> * 红#FF0000 绿#00FF00 蓝#0000FF 黑#000000 白#FFFFFF

## 18. 脚本

> 1. 插入javaScript使html页面更具交互性
>
> 2. 使用\<script>元素插入脚本，\<noscript>提供浏览器无法支持脚本时的替代内容
>
> ```
> <script>
> document.write("Hello World!")
> </script>
> <noscript>抱歉，你的浏览器不支持 JavaScript!</noscript>
> ```

## 19. 字符实体

>1. 在html中某些字符是预留的，如小于号\<和大于号\>，浏览器会误认为标签。若想使用预留字符，就需要使用字符实体
>
>2. **实体字符对大小写区分敏感**
>
>3. 字符实体：使用```&entity_name;```实体名称或```&#entity_number;```实体编号形式
>
>4. 不间断空格：html中大于一个的空格会被自动合并为一个，如需增加空格数，则要使用 \&nbsp; 实体字符
>
>5. 字符表
>
>   ```
>   	空格	        &nbsp;	        &#160;
>   <	小于号	       &lt;	           &#60;
>   >	大于号	       &gt;	           &#62;
>   &	和号	       &amp;	        &#38;
>   "	引号	       &quot;	        &#34;
>   '	撇号 	       &apos; (IE不支持) &#39;
>   ￠	分	       &cent;	        &#162;
>   £	镑	        &pound;          &#163;
>   ¥	人民币/日元	 &yen;	          &#165;
>   €	欧元         &euro;	        &#8364;
>   §	小节	       &sect;	        &#167;
>   ©	版权	       &copy;	        &#169;
>   ®	注册商标	  &reg;            &#174;
>   ™	商标	       &trade;	        &#8482;
>   ×	乘号	       &times;	        &#215;
>   ÷	除号	       &divide;	        &#247
>   ```

## 20. URL

> 1. url是一个网页地址，可以由字母组成baidu.com 或ip地址组成192.68.1.1
>
> 2. 统一资源定位器（url）语法规则
>
>    ****
> 例：   http://www.runoob.com/html/html-tutorial.html
>              **``` scheme://host.domain:port/path/filename```**
>
>    * scheme - 定义因特网服务的类型。最常见的类型是 http
>    * host - 定义域主机（http 的默认主机是 www）
>    * domain - 定义因特网域名，比如 runoob.com
>    * :port - 定义主机上的端口号（http 的默认端口号是 80）
>    * path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
>    * filename - 定义文档/资源的名称
>    
> 3. 常见scheme
>    |scheme|传输协议|类型|
>    |---|----|-----|
>    | http  | 超文本传输协议     | 以 http:// 开头的普通网页。不加密。 |
>    | https | 安全超文本传输协议 | 安全网页，加密所有信息交换。        |
>    | ftp   | 文件传输协议       | 用于将文件下载或上传至网站。        |
>    | file  |                    | 您计算机上的文件。                  |
>    
> 4. **URL只能使用ascll字符集**，但其常常包含字符集以外的字符，所以url必须转化为有效的ascll格式
>
>    * 使用%跟随两个十六进制数来替换非ascll字符