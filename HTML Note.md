#   HTML 学习笔记

-----

## 1.html基础
> 1. \<!DOCTYPE html>  声明为html5文档 (不区分大小写)
> 2. 标签：由<>尖括号包围关键词，分为开始标签 <标签> 和结束标签 </标签>
> 3. 元素：<开始标签>  内容   </结束标签>
> 4. 保存html文件时使用.htm或.html扩展名

## 2.元素
> 1. <body>...</body> 定义html文档主体
> 2. <html>...</html> 定义整个html文档

## 3.属性
> 1. 属性可以在元素中附加信息，一般以值对形式出现 name="value"
> 2. 属性值应使用双引号包裹，但值中带有双引号时使用单引号包裹 ，如name='John"ShotGun"Nelson'
> 3. 适用于大多数元素的属性
> ```
> 1.class   为元素定义一个或多个类名
> 2.id      定义元素唯一id
> 3.style   规定元素行内样式
> 4.title   描述元素额外信息
> ```

## 4.标题
> 1. 通过\<h1>~\<h6>定义标题 (\<h1>定义最大标题，\<h6>定义最小标题)
> 2. \<hr> 创建分割线  无结束标签
> 3. 使用<!-- message -->插入注释，增加可读性

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

> 1.  \<a href="url"> 链接文本 \</a>  href属性描述链接目标
> 2. \<a href="url" target="_blank" > 链接文本 \</a> 在新窗口打开链接

## 8.头部
> 1. \<head> 元素包含了所有头部标签元素
> 2. \<title> 定义html文档标题
> ```
> 1.定义了浏览器工具栏的标题
> 2.定义了添加到收藏夹时的标题
> ```
>
> 3. \<base> 指定所有链接的地址
> ```
> <base href="//www.runoob.com/images/" target="_blank">  指定所有链接的默认地址以及target属性
> ```
> 3. \<link> 定义文档与外部资源之间的关系
> 4. \<style> 定义html文档样式文件引用地址
> 5. \<meta>标签描述基本元数据，不在页面上显示
> ```
> <meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">  定义关键词
> <meta name="description" content="免费 Web & 编程 教程">              定义描述内容
> <meta name="author" content="Runoob">                               定义网页作者
> <meta http-equiv="refresh" content="30">                            每30s刷新网页
> ```

## 9.CSS

> 1.CSS(Cascading Style Sheets) 用于渲染html元素标签的样式
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
> 1. 背景颜色
> * style="background-color：yellow；" 定义元素的背景颜色
> 2. 字体颜色大小
> * style="font-family：arial；color：red；font-size：20px；" font-family字体，color字体颜色，font-size字体大小
> 3. 对齐方式
> * style="text-align:center;"  居中对齐

## 10.图像

> 1. 使用\<img> 定义一个图像，无闭合标签
> 2. \<img src="url" alt="some_text">
> * url为图片地址
> * alt为图片文本，当图片无法显示时将显示文本
> 3. \<img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228"> 指定图像高度和宽度

## 11.表格
> 1.由\<table> 标签定义表格，<tr>定义行 <td>定义表格内数据
> 如：
>
> ```
> <table border="1">
>     <tr>
>         <td>row 1, cell 1</td>
>         <td>row 1, cell 2</td>
>     </tr>
>     <tr>
>         <td>row 2, cell 1</td>
>         <td>row 2, cell 2</td>
>     </tr>
> </table>
> ```



