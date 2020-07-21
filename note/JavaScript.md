## 1. 用法

> 1. 如需在 HTML 页面中插入 JavaScript，请使用\<script> 标签
>
> 2. \<script> 和 \</script> 之间的代码行包含了 JavaScript
>
>    ```
>    <!DOCTYPE html>
>    <html>
>    <body>
>    .
>    .
>    <script>
>    document.write("<h1>这是一个标题</h1>");
>    document.write("<p>这是一个段落</p>");
>    </script>
>    .
>    .
>    </body>
>    </html>
>    ```
>
> 3. 上述例子中的js语句会在页面打开时执行，若想要在某事件发生时执行代码就需要使用函数
>
> 4. 可以引用外部js文件
>
>    ```
>    HTML：
>    <button type="button" onclick="myFunction()">点击这里</button>
>    <script src="myScript.js"></script>
>    JS：
>    function myFunction()
>    {
>        document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
>    }
>    ```

## 2.输出

>1. js本身没有输出函数，但可以用以下方式输出数据
>
>   - 使用 **window.alert()** 弹出警告框。
>
>     ```
>     <script>
>     window.alert(5 + 6);//输出11
>     </script>
>     ```
>
>   - 使用 **document.write()** 方法将内容写到 HTML 文档中。
>
>     ```
>     <script>
>     document.write(Date());//输出时间
>     </script>
>     ```
>
>     **如果在文档加载结束后使用write，整个html页面将被覆盖**
>
>   - 使用 **innerHTML** 写入到 HTML 元素。
>
>     ```
>     <p id="demo">我的第一个段落</p>
>     
>     <script>
>     document.getElementById("demo").innerHTML = "段落已修改。";
>     </script>
>     ```
>
>   - 使用 **console.log()** 写入到浏览器的控制台。F12打开调试窗口
>
>     ```
>     <script>
>     a = 5;
>     b = 6;
>     c = a + b;
>     console.log(c);
>     </script>
>     ```

## 3. 语法

>1. 字面量：称固定值为字面量，整数小数或科学技术都可```3.14 、100 、 10e5 ```
>
>2. 字符串：使用单引号或双引号```"hello"  'hello'```
>
>3. 表达式字面量：用于计算```3+4 、 5*6```
>
>4. 数组字面量：定义一个数组```[40, 100, 1, 5, 25, 10]```
>
>5. 对象字面量：定义一个对象```{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}```
>
>6. 函数字面量：定义一个函数```function myFunction(a, b) { return a * b;}```
>
>7. **变量**：用于存储数据值，js中使用关键词**var**定义变量，使用**=**赋值
>
>  ```
>  var x, length
>  x = 5
>  length = 6
>  ```
>
>8. 可以对文本字符串使用反斜杠换行
>
>   ```
>   document.write("你好 \  //正确
>   世界!");
>   document.write \    //错误
>   ("你好世界!");
>   ```

## 4. 数据类型

> 1. JS拥有动态类型，相同变量可以为不同类型
>
>    ```
>    var x;               // x 为 undefined
>    var x = 5;           // 现在 x 为数字
>    var x = "John";      // 现在 x 为字符串
>    ```
>
> 2. 创建一个数组
>
>    ```
>    var cars=new Array("Saab","Volvo","BMW");
>    或
>    var cars=["Saab","Volvo","BMW"];
>    ```
>
> 3. **对象**由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义
>
>    ```
>    var person={firstname:"John", lastname:"Doe", id:5566};
>    ```
>
>    对象属性有两种寻址方式：
>
>    ```
>    name=person.lastname;
>    name=person["lastname"];
>    ```
>
> 4. 通过设置null清空变量
>
>    ```
>    cars=null;
>    person=null;
>    ```
>
> 5. 声明变量类型，使用new 声明类型
>
>    ```
>    var carname=new String;
>    var x=      new Number;
>    var y=      new Boolean;
>    var cars=   new Array;
>    var person= new Object;
>    ```

## 5. 对象

>1. 对象的方法定义了一个函数，并作为对象的属性存储。
>
>   对象方法通过添加 () 调用 (作为一个函数)。
>
>   该实例访问了 person 对象的 fullName() 方法:
>
>   ```
>   name = person.fullName();
>   ```
>
>   **若不加括号将返回字符串**
>
>2. 创建对象方法，使用```methodName : function() {}```
>
>   ```
>   var person = {
>       firstName: "John",
>       lastName : "Doe",
>       id : 5566,
>       fullName : function() 
>   	{
>          return this.firstName + " " + this.lastName;
>       }
>   ```
>
>3. 访问对象方法，```objectName.methodName()```

## 6. 函数

> 1. 传入参数
>
>    ```
>    <button onclick="myFunction('Harry Potter','Wizard')">点击这里</button>
>    <script>
>    function myFunction(name,job){
>        alert("Welcome " + name + ", the " + job);
>    }
>    </script>
>    ```
>
> 2. 返回值(使用return 退出函数)
>
>    ```
>    function myFunction()
>    {
>        var x=5;
>        return x;
>    }
>    ```

## 7. 事件

>1. 当事件触发时可以执行html代码，使用单引号或双引号添加代码
>
>   ```
>   <some-HTML-element some-event="JavaScript 代码">
>   实例
>   <button onclick="getElementById('demo').innerHTML=Date()">现在的时间是?</button>
>   ```
>
>2. 常见事件
>
>   | 事件        | 描述                         |
>   | :---------- | :--------------------------- |
>   | onchange    | HTML 元素改变                |
>   | onclick     | 用户点击 HTML 元素           |
>   | onmouseover | 用户在一个HTML元素上移动鼠标 |
>   | onmouseout  | 用户从一个HTML元素上移开鼠标 |
>   | onkeydown   | 用户按下键盘按键             |
>   | onload      | 浏览器已完成页面的加载       |
>
>