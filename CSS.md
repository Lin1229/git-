# CSS

## 1. 语法

> 1. ccs语法由选择器以及声明构成```p {color:red;text-align:center;}```  选择器 {属性:值；属性:值}
>
> 2. 使用/* */添加注释

## 2. id和class选择器

>1. id选择器可以为html特定元素指定样式，用#id 定义
>
>```
>#para1
>{
>	text-align:center;
>	color:red;
>} 
><p id="para1">Hello World!</p>
>```
>
>2. class选择器
>
>   * 可以为所有class定义指定样式，用.class名定义
>
>     ```
>     <style>
>     .center
>     {
>     	text-align:center;
>     }
>     </style>
>     
>     <body>
>     <h1 class="center">标题居中</h1>
>     <p class="center">段落居中。</p> 
>     </body>
>     ```
>
>   * 也可为特定html元素定义指定样式，用元素名.class名定义
>
>     ```
>     <style>
>     p.center
>     {
>     	text-align:center;
>     }
>     </style>
>     </head>
>     
>     <body>
>     <h1 class="center">这个标题不受影响</h1>
>     <p class="center">这个段落居中对齐。</p> 
>     </body>
>     ```
>
>  ***class名的第一个字符不能是数字***

## 3. css创建

> 1. 插入样式表的方式：外部样式表、内部样式表、内联样式（优先级为内联>内部>外部>浏览器默认）
>
>    * 外部样式表(可以应用与很多界面，)
>
>      ```
>      使用link定义
>      <head>
>      <link rel="stylesheet" type="text/css" href="mystyle.css">
>      </head>
>      外部样式表不能包含html标签，以.css扩展名定义
>      hr {color:sienna;}
>      p {margin-left:20px;}
>      body {background-image:url("/images/back40.gif");}
>      ```
>
>    * 内部样式表(应用于单个文档)
>
>      ```
>      <head>
>      <style>
>      hr {color:sienna;}
>      p {margin-left:20px;}
>      body {background-image:url("images/back40.gif");}
>      </style>
>      </head>
>      ```
>
>    * 内联样式(仅在一个元素上使用一次)
>
>      ```
>      <p style="color:sienna;margin-left:20px">这是一个段落。</p>
>      ```
>    
> 2. 多重样式
>
>    内部样式和外部样式定义相同元素时，颜色继承于外部样式，文字排列和字体继承于内部样式
>
>    ```
>    h3 /*外部样式*/
>    {
>        color:red;
>        text-align:left;
>        font-size:8pt;
>    }
>    h3 /*内部样式*/
>    {
>        text-align:right;
>        font-size:20pt;
>    }
>    /*h3的样式*/
>    color:red;
>    text-align:right;
>    font-size:20pt;
>    ```

## 4. Position定位

> 1. positon属性指定了元素的定位方式
>
>    * static 定位，默认值，无定位，static定位的元素不会受到top, bottom, left, right影响
>
>      ```
>      div.static {
>          position: static;
>          border: 3px solid #73AD21;
>      }
>      ```
>      
>    * fixed定位，相对于浏览器固定，窗口滚动元素也不移动
>    
>      ```
>      p.pos_fixed
>      {
>          position:fixed;
>          top:30px;
>          right:5px;
>      }
>      ```
>    
>    * relative定位，相对于元素正常位置，移动后元素原本所占的空间不会改变
>    
>      ```
>      h2.pos_left
>      {
>          position:relative;
>          left:-20px;
>      }
>      h2.pos_right
>      {
>          position:relative;
>          left:20px;
>      }
>      ```
>    
>    * absoulte定位，相对与最近已定位父元素，如没有则相对于\<html>
>    
>      ```
>      h2
>      {
>          position:absolute;
>          left:100px;
>          top:150px;
>      }
>      ```
>    
>    * sticky定位，粘性定位，与relative定位相似，但当窗口滚动超过目标区域时，就会切换为fixed定位，固定在窗口上
>    
>      需要设置固定阈值 top, right, bottom 或 left 之一
>    
>      ```
>      div.sticky {
>          position: -webkit-sticky;   /* Safari浏览器 */
>          position: sticky;
>          top: 0;
>          background-color: green;
>          border: 2px solid #4CAF50;
>      }
>      ```
>    
>    * 元素重叠，指定覆盖时元素的堆叠顺序，z-index越大的在上方。
>    
>      ```
>      img
>      {
>          position:absolute;
>          left:0px;
>          top:0px;
>          z-index:-1;
>      }
>      ```

## 5. Float浮动

> 1. 

## . 施工中

## . 居中方法

>1. **居中对齐**
>
>  * 块级元素直接使用margin: auto；(外边距)
>
>  ```
>  .center 
>  {
>      margin: auto;
>      width: 50%;       若没有设置宽度或宽度为100%则居中不起作用
>      border: 3px solid green;
>      padding: 10px;
>  }
>  ```
>
>  * 文本居中，使用text-align：center
>
>  ```
>  .center 
>  {
>      text-align: center;
>      border: 3px solid green;
>  }
>  ```
>
>  * 非块级元素，将其设置为块级元素
>
>  ```
>  img {
>      display: block; /*设置为块级元素*/
>      margin: auto;
>      width: 40%;
>  }
>  ```
>2. **左右对齐**
>   
>   * 使用定位方式
>   
>     ```
>     .right {
>         position: absolute;
>         right: 0px;  /*右边界为0，右对齐，left: 0px;左对齐*/
>         width: 300px;
>         border: 3px solid #73AD21;
>         padding: 10px;
>     }
>     ```
>   
>   * 使用float方式
>   
>     
>   
>     

