# itorable

ECMAScript 2015引入了iterable类型，Array、Map和Set都属于iterable类型。关于itorable也不会陌生，C++、Java等许多语言都有类似的知识点。

区别在于，在Javascript中需要通过`for...of`循环来使用itorable特性。

> var a = \[1, 2, 3\];  
> var m = new Map\(\[ \[1,'Jane'\], \[2, 'Jacky'\] \]\);
>
> for \(x of a\){  
>     console.log\(x\);  
> }  
>   
> for\(x of m\){  
>     console.log\(x\);  
> }

这里要说明一下Map在循环时，返回的是一个数组，第一元素是Key，第二个无素是Value。

#### 为什么不使用for...in

因为for...in循环的是对象的属性名称，



