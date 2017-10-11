# 作用域

JavaScript作用域看上去与C++、Java语言很相似，但实际上这种相似只是表面上，在很多情况下有许多特殊之处，有时甚至让人困惑。

#### 变量提升

JavaScript会把整个函数体中的变量声明语句提升至函数顶部，故下面的代码是不会报错的。但其结果为ABCDundefined，这是因为虽然提升了变量的声明，但不会一同提升变量`y`的赋值。

> 'use strict';
>
> function foo\(\){  
>     var x = 'ABCD' + y;  
>     console.log\(x\);  
>     var y = '1234';  
> }

#### 名字空间

因为所有全局变量都会绑定到`window`上，所以不同js文件中的同名变量会产生命名冲突。解决的方法之一是把自己的所有变量与函数都绑定到一个指定的全局变量中。

> var my = {};
>
> my.arr = \[1,2,3,4\];
>
> my.foo = function\(\){ return 1;};

#### 局部作用域

由于JavaScript在最初只有全局与函数二个局部作用域，所以像`for`循环语句块中的初始循环变量是没有局部作用域的。为了解决这个问题，ECMAScript 2015引入了let关键字，用`let`替代`var`可以申明一个具有语句块作用域的变量。

> 'use strict';
>
> function foo\(\){  
>     var sum = 0;  
>     for\(let i = 0; i &lt; 10; i++\){      // i在for循环外不存在  
>         sum += i;  
>     }  
>     return sum;  
> }

#### 常量

旧的JavaScript不支持常量声明，在ECMAScript 2015中，引入关键字`const`，当用`const`声明变量后，此变量即为常量。

> 'use strict';
>
> const MAX = 65535;



