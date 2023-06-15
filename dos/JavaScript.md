# JavaScript程序设计

![image-20230309182400674](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230309182400674.png)

### 为什么学习 JavaScript?

JavaScript 是 web 开发人员必须学习的 3 门语言中的一门：

1. **HTML** 定义了网页的内容
2. **CSS** 描述了网页的布局
3. **JavaScript** 控制了网页的行为



### JS基础输出语句

```javascript
document.write();
alert();
console.log();
```



### JS代码编写位置

1. 标签内（不推荐，后期维护，结构与行为耦合）
2. 外部文件引入（**最佳**）
3. 写在script标签中



**可通过外部文件将JS代码编写在js文件中，方便引入(开发中推荐使用）**

```javascript
<script type="text/javascript" src=""> </script>
```

> PS：script标签一旦用于外部文件引入，就不能编写代码了，即使编写浏览器也不会执行



### JS代码编写注意事项

1. JS严格区分大小写
2. JS每一条语句必须（ ; ）结尾
3. JS会自动忽略多个空格和换行



### 标识符书写注意事项

1. 标识符中可以含有**字母**、**数字**、**_** 、**$**
2. 标识符不能以数字开头
3. 标识符不能是js中的关键字或保留字
4. 标识符一般都采用**驼峰命名法**



![image-20230309182317219](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230309182317219.png)



### 变量提升 

JavaScript引擎的工作方式是，显黑系带吗，回去所有被声明变量，然后再一行一样的运行，这造成的结果，就是所有的变量的声明语句，都会被提升到代码段的头部，这就叫做变量提升（hoisting）

```javascript
var age;
console.log(age);
age = 10;
//变量提升
```

### 数据类型*

**值类型(基本类型)**：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol。

**引用数据类型（对象类型）**：对象(Object)、数组(Array)、函数(Function)，还有两个特殊的对象：正则（RegExp）和日期（Date）。

**注：***Symbol 是 ES6 引入了一种新的原始数据类型，表示独一无二的值。*



**数据类型可分为**

- 基本数据类型（原始类型）
  1. 数值/数字/ 类型
  2. 字符串类型：被双引号或单引号包裹的值就是字符串
  3. 布尔类型：计算机是由0和1组成0：false 1：true
  
- 合成类型（复合类型）

  对象：因为一个对象往往是多个原始类型的值合成，可以看作是一个存放各种值的容器

### 逻辑运算符

逻辑运算符用于测定变量或值之间的逻辑。

给定 x=6 以及 y=3，下表解释了逻辑运算符：

| 运算符 | 描述                    | 例子                      |
| :----- | :---------------------- | :------------------------ |
| &&     | and（多个条件都要满足） | (x < 10 && y > 1) 为 true |
| \|\|   | or（满足一个条件即可）  | (x==5 \|\| y==5) 为 false |
| !      | not                     | !(x==y) 为 true           |

**布尔值取反**

```js
!true //false
!false // true
```

**非布尔值取反**

对于非布尔值，取反运算符会将其转换为布尔值，可以这样记忆，以下六个值取反后为true，其他值都为false

```js
undefined
null
false
0
NaN
空字符串（'')
```

### JavaScript条件语句

#### if 语句

只有当指定条件为 true 时，该语句才会执行代码。

**语法**

```js
if (condition)
{
  当条件为 true 时执行的代码
}


//实例

<p>如果时间早于 20:00，会获得问候 "Good day"。</p>
<button onclick="myFunction()">点击这里</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x="";
	var time=new Date().getHours();
	if (time<20){
		x="Good day";
    }
	document.getElementById("demo").innerHTML=x;
}
</script>
```

#### if...else 语句

请使用 if....else 语句在条件为 true 时执行代码，在条件为 false 时执行其他代码。

**语法**

```js
if (condition)
{
    当条件为 true 时执行的代码
}
else
{
    当条件不为 true 时执行的代码
}

//实例
<p>点击这个按钮，获得基于时间的问候。</p>
<button onclick="myFunction()">点击这里</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x="";
	var time=new Date().getHours();
	if (time<20){
	 	x="Good day";
     }
	else{
 		x="Good evening";
 	}
	document.getElementById("demo").innerHTML=x;
}
</script>
```

#### if...else if...else 语句

使用 if....else if...else 语句来选择多个代码块之一来执行。

```js
if (condition1)
{
    当条件 1 为 true 时执行的代码
}
else if (condition2)
{
    当条件 2 为 true 时执行的代码
}
else
{
  当条件 1 和 条件 2 都不为 true 时执行的代码
}

//实例
<script type="text/javascript">
var d = new Date();
var time = d.getHours();
if (time<10)
{
	document.write("<b>早上好</b>");
}
else if (time>=10 && time<20)
{
	document.write("<b>今天好</b>");
}
else
{
	document.write("<b>晚上好!</b>");
}
</script>
<p>
这个例子演示了 if..else if...else 语句。
</p>

```

#### JavaScript switch 语句

> 工作原理：首先设置表达式 *n*（通常是一个变量）。随后表达式的值会与结构中的每个 case 的值做比较。如果存在匹配，则与该 case 关联的代码块会被执行。请使用 **break** 来阻止代码自动地向下一个 case 运行。

```js
switch(n)
{
    case 1:
        执行代码块 1
        break;
    case 2:
        执行代码块 2
        break;
    default:
        与 case 1 和 case 2 不同时执行的代码
}

<p>点击下面的按钮来显示今天是周几：</p>
<button onclick="myFunction()">点击这里</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x;
	var d=new Date().getDay();
	switch (d){
  		case 0:x="今天是星期日";
    	break;
 		case 1:x="今天是星期一";
        break;
  		case 2:x="今天是星期二";
        break;
        case 3:x="今天是星期三";
   	 	break;
  		case 4:x="今天是星期四";
    	break;
  		case 5:x="今天是星期五";
        break;
  		case 6:x="今天是星期六";
    	break;
 	}
	document.getElementById("demo").innerHTML=x;
}
</script>
```

### Js三元运算符

![image-20230329152526916](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329152526916.png)

> 这个三元运算符可以视为if...else的简写形式，因此可以适用于多种场合。
>
> JavaScript中还有一个三元运算符（即该运算符需要三个运算子），也可以运用逻辑判断

**条件1为真时执行表达式1 为假时执行表表达式2**

```js
（条件1）？表达式1 ：表达式2

```

![image-20230329152221483](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329152221483.png)

### JavaScript for 循环*

循环可以将代码块执行指定的次数。

如果你希望**一遍又一遍地运行相同的代码**，并且每次的值都不同，那么使用循环是很方便的。

![image-20230329153420959](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329153420959.png)

### JavaScript for 循环实操*

```js
//循环输出1~100之间数字的和
var sum = 0 ；
for (var i = 1;i <= 100;i++){
    //5050
    sum + =i; //sum = sum + i;
}
console.log(sum);//5050


//循环输出1000以内的奇数 
for (var i = 0; i<= 1000; i++){
    if(i % 2 != 0){
        console.log(i);
    }
}


//九九乘法表打印
var sum = 0;
    for(var i=1;i<=9;i++){
       document.write("</br>")
          for(var j=1;j<=i;j++){
             sum = i * j;
             document.write(j + "*"+ i + "=" + sum +" " );
            }
        }



```

### 字符串*

![image-20230329163045591](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329163045591.png)

![image-20230329163115650](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329163115650.png)

![image-20230329163323825](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230329163323825.png)

------

**字符串方法**

| 方法                | 描述                                                         |
| :------------------ | :----------------------------------------------------------- |
| charAt()            | 返回指定索引位置的字符                                       |
| charCodeAt()        | 返回指定索引位置字符的 Unicode 值                            |
| concat()            | 连接两个或多个字符串，返回连接后的字符串                     |
| fromCharCode()      | 将 Unicode 转换为字符串                                      |
| indexOf()           | 返回字符串中检索指定字符第一次出现的位置                     |
| lastIndexOf()       | 返回字符串中检索指定字符最后一次出现的位置                   |
| localeCompare()     | 用本地特定的顺序来比较两个字符串                             |
| match()             | 找到一个或多个正则表达式的匹配                               |
| replace()           | 替换与正则表达式匹配的子串                                   |
| search()            | 检索与正则表达式相匹配的值                                   |
| slice()             | 提取字符串的片断，并在新的字符串中返回被提取的部分           |
| split()             | 把字符串分割为子字符串数组                                   |
| substr()            | 从起始索引号提取字符串中指定数目的字符                       |
| substring()         | 提取字符串中两个指定的索引号之间的字符                       |
| toLocaleLowerCase() | 根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLocaleUpperCase() | 根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLowerCase()       | 把字符串转换为小写                                           |
| toString()          | 返回字符串对象值                                             |
| toUpperCase()       | 把字符串转换为大写                                           |
| trim()              | 移除字符串首尾空白                                           |
| valueOf()           | 返回某个字符串对象的原始值                                   |

**PS:**

`charAt`  返回指定索引位置的字符

```js
var str = "hello";

console.log(str1.charAt(4));// 返回值为o 
```

------

`concat`  连接两个或多个字符串，返回连接后的字符串 如果存在非字符串如数值，会先转换为字符串然后再连接

```js
var str1 = "hello";
var str2 = " 你好！";
var result =str1.concat(str2);

console.log(result);
console.log(str1.concat(str2));

```

concat 与 + 区别

concat不管什么类型直接合并成字符串，加号是遇到数字类型先做运算，遇到字符串就和字符串相连接

------

`substring`方法用于从原字符串汇总取出字符并返回，不改变字符串，它的的一个参数表示子字符串的开始位置，第二个位置表示结束位置（返回结果不含该位置）

```js
var str ="helloWorld!";

console.log(str.substring(0,4));
```

如果省略第二个参数，则表示子字符串一直到字符串结束

如果第一个参数大于第二个参数，`substring`方法会自动更换两个参数的位置

如果参数是负数，`substring`的方法会自动将负数转换为0

------

### 数组Array*

数组对象的作用是：使用单独的变量名来存储一系列的值。

#### 什么是数组?

数组对象是使用单独的变量名来存储一系列的值。

如果你有一组数据（例如：车名字），存在单独变量如下所示：

```js
var car1="Saab";
var car2="Volvo";
var car3="BMW";
```

然而，如果你想从中找出某一辆车？并且不是3辆，而是300辆呢？这将不是一件容易的事！

最好的方法就是用数组。

数组可以用一个变量名存储所有的值，并且可以用变量名访问任何一个值。

数组中的每个元素都有自己的的ID，以便它可以很容易地被访问到。

------

#### 创建一个数组

创建一个数组，有三种方法。

下面的代码定义了一个名为 myCars的数组对象：

1: 常规方式:

```js
var myCars=new Array();
myCars[0]="Saab";      
myCars[1]="Volvo";
myCars[2]="BMW";
```

2: 简洁方式:

```js
var myCars=new Array("Saab","Volvo","BMW");
```

3: 字面:

```js
var myCars=["Saab","Volvo","BMW"];
```

------

#### 访问数组

通过指定数组名以及索引号码，你可以访问某个特定的元素。

即通过下标访问或添加都可（下标由0开始）

------

以下实例可以访问myCars数组的第一个值：

```js
var name=myCars[0];
```

以下实例修改了数组 myCars 的第一个元素:

```js
myCars[0]="Opel";
```

>  [0] 是数组的第一个元素。[1] 是数组的第二个元素。

------

#### 常用数组方法

##### push()方法

`push`方法用于在数组的末端添加一或多个元素，并返回添加元素的数组长度，注意，该方法会改变原数组

```js
var arr = [];
arr.push("Hello")；//1
arr.push('world!');// 2
arr.push(true,{});// 4
arr//[Hello,world!,true,{}];
```

------

##### pop()方法

`pop`方法用于删除数组的最后一个元素，并返回该元素，注意，该方法会改变原数组

```js
var arr = ['hello','wprld',true];

arr.pop();//'hello','wprld',true
```

------

##### shift()方法

`shift`方法用于删除数组的第一个元素，并返回该元素，注意，该方法会改变原数组

```js
var arr = ['hello','world',]
arr.shift(); // 'hello'
```

`shift`方法可以遍历并清空一个数组

```js
var list = [1,2,3,4,5,6];
var item;

while (item = list.shift()){
   console.log(ltem);
}


```

![image-20230404132630794](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230404132630794.png)

##### unshift()方法

`unshift`方法用于在数组的第一个位置添加元素，并返回添加元素后的值。注意该方法会改变数组

```js
var arr = ['hello','world',999];

arr.unshift('666');//[666,'hello','world',999]
```

`unshift`方法可以接受多个参数，这些参数都会添加到目标数组头部

```js
var arr = ['hello','world',999];
arr.unshift('nihao','你好')；

//['你好','nihao','hello','world',999]
```

------

##### join()方法

`join`方法以指定参数作为分隔符，将所有的数组成员连接为一个字符串返回。如果不提供参数，默认用逗号分隔

```js
var a = [1,2,3,4];

a.join(' ');//1,2,3,4
a.join('|');// 1|2|3|4
a.join()//1,2,3,4
```

如果数组成员是`undefined`或`null`或空位，会被转成空字符串

```js
[undefined,null].join('#');
//'#'

['a',,'b'].join('_');
//'a__b'
```

数组的`join`配合字符串的`split`可以实现数组与字符串的互换

```js
var arr = ['a','b','c'];
var myArr = arr.join("");
console.log(myArr);
console.log(myArr.split(""));
```

------

#### 数组静态方法_Array.isArray()

`Array.isArray()`方法返回一个布尔值，表示参数是否为数组，他可以弥补typeof运算符的不足

![image-20230403162746559](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230403162746559.png)

------

#### 数组的遍历

数组的遍历可以考虑使用for循环或者while循环

```js
var a = ['hello','world',666];

//for循环
for(var i = 0;i<a.length;i++){
    console.log(a[i]);
}

//while循环

var i = 0;
while(i<a.length){
   console.log(a[i]);
   i++;
}
```

**for...in遍历数组**

```js
var a = ['hello',world,666];

for(var i in a){
console.log(a[i]);
}
```

------

### 函数*

> 函数是一段可以反复调用的代码块
>
> 函数是由事件驱动的或者当它被调用时执行的可重复使用的代码块。

#### 函数的声明

> 函数就是包裹在花括号中的代码块，前面使用了关键词 function：

> function命令：function命令声明的代码区块，就是一个函数，function命令后面就是函数名，函数名后面就是一对圆括号，里面是传入函数的参数，函数体放在大括号里面。

```js
function functionname()
{
    // 执行代码
}
```

当调用该函数时，会执行函数内的代码。

可以在某事件发生时直接调用函数（比如当用户点击按钮时），并且可由 JavaScript 在任何位置进行调用。

#### 函数名的提升

> JavaScript引擎将函数名视同变量名，所以采用function命令声明函数时，整个函数会像声明变量一样，被提升到代码头部

```js
add();

function add(){
  
}
//一样会执行函数
```

#### 函数参数

> 函数运行的时候，有时候要提供外部数据，不同的外部数据会得到不同的结果，这种外部数据就叫参数

```js
function square(x){
    console.log(x * x);
}

square(2);//4
square(3);//9

```

![image-20230405162055987](C:\Users\90560\AppData\Roaming\Typora\typora-user-images\image-20230405162055987.png)

#### 函数返回值

> JavaScript函数提供两个接口实现与外界的交互，其中参数作为入口，接受外界信息，返回值作为出口，把运算结果反馈给外界

```js
function getName(name){
   return name;
}

var myName = getNmae("gao");
console.log(myName); //gao
```

------

### JavaScript对象

> JavaScript 对象是拥有属性和方法的数据。
>
> 在 JavaScript中，几乎所有的事物都是对象。
>
>  在 JavaScript 中，对象是非常重要的，当你理解了对象，就可以了解 JavaScript 。

#### 对象定义

你可以使用字符来定义和创建 JavaScript 对象:

对象的每一个键名又称为“属性”（property），它的键值可以是任何数据类型。如果一个属性的值为函数，通常这个属性被称为方法，它可以像函数那样调用

```js
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

定义 JavaScript 对象可以跨越多行，空格跟换行不是必须的：

```js
var person = {
    firstName:"John",
    lastName:"Doe",
    age:50,
    eyeColor:"blue"
};
```

------

#### 对象属性

可以说 "JavaScript 对象是变量的容器"。

但是，我们通常认为 "JavaScript 对象是键值对的容器"。

键值对通常写法为 **name : value** (键与值以冒号分割)。

键值对在 JavaScript 对象通常称为 **对象属性**。

> JavaScript 对象是属性变量的容器。

------

#### 访问对象属性

你可以通过两种方式访问对象属性:

```js
person.lastName;

person["lastName"];
```

------

#### Math对象

##### Math.abs()

`Math.abs()`方法返回参数值的绝对值

```js
Math.abs(1);// 1
Math.abs(-1);// 1
```

##### Math.max(),Math.min()

`Math.max`方法返回参数之中的最大值，Math.min方法返回参数中最小值，如果参数为空，`Math.min`返回`Infinity`，`Math.max`返回`-infinity`

```js
Math.max(2,-1,5);//5
Math.min(2,-1,5);//-1
Math.min()//Infinity
Math.max()//-Infinity
```

------

##### Math.floor(),Math.ceil()

`Math.floor`方法返回小于参数的最大整数

```js
Math.floor(3.2);//3

Math.floor(-3.2);// -4
```

Math.ceil方法返回大于参数值的最小整数

```js
Math.ceil(3.2);//4
Math.ceil(-3.2)//-3
```

------

##### Math.random()

`Math.random()`返回0~1之间的一个伪随机数，可能等于0，但是一定小于1

```js
Math.random()
```

任意范围内随机数生成函数如下

```js
function getRandomArbitrary(){
return Math.random() * (max - min) + min ;
}
getRandomArbitrary(5,10);
```

#### Date对象

`Date` 对象是 avaScript 原生的时间库。它以1970年1月1日00:00:00作为时间的零点，可以表示的时间范围是前后各1亿天 (单位为毫秒)



##### Date.now()

`Date.now` 方法返回当前时间距离时间零点 (1970年1月1日 00:00:00 UTC)的毫秒数，相当于 Unix 时间戳乘以1000

```js
Date.now(); 1635216733395
```

**时间戳**

时间戳是指格林威治时间1970年01月01日00时00分00秒(北京时间1970年01月01日08时00分00秒)起至现在的总秒数。

格林威治和北京时间就是时区的不同

Unix是20世纪70年代初出现的一个操作系统，Unix认为1970年1月1日0点是时间纪元。lavaScript也就遵循了这一约束



`Date` 对象提供了一系列 get 方法，用来获取实例对象某个方面的值

**实例方法get类**

> **getTime()**: 返回实例距离1970年1月1日00:00:00的毫秒数getDate(): 返回实例对象对应每个月的几号 (从1开始)getDay0: 返回星期几，星期日为0，星期一为1，以此类推
> **getYear()**: 返回距离1900的年数
> **getFullYear()**: 返回四位的年份
> **getMonth()**: 返回月份 (0表示1月，11表示12月)
> **getHours()**: 返回小时 (0-23)
> **getMilliseconds()**: 返回毫秒 (0-999)
> **getMinutes()**: 返回分钟 (0-59)
> **getSeconds()**: 返回秒 (0-59)

```js
var d = new Date('January 6,2023');
d.getDate //6
```

