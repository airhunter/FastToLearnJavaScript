# 函数

其格式与大多数语言一样，只是需要以function打头，然后由于是动态类型语言，所以返回值类型不需要指定。定义方式如下：

> function getSomething\(x\){  
>     // do something  
>     return x;  
> }

如果没有指定return语句，函数也会有返回值，只是返回值是undefined.

还有一种特殊的定义方法，为Javascript所特有。

> var getSomething = function\(x\){  
>     // do something  
>     return x;  
> };

变量getSomething保存着函数本身，可以视为函数的别名，而函数本身实际上是一个匿名函数。

函数调用一个特别点是对于需要参传的函数，即使参数不传入程序也不会报错，只是函数的返回值为NaN。



