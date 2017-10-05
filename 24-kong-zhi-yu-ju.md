# 条件语句

语法结构与C++、Java语言完全一致。当条件不是布尔变量时，JavaScript把`null`、`undefined`、`0`、`NaN`和空字符串`‘’`都会视为`false`，其他值都认为是`true`。

> var score = 98;  
> if \(score &gt;= 90\){  
>           alert\('Perfect'\);  
> }else if\(score &gt;= 80\){  
>           alert\('Good'\)  
> }else if\(score &gt;= 60\){  
>           alert\('Not Bad'\)  
> }else{  
>           alert\('Bad'\);  
> }

# 循环语句

#### for 和 for...in

`for`循环支持两种方式，普通的`for`以及`for...in`形式。

> var x = 0;
>
> for \(var i = 1; i &lt; 10; i++\){  
>        x = x + i;  
> };
>
> console.log\(x\);
>
> var arr = \[1,2,3,4,5,6,7\];
>
> for \(var i in arr\){  
>      console.log\(i\);  
> }

`for...in`形式中可以用在所有的容器类型中，像对象、数组都可以。

#### while





