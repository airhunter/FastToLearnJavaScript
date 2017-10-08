# 作用域

作用域的绝大多数特性与其它语言并没有不同，所以我们只聊一下特别的部分。

#### 变量提升

JavaScript会把整个函数体中的变量声明语句提升至函数顶部，故下面的代码是不会报错的。但其结果为ABCDundefined，这是因为虽然提升了变量的声明，但不会一同提升变量`y`的赋值。

> 'use strict';
>
> function foo\(\){  
>     var x = 'ABCD' + y;  
>     console.log\(x\);  
>     var y = '1234';  
> }



