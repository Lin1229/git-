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

## 2. 输出

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
>   * 对象方法通过添加 () 调用 (作为一个函数)。
>
>   * 该实例访问了 person 对象的 fullName() 方法:
>
>     ```
>      name = person.fullName();
>     ```
>
>  **若不加括号将返回字符串**
>
>2. 创建对象方法，使用```methodName : function() {}```
>
>   ```
>    var person = {
>         firstName: "John",
>         lastName : "Doe",
>         id : 5566,
>         fullName : function() 
>     	{
>            return this.firstName + " " + this.lastName;
>         }
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

## 10. break

>js语句可以进行标记，通过在语句前加冒号进行标记，break可以跳过代码块
>
>```
>cars=["BMW","Volvo","Saab","Ford"];
>list: 
>{
>    document.write(cars[0] + "<br>"); 
>    document.write(cars[1] + "<br>"); 
>    document.write(cars[2] + "<br>"); 
>    break list;
>    document.write(cars[3] + "<br>"); 
>    document.write(cars[4] + "<br>"); 
>    document.write(cars[5] + "<br>"); 
>}
>```

## 11. typeof

>1. 使用typeof运算符检测变量类型```typeof "John"         返回 string```
>
>2. **null**是一个特殊数据类型，表示空，是一个对象
>
>   ```
>   给对象设置为null来清空
>   var person = null          person值为null 类型为obiect
>   也可以给对象设置为undefined清空
>   var person = undefined     person值为undefined 类型也为undefined
>   ```
>
>3. **undefined**是一个没有值的变量
>
>   ```
>   var person //person 值和类型都为undefined
>   ```
>4. undefined和null值相同，类型不相同
>

## 12. 类型转换

> 1. 数字转化为字符串
>
>    ```
>    全局方法String()
>    String(x)
>    String(3.14)
>    Number方法toString()
>    x.toString()
>    (3.14).toString
>    ```
>
> 2. 布尔转化为字符串
>
>    ```
>    全局方法String()
>    String(true)
>    Boolean方法
>    true.toString()
>    ```
>
> 3. 日期转化为字符串
>
>    ```
>    Date对象
>    Date()返回字符串
>    全局方法
>    String(new Date())
>    Date方法
>    obj = new Date()
>    obj.toString()
>    ```
>
> 4. 字符串转化数字
>
>    ```
>    全局方法Number()，空字符串会转化成0，其他字符串转化为NaN
>    Number("3.14")    // 返回 3.14
>    Number(" ")       // 返回 0
>    Number("")        // 返回 0
>    Number("99 88")   // 返回 NaN
>    ```
>
> 5. 使用一元运算符"+"转化数字
>
>    ```
>    var y = "5";      // y 是一个字符串
>    var x = + y;      // x 是一个数字
>    -----------------------------------
>    var y = "John";   // y 是一个字符串
>    var x = + y;      // x 是一个数字 (NaN)
>    ```
>    
> 6. 将布尔转化为数字
>
>    ```
>    使用全局方法
>    Number()
>    ```
>
> 7. 日期转化为数字
>
>    ```
>    全局方法
>    var d = new Date()
>    Number(d)
>    日期方法
>    d.getTime()
>    ```
>
> 8. 自动转换类型
>
>    ```
>    5 + null    // 返回 5         null 转换为 0
>    "5" + null  // 返回"5null"   null 转换为 "null"
>    "5" + 1     // 返回 "51"      1 转换为 "1" 
>    "5" - 1     // 返回 4         "5" 转换为 5
>    ```
>
> 9. 自动转化为字符串
>
>    ```
>    输出一个对象或一个变量时 JavaScript 会自动调用变量的 toString() 方法：
>    document.getElementById("demo").innerHTML = myVar;
>    
>    myVar = {name:"Fjohn"}  // toString 转换为 "[object Object]"
>    myVar = [1,2,3,4]       // toString 转换为 "1,2,3,4"
>    myVar = new Date()      // toString 转换为 "Fri Jul 18 2014 09:08:55 GMT+0200"
>    ```
>
>    **"0"，"000"转化为bool值后为true，""转化为bool为false**

## 13.  正则表达式

> 1. 正则表达式是由一个字符序列形成的搜索模式。
>
>    当你在文本中搜索数据时，你可以用搜索模式来描述你要查询的内容。
>
>    正则表达式可以是一个简单的字符，或一个更复杂的模式。
>
>    正则表达式可用于所有文本搜索和文本替换的操作。
>
> 2. 语法```/正则表达式主体/修饰符(可选)```
>
> 3. 正则表达式修饰符
>
>    | 修饰符 | 描述                                                     |
>    | :----- | :------------------------------------------------------- |
>    | i      | 执行对大小写不敏感的匹配。                               |
>    | g      | 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。 |
>    | m      | 执行多行匹配。                                           |
>
>    | 表达式      | 描述                           | 实例                           |
>    | :---------- | :----------------------------- | ------------------------------ |
>    | [abc]       | 查找方括号之间的任何字符。     | ```/[abc]/``` 或``` /[a-c]/``` |
>    | [0-9]       | 查找任何从 0 至 9 的数字。     | ```/[0-9]/```                  |
>    | [^abc]      | 查找任何不在方括号之间的字符。 | ```/[^a-c]/```                 |
>    | (red\|blue) | 查找任何以 \| 分隔的选项。     | ```/(red|blue)/```             |
>
>    | 元字符 | 描述                                           | 实例                                                         |
>    | :----- | :--------------------------------------------- | ------------------------------------------------------------ |
>    | \d     | 查找数字。                                     | var str="Give 100%!";<br>var patt1=/\d/g;<br>patt1="1,0,0"   |
>    | \s     | 查找空白字符。                                 |                                                              |
>    | \b     | 匹配单词边界（查找位于单词的开头或结尾的匹配） | var str="Visit Runooob";  <br/>var patt1=/\bRun/g;<br/>patt1="Run" |
>    | \uxxxx | 查找以十六进制数 xxxx 规定的 Unicode 字符。    |                                                              |
>
>    | 量词   | 描述                                   | 实例                                                         |
>    | :----- | :------------------------------------- | ------------------------------------------------------------ |
>    | n+     | 匹配任何包含至少一个 *n* 的字符串。    | /o+/g<br>/\w+/g                                              |
>    | n*     | 匹配任何包含零个或多个 *n* 的字符串。  | /10*/g(匹配1以及后面包括的任意个0)                           |
>    | n?     | 匹配任何包含零个或一个 *n* 的字符串。  | /10*/g(匹配1以及后面包括的一个0)                             |
>    | n{X}   | 匹配包含X个n序列的字符串               | /a{2}/ 不匹配 "candy," 中的 "a"，但是匹配 "caandy," 中的两个 "a"， |
>    | n{X,}  | n 连续出现至少 X 次时匹配              | /a{2,}/ 不匹配 "candy" 中的 "a"，但是匹配  "caaaaaaandy." 中所有的 "a"。 |
>    | n{X,Y} | n 连续出现至少 X 次，至多 Y 次时匹配。 |                                                              |
>
> 4. search方法和replace方法
>
>    * search方法用于检索字符串，并返回子字符串起始位置
>
>      ```
>      var str = "Visit Runoob!"; 
>      var n = str.search(/Runoob/i);//正则表达式
>      var n = str.search("Runoob");//字符串
>      ```
>
>    * replace方法用于字符串替换
>
>      ```
>      var str = document.getElementById("demo").innerHTML; 
>      var txt = str.replace(/microsoft/i,"Runoob");//正则表达式
>      var txt = str.replace("Microsoft","Runoob");//字符串
>      ```
>
> 5. test()方法
>
>    test() 方法是一个正则表达式方法。
>    test() 方法用于检测一个字符串是否匹配某个模式，
>    如果字符串中含有匹配的文本，则返回 true，否则返回 false。
>    以下实例用于搜索字符串中的字符 "e"
>
>    ```
>    var patt = /e/;
>    patt.test("The best things in life are free!");
>    也可以合并为一行
>    /e/.test("The best things in life are free!")
>    ```
>
> 6. exec()方法
>
>    exec() 方法是一个正则表达式方法。
>    exec() 方法用于检索字符串中的正则表达式的匹配。
>    该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。
>    以下实例用于搜索字符串中的字母 "e":
>
>    ```
>    /e/.exec("The best things in life are free!");
>    ```
>    
>  7. RegExp
>
>     RegExp 对象是一个预定义了属性和方法的正则表达式对象。
>
>     ```var patt1=new RegExp("e"); ```
>

## 14. 错误

>1. try和catch
>
>   * try语句定义在执行过程中执行错误测试的代码块，catch会捕捉到try块中的错误并执行代码
>
>     ```
>     var txt=""; 
>     function message() 
>     { 
>         try { 
>             adddlert("Welcome guest!"); 
>         } catch(err) { 
>             txt="本页有一个错误。\n\n"; 
>             txt+="错误描述：" + err.message + "\n\n"; 
>             txt+="点击确定继续。\n\n"; 
>             alert(txt); 
>         } 
>     }
>     ```
>
>2. finally和throw
>
>   * finally不论是否有错误都会执行，throw语句允许我们创建自定义错误
>
>     ```
>     function myFunction() {
>       var message, x;
>       message = document.getElementById("p01");
>       message.innerHTML = "";
>       x = document.getElementById("demo").value;
>       try { 
>         if(x == "") throw "值是空的";
>         if(isNaN(x)) throw "值不是一个数字";
>         x = Number(x);
>         if(x > 10) throw "太大";
>         if(x < 5) throw "太小";
>       }
>       catch(err) {
>         message.innerHTML = "错误: " + err + ".";
>       }
>       finally {
>         document.getElementById("demo").value = "";
>       }
>     }
>     ```

## 15. 变量提升

>1. js中，函数和变量的声明都会被提升到函数顶部，所以变量可以先使用后声明
>
>   ```
>   x = 5; // 变量 x 设置为 5
>   
>   elem = document.getElementById("demo"); // 查找元素
>   elem.innerHTML = x;                     // 在元素中显示 x
>   
>   var x; // 声明 x
>   ```
>
>2. 变量初始化不会提升
>
>   ```
>   var x = 5; // 初始化 x
>   
>   elem = document.getElementById("demo"); // 查找元素
>   elem.innerHTML = x + " " + y;           // 显示 x 和 y
>   
>   var y = 7; // 初始化 y
>   ```
>
>   显示结果x=5，y=undefined，因为变量声明var y提升了，但y=7没有提升
>
>   这个例子与下面代码等价
>
>   ```
>   var x = 5; // 初始化 x
>   var y;     // 声明 y
>   
>   elem = document.getElementById("demo"); // 查找元素
>   elem.innerHTML = x + " " + y;           // 显示 x 和 y
>   
>   y = 7;    // 设置 y 为 7
>   ```

## 16. 严格模式

>1. 严格模式通过在脚本或函数的头部添加 "use strict"; 表达式来声明
>
>   ```
>   "use strict";
>   x = 3.14;       // 报错 (x 未定义)
>   ```
>
>2. 在函数内部声明时是局部作用域
>
>   ```
>   x = 3.14;       // 不报错
>   myFunction();
>   
>   function myFunction() {
>      "use strict";
>       y = 3.14;   // 报错 (y 未定义)
>   }
>   ```
>
>3. 严格模式的限制
>
>   * 不允许使用未声明的变量
>   * 不允许删除变量或对象
>   * 不允许删除函数
>   * 不允许变量重名
>   * 不允许使用八进制
>   * 不允许使用转义字符
>   * 不允许对只读属性赋值