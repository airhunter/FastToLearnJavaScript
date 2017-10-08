# 函数

其格式与大多数语言一样，只是需要以function打头，然后由于是动态类型语言，所以返回值类型不需要指定。定义方式如下：

> function foo\(x\){  
>     // do something  
>     return x;  
> }

如果没有指定return语句，函数也会有返回值，只是返回值是undefined.

还有一种特殊的定义方法，为Javascript所特有。

> var foo = function\(x\){  
>     // do something  
>     return x;  
> };

变量getSomething保存着函数本身，可以视为函数的别名，而函数本身实际上是一个匿名函数。

函数调用一个特别点是对于需要参传的函数，即使参数不传入程序也不会报错，只是函数的返回值为NaN。

函数还有一个内部可以使用的关键字arguments，可以把它视为一个数组，虽然它并不是。其保存着调用者传入的所有参数。这使得它有了一种有趣的特性，即使函数在定义时没有指定任何入参，但如果调用时传入了参数，那么通过arguments还是可以获取到这些入参。

最后再来说一下与arguments相似的rest参数，其用于保存所有未明确定义的变量。例子如下：

> function foo\(a, b, ...rest\){  
>     console.log\('a = ' + a\);  
>     console.log\('b = ' + b\);  
>     for \(var i in rest\){  
>         console.log\(i\);  
>     }  
> }



