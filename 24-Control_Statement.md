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

`for...in`形式中可以用在所有的容器类型中，像对象、数组都可以。需要注意的是，在循环数组时，取出的是元素的索引，而不是值。因为数组也是对象，其元素的索引被作为对象的属性存储了起来。

#### while和do...while

语法与C++、Java一致，无变化。

> var x = 1;  
> var sum = 0;
>
> while\(x &lt; 100\){  
>     sum += x;  
> }
>
> console.log\(sum\);
>
> var x = 1;  
> var sum = 0;  
> do{  
>      sum += x;  
> }while\(x &lt; 100\);
>
> console.log\(sum\);



