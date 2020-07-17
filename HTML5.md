## 1. HTML5

> 1. 声明html5文档 \<!DOCTYPE html>
>
>    ```
>    <!DOCTYPE html>
>    <html>
>    <head>
>    <meta charset="utf-8">
>    <title>文档标题</title>
>    </head>
>     
>    <body>
>    文档内容......
>    </body>
>     
>    </html>
>    ```
>
>    中文网页需要在头部中使用***\<meta charset="utf-8">***声明，否则将出现乱码
>

## 2.  Canvas

> 1. HTML5 \<canvas>元素用于图形绘制，其只是图形容器，绘制需要使用script脚本,例子如下
>
>    * id属性在脚本中引用，width和height定义长宽
>
>      ```<canvas id="myCanvas" width="200" height="100"> </canvas>``` 
>
>    * 使用style添加边框
>
>      ```<canvas id="myCanvas" width="200" height="100" style="border:1px solid #000000;"> </canvas>```
>
> 2. **使用Javascript绘制图像**
>
>    ```
>    var c=document.getElementById("myCanvas");      找到canvas元素
>    var ctx=c.getContext("2d");                     创建context对象 ，2d为内置html5对象，具有多种绘制方法
>    ctx.fillStyle="#FF0000";                        填充红色
>    ctx.fillRect(0,0,150,75);                       fillRect（x，y，width，height）设置填充方式
>    ```
>    
> 3. Canvas坐标
>    
>    * canvas是一个二维网格，左上角为(0,0) ，fillRect（0，0，150，75）意为绘制一个150x75的矩形，从(0，0)开始
>    
> 4. 路径
>
>    * 直线
>
>      ```
>      var c=document.getElementById("myCanvas");
>      var ctx=c.getContext("2d");
>      ctx.moveTo(0,0);        设置起点
>      ctx.lineTo(200,100);    设置终点
>      ctx.stroke();           画直线
>      ```
>
>    * 圆形
>
>      ```
>      var c=document.getElementById("myCanvas");
>      var ctx=c.getContext("2d");
>      ctx.beginPath();
>      ctx.arc(95,50,40,0,2*Math.PI);   arc（x，y，r，start，stop） 
>      ctx.stroke();
>      ```
>
>    * 文本
>
>      ```
>      var c=document.getElementById("myCanvas");
>      var ctx=c.getContext("2d");
>      ctx.font="30px Arial";         定义字体
>      ctx.fillText("Hello World",10,50);    绘制实心文本
>      ctx.strokeText("Hello World",10,50);  绘制空心文本
>      ```
>
>    * 渐变,有两种渐变方式：线条渐变和圆渐变,使用渐变时必须使用两种以上的停止色
>
>    * 通过```addColorStop()```方法设置停止色，参数用坐标描述(从0至1)
>
>    * 线条渐变
>    
>      ```
>      var c=document.getElementById("myCanvas");
>          var ctx=c.getContext("2d");
>          var grd=ctx.createLinearGradient(0,0,200,0); 创建线条渐变(x,y,x1,y1)
>          grd.addColorStop(0,"red");                   设置停止色
>          grd.addColorStop(1,"white");                 设置停止色
>          ctx.fillStyle=grd;
>       ctx.fillRect(10,10,150,80);                填充渐变
>      ```
>
>    * 圆渐变
>    
>      ```
>          var c=document.getElementById("myCanvas");
>          var ctx=c.getContext("2d");
>          var grd=ctx.createRadialGradient(75,50,5,90,60,100);  创建圆渐变(x,y,r,x1,y1,r1)
>          grd.addColorStop(0,"red");
>          grd.addColorStop(1,"white");
>          ctx.fillStyle=grd;
>   	ctx.fillRect(10,10,150,80);
>      ```
>
>    * 图像
>    
>      ```
>        var c=document.getElementById("myCanvas");
>        var ctx=c.getContext("2d");
>        var img=document.getElementById("scream");
>        ctx.drawImage(img,10,10); 创建图像
>      ```
>

## 3. SVG

