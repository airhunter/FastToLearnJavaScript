# 函数

其格式与大多数语言一样，只是需要以`function`打头，然后由于是动态类型语言，所以返回值类型不需要指定。定义方式如下：

> function foo\(x\){  
>     // do something  
>     return x;  
> }

如果没有指定`return`语句，函数也会有返回值，只是返回值是`undefined`.

还有一种特殊的定义方法，为Javascript所特有。

> var foo = function\(x\){  
>     // do something  
>     return x;  
> };

变量`foo`保存着函数本身，可以视为函数的别名，而函数本身实际上是一个匿名函数。

函数调用一个特别点是对于需要参传的函数，即使参数不传入程序也不会报错，只是函数的返回值为`NaN`。

函数还有一个内部可以使用的关键字`arguments`，可以把它视为一个数组，虽然它并不是。其保存着调用者传入的所有参数。这使得它有了一种有趣的特性，即使函数在定义时没有指定任何入参，但如果调用时传入了参数，那么通过`arguments`还是可以获取到这些入参。

最后再来说一下与`arguments`相似的`rest`参数，其用于保存所有未明确定义的变量。例子如下：

> function foo\(a, b, ...rest\){  
>     console.log\('a = ' + a\);  
>     console.log\('b = ' + b\);  
>     for \(var i in rest\){  
>         console.log\("rest\[" + i + "\] = " + rest\[i\]\);  
>     }  
> }

#### 箭头函数

> x =&gt; x \* x

这就是剪头函数的表达方式，相当于普通函数：

> function\(x\){  
>     return x \* x;  
> }

箭头函数需要ECMAScript 2016支持。对于相对复杂的含有多条语句的函数，这时就不能写得如此简略了。

> x =&gt; {  
>     if \( x &gt; 0\){  
>         return x \* x;  
>     }else{  
>         return - x \* x;  
>     }  
> }

如果有多个形参情况：

> //两参数情况  
> \(x, y\) =&gt; x \* y
>
> //无参数:  
> \(\) =&gt; 1000
>
> //可变参数  
> \(x, y, ...lst\) =&gt; {  
>     var sum = x + y  
>     for \(int i = 0; i &lt; lst.length; i++\){  
>         sum += lst\[i\];  
>     }  
>     return sum

#### 生成器（Generator\)

JavaScript中的generator是借鉴了Python中的generator概念，如果对Python有相当的经验，那么理解起来会十分容易。对于没有经验的读者，可以理解为生成器是一种可以返回多次结果，并且记住中间状态的函数。



