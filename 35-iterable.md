# 迭代器

ECMAScript 2015引入了`iterable`类型，Array、Map和Set都属于`iterable`类型。关于`itorable`也不会陌生，C++、Java等许多语言都有类似的知识点。

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

因为`for...in`循环的是对象的属性名称，一个数组的索引实际上是被作为一个属性来保存的。所以如果给数组添加一个额外的属性后`for...in`这种形式的循环就会带来一些奇怪的现象。另外，`for...in`循环得到的值实际上是Key或索引，而`for...of`得到的是值。

> var arr = \[1,2,3,4,5\];  
> arr.name = 'ABC';  
> for \(var x in a\){  
>     console.log\(x\);    // '1','2','3','4','5','ABC'  
> }

#### forEach

我们还可以使用`itorable`的内置方法`forEach`方法，传入一个自定义函数即可。自定义函数的三个参数，按顺序分别为当前元素的值、当前元素的索引、对象本身，在下例中是数组a。

> var a = \[1,2,3\];
>
> a.forEach\(function\(elem, idx, arr\){  
>     console.log\(elem\);  
> }\);



