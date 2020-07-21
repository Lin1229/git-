# AJAX

## 1.XHR 创建对象

> 1. 创建XMLHttpRequest对象```variable=new XMLHttpRequest```
>
> 2. 老版本IE(5，6)使用ActiveX对象```variable =new ActiveXObject("Microsoft.XMLHTTP")```
>
> 3. 使用前检查浏览器是否支持HML对象
>
>    ```
>    var xmlhttp;                  //创建xmlhttp变量
>    if (window.XMLHttpRequest)
>    {
>        //  IE7+, Firefox, Chrome, Opera, Safari 浏览器执行代码
>        xmlhttp=new XMLHttpRequest();
>    }
>    else
>    {
>        // IE6, IE5 浏览器执行代码
>        xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
>    }
>    ```

## 2. XHR请求

> 想要发送请求到服务器，需要XML对象下的open()和send()方法
>
> ```
> xmlhttp.open("GET","ajax_info.txt",true);
> xmlhttp.send();
> ```
>
> | 方法                         | 描述                                                         |
> | :--------------------------- | :----------------------------------------------------------- |
> | open(*method*,*url*,*async*) | 规定请求的类型、URL 以及是否异步处理请求。<br> *method*：请求的类型；GET 或 POST<br>*url*：文件在服务器上的位置<br>*async*：true（异步）或 false（同步） |
> | send(*string*)               | 将请求发送到服务器。*string*：仅用于 POST 请求               |
> ---
>
> ---
>
> ---
>
>
> get通常更快速简单，但是以下情况时需要使用post
>
> * 无法使用缓存文件（更新服务器上的文件或数据库）
>
> * 向服务器发送大量数据（POST 没有数据量限制）
>
> * 发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠
>
> 一个简单的get请求
>
> ```
> xmlhttp.open("GET","/try/ajax/demo_get.php",true);
> xmlhttp.send();
> ```
>
> 上面例子中有可能得到缓存的结果，为url添加唯一id可以避免
>
> ```
> xmlhttp.open("GET","/try/ajax/demo_get.php?t=" + Math.random(),true);
> xmlhttp.send();
> ```
>
> 想要通过get发送信息，可以向url中加入信息
>
> ```
> xmlhttp.open("GET","/try/ajax/demo_get2.php?fname=Henry&lname=Ford",true);//?后为发送的信息
> xmlhttp.send();
> ```
>
> ---
>
> ---
>
> ---
>
> post请求
>
> ```
> xmlhttp.open("POST","/try/ajax/demo_post.php",true);
> xmlhttp.send();
> ```
>
> post请求发送数据，使用setRequsetHeader()
>
> |               方法               |                             描述                             |
> | :------------------------------: | :----------------------------------------------------------: |
> | setRequestHeader(*header,value*) | 向请求添加 HTTP 头。<br>*header*: 规定头的名称<br>*value*: 规定头的值 |
>
> ```
> xmlhttp.open("POST","/try/ajax/demo_post2.php",true);
> xmlhttp.setRequestHeader("Content-type","application/x-www-form-urlencoded");
> xmlhttp.send("fname=Henry&lname=Ford");
> ```
>
> ---
>
> * url参数是服务器上文件的地址
>
> * 若要实现js与xml异步，就需要将open中的async参数设置为true
>
> * AJAX使得js发送请求后可以执行其他脚本，无需等待服务器响应，响应就绪后再进行处理。
>
>   ```
>   xmlhttp.onreadystatechange=function()
>   {
>       if (xmlhttp.readyState==4 && xmlhttp.status==200)
>       {
>           document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
>       }
>   }
>   xmlhttp.open("GET","/try/ajax/ajax_info.txt",true);
>   xmlhttp.send();
>   ```
>
>   |名称|数值|状态|
>   |----|----|----|
>   |.readyState|0<br>1<br>2<br>3<br>4|请求未初始化<br>服务器链接已建立<br>请求已接收<br>请求处理中<br>请求已完成，响应已就绪|
>   |.status|200<br>404|完成<br>未找到页面|
>   
> * 若async异步参数为false，当服务器繁忙或缓慢时，应用程序会挂起
>
> * 此时不需要编写onreadyseatechange函数，将代码放到send()后
>
>   ```
>   xmlhttp.open("GET","/try/ajax/ajax_info.txt",false);
>   xmlhttp.send();
>   document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
>   ```
>

## 3. XHR响应

>1. 获取服务器响应，使用responseText或responseXML
>
> | 属性         | 描述                       |
> | :----------- | :------------------------- |
> | responseText | 获得字符串形式的响应数据。 |
> | responseXML  | 获得 XML 形式的响应数据。  |
>
>text
>```
>document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
>```
>xml
>```
>xmlDoc=xmlhttp.responseXML;
>txt="";
>x=xmlDoc.getElementsByTagName("ARTIST");
>for (i=0;i<x.length;i++)
>{
>    txt=txt + x[i].childNodes[0].nodeValue + "<br>";
>}
>document.getElementById("myDiv").innerHTML=txt;
>```
>