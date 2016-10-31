---
layout: post
title: Javascript
category: javascript
tag: [javascript]
---

##  Javascript的基本语法

一、简介

 1、什么是javascript

    JavaScript 是网景（Netscape）公司开发的一种基于客户端浏览器、面向（基于）对象、事件驱动式的网页脚本语言。
客户端浏览器：

HTML、CSS、JavaScript客户端语言

PHP/Java/.NET服务器语言

判断一种语言是客户端还是服务器端，主要看“它”在哪里运行

JavaScript是一种面向对象的脚本语言

事件驱动式

2、javascript的用途

1）网页特效

2）表单验证

3）网页小游戏（超级玛丽、五子棋、坦克大战）

4）服务器端编程（Ajax、Node.js）

3、快速入门

二、javascript的基本语法

1、基本格式 

 1）JavaScript区分大小写

 2）JavaScript脚本程序须嵌入在HTML文件中

3）JavaScript脚本程序中不能包含HTML标记代码

如果想在javascript中使用html代码，可以采用document.write(“<h1>hello world</h1>”);

4）每行写一条脚本语句

document.write(‘hello’);alert(‘world’);

5）语句末尾可以加分号（建议都加分号）

document.write(‘hello world’)

alert(‘hello javascript’);

6）JavaScript脚本程序可以独立保存为一个外部文件
public.js文件中，并通过script中的src属性直接引入

2、变量

变量是用来临时存储数值的容器，变量存储的数值是可以变化的

变量必须要先声明才能使用，使用var声明变量

错误的：
alert(i);
正确的：
var i=10;
alert(i);
正确的：（只限全局，不推荐使用）
i=10;
alert(i)

变量的命名规则：第一个字符必须是英文字母，或者是下划线(_)，还可以是$美元符号，其后的字符，可以是英文字母，数字，下划线；变量名不能是JavaScript的保留字
变量的作用域:全局变量、局部变量

3、变量的数据类型：

1）String 字符类型 

2）Number 整型、浮点型

3）、boolean  true、false  

4）Undefined（变量声明，但未赋值）

 5）Null 空类型

 6）Object 对象类型（数组）

4、parseInt、parseFloat、isNaN函数

  parseInt()：将字符串转化为整数

  parseFloat()：将字符串转化为浮点数

  isNaN()：判断给定的值是否不为数值，如果不是数值则返回true，是数值返返回false

5、运算符

1）算术运算符

"+"  "-"  "*"  "/"  "%"

++ ：自加

--  ：自减

2）比较运算符

> < == === >= <= != !==

==：值相等，类型可以不同

===：全等于，要求值相等且类型要一致

3）逻辑运算符

&&  ||  !

4）赋值运算符

= += -= *= /= %=

5）字符串运算符

+
三、通过id找对象

  基本语法：document.getElementById(id值)

  获取单标签的值：

  获取双标签的值：



##   Javascript的语言结构
一、流程过程

1）顺序结构

2）分支结构

if else if else

switch

说明：

在if结构中，既可以对固定值的判断也可以实现对范围的判断

在switch，只能实现对固定值的判断

3）循环结构

for循环

while循环

do…while…循环

for…in…循环

4)循环控制

 break continue

二、JavaScript中的函数

1、函数分类

1）系统函数

2）自定义函数

2、自定义函数

使用函数前要先定义才能调用

	函数定义有三个部分:函数名,参数列表,函数体

	定义函数的格式

	function 函数名([参数1,参数2...]){

		函数执行部分;

		return 表达式;

	}


3、函数的功能：

1）代码重用

2）模块化编程

4、快速入门

5、函数参数

实参：在函数调用时，所传递的参数，我们称之为实参

形参：函数定义时，所指定的参数，我们称之为形参

6、自调用匿名函数

我们把没有名字的函数就称之为匿名函数

说明：即使是匿名函数，只要其进行了定义，那么系统就会自动返回其函数的首地址

自调用匿名函数作用：

在以后项目开发中，经常会引入各种各样的js代码库，如jQuery、Extjs、Dojo，可能在使用过程，就会产生函数冲突，为了解决函数冲突问题，我们通常采用自调用匿名函数解决此问题。




##  Javascript的事件

一、事件编程

1、什么是事件驱动式？

答：在JavaScript中，用户的行为（点击、移动）会被Javascript中的事件所捕获，并执行相应的处理程序，我们把这个过程就称之事件驱动式。

2、JavaScript中常用的事件

	onload   		： 	 页面加载完毕时触发

	onunload		： 	 页面卸载时触发(关闭)

	onblur		：	 失去焦点时触发

	onfocus		：   获得焦点时触发

	onclick		：   单击时触发

	onmouseover  ：   鼠标悬浮时触发

	onmouseout   ：   鼠标离开时触发 

	onmousedown ：	  鼠标按下时触发

	onmouseup	： 鼠标弹起时（释放）时触发

	onmousemove ： 鼠标移动时触发

	onchange		： 状态改变时触发

	onselect	    ： 文本框文本被选择时触发（input、textarea）

	onkeypress	    ： 键盘按下时触发（无法捕获功能键）

	onkeydown    ： 键盘按下时触发（可以捕获功能键）

	onkeyup 		： 键盘弹起时触发

	onsubmit		： 表单提交时触发  

   只有返回值为真时才能提交  否则不能提交

	onseset		： 表单重置时触发

3、事件绑定的方式分为三种:

行内绑定  

动态绑定

引入

4、获取对象的第二种方法

 document.getElementsByName(name值);  获得的对象是多个对象

5、获取的长度

 object.length




##  Javascript的内置对象(二)
一、数组对象 

1、什么是数组？

答：一组数据的集合

一维数组

二维数组

多维数组

在javascript中数组只有索引数组之分

2、数组的定义

	var arr=[值1,值2,值3];  		//隐式创建

	var arr=new Array(值1,值2,值3); //显示创建或直接实例化

	var array=new Array(size);       //显示创建并指定数组长度

3、数组的访问

4、定义文本下标数组

5、数组的分类

二、数组的遍历

1、通过for循环进行遍历输出

数组拥有一个属性length，标识数组长度

2、通过for…in…进行遍历输出

三、数组的常用系统函数

  pop()：该方法用于删除并返回数组元素中最后一个元素

  shift()：该方法用于删除并返回数组的第一个元素

  push()：该方法向数组末尾添加一个或多个元素，并返回添加后的数组长度

  unshift()：该方法是向数组开头添加一个或者多个元素，并返回添加后的数组长度

  reverse()：该方法用于颠倒数组元素的顺序

  sort()：该方法用于将数组进行排序

四、时间日期对象 date 类

1、Date对象的创建方式

  方式一：var date=new Date()  //创建一个当前时间

  方式二：var date=new Date(2014,8,10)  //指定年月日创建时间 写8实际上
  是9月份系统默认多一个月

  方式三：var date=new Date(“Jan 2,2008 10:21:22”)  //根据字符串创建对象

2、常用的时间类函数 

  date()：返回系统当前的日期和时间

  getDate()：从日期对象中返回一个月中的某一天

  getDay()：从日期对象中返回一周中的某一天

  getMonth()：从日期对象中返回月份

  getYear()：从日期对象中返回年份

  getHours()：从日期对象中返回小时

  getMinutes()：从日期对象中返回分钟

  getSeconds()：从日期对象中返回秒数

  getTime()：返回从1970年1月1日至今的毫秒数

  toLocaleString()：根据本地时间格式，把日期对象转换为字符串







 



