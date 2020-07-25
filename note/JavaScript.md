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
> | 事件        | 描述                         |
> | :---------- | :--------------------------- |
> | onchange    | HTML 元素改变                |
> | onclick     | 用户点击 HTML 元素           |
> | onmouseover | 用户在一个HTML元素上移动鼠标 |
> | onmouseout  | 用户从一个HTML元素上移开鼠标 |
> | onkeydown   | 用户按下键盘按键             |
> | onload      | 浏览器已完成页面的加载       |
>

## 8. 字符串

> 1. 字符串使用单引号或双引号```var carname = "Volvo XC60";```
>
> 2. 使用下标访问字符串中字符```carname[6]```
>
> 3. 字符串中可以使用引号，但不能与字符串引号相同```"He is called 'Johnny'"```
>
> 4. 使用length属性计算字符串长度
>
> 5. 转义字符
>
>    | 代码 | 输出        |
>    | :--- | :---------- |
>    | \'   | 单引号      |
>    | \"   | 双引号      |
>    | \\   | 反斜杠      |
>    | \n   | 换行        |
>    | \r   | 回车        |
>    | \t   | tab(制表符) |
>    | \b   | 退格符      |
>    | \f   | 换页符      |
>
> 6. 使用new定义的字符串是一个对象
>
>    ```
>    var y = new String("John");
>    window.alert(typeof y); //输出object
>    ```
>
> 7. 使用+号进行字符串连接```"What a very"+"nice day";```
>
> 8. **模板字符串**
>
>    * 模板字符串使用反引号**(``)**来替代普通字符串中的单引号和双引号
>
>    * 模板字符串可以包含特定语法`${expression}`的占位符
>
>    * 模板字符串可以实现多行字符串
>
>      ```
>      console.log('string text line 1\n' +
>      'string text line 2');//普通字符串方法
>      
>      console.log(`string text line 1
>      string text line 2`);//模板字符串方法
>      ```
>
>    * 可以插入表达式
>
>      ```
>      var a = 5;
>      var b = 10;
>      console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');//普通字符串方法
>      
>      console.log(`Fifteen is ${a + b} and
>      not ${2 * a + b}.`);//模板字符串方法
>      ```

## 9. 运算符

> 1. 算术运算符和赋值运算符与c中相同
>
> 2. +号字符串运算
>
>    * 运用于多个字符串连接
>    * 若是字符串与数字相加则为字符串，```"Hello"+5```结果为```Hello5```
>
> 3. 比较运算符
>
>    | 运算符 | 描述           | 比较    | 值    |
>    | ------ | -------------- | ------- | ----- |
>    | ==     | 值相等         |         |       |
>    | ===    | 值和类型都相等 | 5==="5" | false |
>    | !=     | 值不等         |         |       |
>    | !==    | 值和类型都不等 | 5!=="5" | true  |
>
>
> 4. 逻辑运算符
>
>    * &&与 ||或 ！非
>
>    * 在js逻辑运算中，0、""、null、false、undefined、NaN都会判为false，其他都为true
>
>    * &&运算有数值参与时，结果为true则返回最后一个真值，结果为false则返回第一个假值
>
>    * ||运算有数值参与时，结果为true则返回第一个真值，结果为false则返回最后一个假值
>
>      ```
>      console.log( 5 && 4 );//当结果为真时，返回第二个为真的值4 
>      console.log( 0 && 4 );//当结果为假时，返回第一个为假的值0 
>      console.log( 5 || 4 );//当结果为真时，返回第一个为真的值5 
>      console.log( 0 || 0 );//当结果为假时，返回第二个为假的值0 
>      ```
>
>    * **逻辑与的优先级高于逻辑或**
>
>      ```
>       console.log(3||2&&5||0);//5 先计算2&&5返回5，再计算3||5||0返回3
>       console.log((3||2)&&(5||0));//5 先计算3||2返回3，5||0返回5，再计算3&&5返回5
>      ```
>
>    * 代码精简写法，但降低可读性
>
>      ```
>      if(a >=5)
>      {
>      	alert("你好");
>      }
>      
>      与以下写法相等
>      
>      a >= 5 && alert("你好");
>      ```
>
> 5. 条件运算符
>
>    ```variablename=(condition)?value1:value2 ```