# 闭包

闭包的定义相当的抽象，不容易理解。所以换个简单的理解就是以子函数作为媒介，将父函数包裹的内部函数、变量作为一个整理（容器），以供外部使用的函数。

它的两大作用是：读取函数内部变量和让这些变量的值保持在内存中。（类似于C++的static关键字效果）

一个用于解释闭包用途的例子：

> function f1\(\){  
>     var n = 999;  
>     function f2\(\){  
>         alert\(n\);  
>     }  
>     return f2;  
> }
>
> var result = f1\(\);
>
> result\(\);     //999

将值保持在内存中的例子：

> function f1\(\){  
>     var n = 999;  
>     nAdd = function\(\){n+1;}  
>     function f2\(\){  
>         alert\(n\);  
>     }  
>     return f2;  
> }
>
> var result = f1\(\);
>
> result\(\);             //999
>
> nAdd\(\);
>
> result\(\);            // 1000