> 1. SVG指可伸缩矢量图形，在缩放时图形质量不会损失 ，由\<svg>定义

## 4. MathML

> 1. mathml是一个数学标记语言，由\<math>定义

## 5. 拖放（未完成）

> 1.拖放即抓取一个对象拖到另一个位置，html5所有元素都支持拖放，通常分为以下步骤
>
> * 设置元素为可拖放： 元素中加入属性 draggable="true" 如 ```<img draggable="true">```
> * 触发事件：拖动时会发生什么
> * 放到何处：
> * 放置：触发放置事件

## 6.地理位置（未完成）

> 1. 使用getCurrentPosition() 方法来获得用户的位置。
>
>    ```
>    var x=document.getElementById("demo");
>    function getLocation()
>    {
>        if (navigator.geolocation)  是否支持地理位置
>        {
>            navigator.geolocation.getCurrentPosition(showPosition);
>        }
>        else
>        {
>            x.innerHTML="该浏览器不支持获取地理位置。";
>        }
>    }
>     
>    function showPosition(position)
>    {
>        x.innerHTML="纬度: " + position.coords.latitude + 
>        "<br>经度: " + position.coords.longitude;    
>    }
>    ```

## 7. 视频

> 1. \<video>标签，controls提供播放暂停和音量控件来控制视频，支持MP4, WebM, 和 Ogg
> 2. \<video> 元素支持多个 \<source> 元素.\<source> 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式：
> ```
> <video width="320" height="240" controls>   设置长宽
>   <source src="movie.mp4" type="video/mp4">
>   <source src="movie.ogg" type="video/ogg">
> 您的浏览器不支持Video标签。      video标签之间的内容当浏览器不支持video标签时显示
> </video> 
> ```
> 2. 使用javascript控制视频
>
>    ```
>    <div style="text-align:center"> 
>      <button onclick="playPause()">播放/暂停</button> 
>      <button onclick="makeBig()">放大</button>
>      <button onclick="makeSmall()">缩小</button>
>      <button onclick="makeNormal()">普通</button>
>      <br> 
>      <video id="video1" width="420">
>        <source src="mov_bbb.mp4" type="video/mp4">
>        <source src="mov_bbb.ogg" type="video/ogg">
>        您的浏览器不支持 HTML5 video 标签。
>      </video>
>    </div> 
>    
>    <script> 
>    var myVideo=document.getElementById("video1"); 
>    
>    function playPause()
>    { 
>    	if (myVideo.paused) 
>    	  myVideo.play(); 
>    	else 
>    	  myVideo.pause(); 
>    } 
>    
>    	function makeBig()
>    { 
>    	myVideo.width=560; 
>    } 
>    
>    	function makeSmall()
>    { 
>    	myVideo.width=320; 
>    } 
>    
>    	function makeNormal()
>    { 
>    	myVideo.width=420; 
>    } 
>    </script> 
>    ```

## 8.音频

> 1. \<audio>标签控制音频，controls提供播放暂停和音量控件来控制视频，支持MP3, Wav, 和 Ogg
>
> 2. \<audio> 元素支持多个 \<source> 元素.\<source> 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式：
>
> ```
> <audio controls>
>   <source src="horse.ogg" type="audio/ogg">
>   <source src="horse.mp3" type="audio/mpeg">
> 您的浏览器不支持 audio 元素。
> </audio>
> ```

## 9. 表单

