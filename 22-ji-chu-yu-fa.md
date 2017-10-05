# 基础语法

基础语法

#### 代码结束符

每个语句以`;`号结束。但JavaScript并不强制要求每个语句添加`;` 号。但了少记忆一个知识点，还是加上吧。

#### 语句块

代码段用`{...}`包裹。

> if \(finished\){
>
> // dosomething.
>
> }

#### 注释

`/* something */`和`//`两种注释风格同时支持。

#### 大小写

严格区分大小写

#### 字符串

`'abc'`单引号和`"abc"`双引号都可以表示字符串，并且两者没有区别。可以通过来`\`转义，与C++和Java等语法一致。

在ECMAScript 2015中可以通过\`\`来表示多行文本，类似于Python语言的三个引号的作用。

除了可以使用加号连接字符串，JavaScript还提供一了一种称为模板字符串的字符串连接方法，需要ECMAScript 2015支持。

> var FirstName = 'Smith';  
> var LastName = 'Wong';  
> var HelloMessage = 'Hello,${FirstName} ${LastName} , Nice to meet you!';

字符串的索引号从0开始，但即使索引越界也不会引起报错，而只是返回undefined。

字符串是一种不变量，但不同与Java或Python，尝试修改字符串中元素的值同样不会引起报错，只是没有任何效果而已。

#### 布尔运算

布尔值只有`true`和`false`两种（注意大小写），三种运算符分别为`&&`（与）、`||`（或）、`!`（非）。

#### null和undefined

`null`表示空，这与其它大多数语言一致。而`undefined`表示值未定义。

#### 数组

数组有两种表示方式

> \[1, 2, 3, 4, null, 'test', false\];
>
> new Arrary\(1,2,3,4\)

然后它有一些奇怪的特性有别于其它编程语言

修改数组的length属性会导致数组大小的变化。

> var arr = \[1,2,3\];  
> arr.length;    //3  
> arr.length = 6;  
> console.log\(arr\);               //\[1,2,3,null,null,null\]  
> arr.length = 2;  
> console.log\(arr\);              //\[1,2\]

如果给超过索引赋值，那么不只不会报错，反而会改变数组的大小。

> var arr = {1,2,3};  
> arr\[4\] = 99;  
> console.log\(arr\);       //\[1,2,3,null,99\]

#### 对象

对象在JavaScript中实际上是一种Key-Value集合，并且Key都是字符串类型，值的类型随意。

> var computer = {  
>     host : '192.168.1.101',  
>     memory : 16,  
>     harddisk : 2048,  
>     monitor : 24,  
>     cddriver : null };
>
> //获取对象的属性  
> computer.host; // '192.168.1.101'  
> computer.memory; // 16

如果Key包含特殊字符，就需要用`''或""`引号括起来，并且在访问时必须用`['abc']`的方式来访问。

> var computer = {  
>     'host-name' : '192.168.100.101' };
>
> console.log\(computer\['host-name'\]\);

访问一个不存在的属性不会报错，而是返回`undefined`

#### 变量

变量使用`var`声名。JavaScript是一种变量类型不固定的语言，所以可以做到b在声名时为数值，然后又赋值一个字符串给它。如例子中所展示的一样。

> var a;
>
> var b = 1;
>
> b = '1334''; //作为动态语言，b的值可能赋予任何类型的值，并可以反复修改。

变量也可以不使用var而直接使用，但这种情况下变量即为全局变量，容易引起各种难以调试的问题，所以不建议这样使用。为了强制要求声名变量。可以在代码第一行写上：

> 'use strict';

这是一个需要ECMAScript高版本才能支持的特性，并不是所有浏览器都能支持。好在对于不支持这个语法的浏览器也只会把这句话当成一般的字符串语句，不会引起任何错误。

