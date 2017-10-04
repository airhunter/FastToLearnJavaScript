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

`'abc'`单引号和`"abc"`双引号都可以表示字符串，并且两者没有区别。

#### 布尔运算

布尔值只有`true`和`false`两种（注意大小写），三种运算符分别为`&&`（与）、`||`（或）、`!`（非）。

#### null和undefined

`null`表示空，这与其它大多数语言一致。而`undefined`表示值未定义。

#### 数组

数组有两种表示方式

> \[1, 2, 3, 4, null, 'test', false\];
>
> new Arrary\(1,2,3,4\)

然后它有一些奇怪的特性有别于其它编程语言。

#### 对象

对象在JavaScript中实际上是一种Key-Value集合，并且Key都是字符串类型，值的类型随意。

> var computer = {  
>     host = '192.168.1.101',  
>     memory = 16,  
>     harddisk = 2048,  
>     monitor = 24,  
>     cddriver = null };
>
> //获取对象的属性  
> computer.host; // '192.168.1.101'  
> computer.memory; // 16

#### 变量

变量使用`var`申请。

> var a;
>
> var b = 1;