>1.html5拥有多种新的表单类型，与html一样表单由\<form>定义，使用\<input>标签输入
>
>2.html5新增多种input类型：
>
>* color 从色盘中选取颜色
>
>```
><form action="demo-form.php">  将内容提交给目标文件处理
> 选择你喜欢的颜色: <input type="color" name="favcolor"><br>
> <input type="submit">
></form>
>```
>
>* date 选取日期
>
>```
><form action="demo-form.php">
> 生日: <input type="date" name="bday">
> <input type="submit">
></form>
>```
>
>* datetime 选取日期和时间（UTC）
>
>```
><form action="demo-form.php">
> 生日 (日期和时间): <input type="datetime" name="bdaytime">
> <input type="submit">
></form>
>```
>
>* datetime-local 选取日期和时间（本地）
>
>```
><form action="demo-form.php">
> 生日 (日期和时间): <input type="datetime-local" name="bdaytime">
> <input type="submit">
></form>
>```
>
>* email 提交时会自动验证email是否合法
>
>```
><form action="demo-form.php">
> E-mail: <input type="email" name="usremail">
> <input type="submit">
></form>
>```
>
>* month  选取年月
>
>```
><form action="demo-form.php">
> 生日 ( 月和年 ): <input type="month" name="bdaymonth">
> <input type="submit">
></form>
>```
>
>* number 选取数字（需设置范围）
>
>```
><form action="demo-form.php">
> 数量 ( 1 到 5 之间): <input type="number" name="quantity" min="1" max="5">
> <input type="submit">
></form>
>```
>
>使用以下属性对数字类型进行限定：
>|属性|作用|
>| --------- | -------------------------- |
>| disabled  | 规定输入字段是禁用的       |
>| max       | 规定允许的最大值           |
>| maxlength | 规定输入字段的最大字符长度 |
>| min       | 规定允许的最小值           |
>| pattern   | 规定用于验证输入字段的模式 |
>| readonly  | 规定输入字段的值无法修改   |
>| required  | 规定输入字段的值是必需的   |
>| size      | 规定输入字段中的可见字符数 |
>| step      | 规定输入字段的合法数字间隔 |
>| value     | 规定输入字段的默认值       |
>
>* range 选取数字 （显示为滑动条）
>
>```
><form action="demo-form.php" method="get">
>Points: <input type="range" name="points" min="1" max="10">
><input type="submit">
></form>
>```
>
>使用以下属性对数字类型进行限定：
>|属性|作用|
>| --------- | -------------------------- |
>| max       | 规定允许的最大值           |
>| min       | 规定允许的最小值           |
>| step      | 规定输入字段的合法数字间隔 |
>| value     | 规定输入字段的默认值       |
>* search 定义一个搜索字段，类似谷歌
>
>```
> <form action="demo-form.php">
>   Search Google: <input type="search" name="googlesearch"><br>
>   <input type="submit">
> </form>
>```
>
>* tel 电话号码字段
>
>```
><form action="demo-form.php">
>  电话号码: <input type="tel" name="usrtel"><br>
>  <input type="submit">
></form>
>```
>
>* time 选择时间
>
>```
><form action="demo-form.php">
>  选择时间: <input type="time" name="usr_time">
>  <input type="submit">
></form>
>```
>
>* url 输入地址，会自动验证合法性
>
>```
><form action="demo-form.php">
>  添加你的主页: <input type="url" name="homepage"><br>
>  <input type="submit">
></form>
>```
>
>* week 选择年和星期
>
>```
><form action="demo-form.php">
>  选择周: <input type="week" name="year_week">
>  <input type="submit">
></form>
>```

## 10.新表单元素

>1.  \<datalist>规定输入域的选项列表，根据用户输入能自动补全，记录输入历史。
>
>```
><form action="demo-form.php" method="get">
><input list="browsers" name="browser">
><datalist id="browsers">
><option value="Internet Explorer">
><option value="Firefox">
><option value="Chrome">
><option value="Opera">
><option value="Safari">
></datalist>
><input type="submit">
></form>
>```
>
>2. \<keygen>标签规定用于表单的密钥对生成器字段。
>
> 当提交表单时，会生成两个键，一个是私钥，一个公钥。
>
> 私钥（private key）存储于客户端，公钥（public key）则被发送到服务器。
>
> 公钥可用于之后验证用户的客户端证书（client certificate）。
>
> ```
> <form action="demo_keygen.php" method="get">
>   用户名: <input type="text" name="usr_name">
>   加密: <keygen name="security">
>   <input type="submit">
> </form>
> ```
>3. \<output>用于不同类型的输出
>
>```
><form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
><input type="range" id="a" value="50">100
>+<input type="number" id="b" value="50">
>=<output name="x" for="a b"></output>
></form>
>```

