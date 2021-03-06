# 对象的方法

JavaScript并不是一个面向对象语言，因为他对面向对象三个特性的支持并不完整。所以导致了它在对象这部分内容时的特性很奇怪。其中一点就是`this`的应用。

#### this

在JavaScript中为一个对象添加一个方法是一件很简单的事情。

> var computer = {  
>     host : '192.168.100.90',  
>     memory : 16,  
>     addMemory : function\(x\){  
>         this.memory += x;  
>         return this.memory;  
>     }  
> };

这个时候`this`的作用与其它面向对象语言的特性一致。

让我们换一种写法，然后看看`this`的奇怪特性。

> function addMemory\(x\){  
>     this.memory += x;  
>     return this.memory;  
> }
>
> var computer = {  
>     host : '192.168.100.90',  
>     memory : 16,  
>     addM : addMemory  
> };
>
> computer.addM\(16\);    //right, return 32.  
> addMemory\(16\);       //wrong, return NaN
>
> var foo = computer.addM;  
> foo\(16\);            //wrong, return NaN

为什么会有这些问题？因为`this`指向的是当前对象。当单独调用addMemory时，`this`指向着全局对象，即`window`。而把对象方法赋值给foo变量，`this`的指向仍然不正确。最重要的是，它不会报错。只是返回`NaN`或者其它你意料之外的值，至于`this`到底指向哪里，完全取决于你的代码是怎么写的。想完全绕过这个问题目前是不可能的，好在ECMA已经发现了这个问题，所以当你以`use strcit`开始书写代码的话，那么当这种情况发生时，会直接报错。而不是返回什么`NaN`。

#### apply和call

因为`this`的指向如此不靠谱，我们也许会想干脆自己指定`this`的值，这在JavaScript中是可以做到的。使用`apply`函数，它有2个参数，第一个参数是需要绑定的`this`变量，第二个参数是函数的参数（数组）。另一个方法是`call`，与`apply`的不同点是，`call`没有把函数的入参打包成数组，只需要按顺序传入参数即可。继续拿上面的例子：

> AddMemory.apply\(computer, \[16\]\);     //right, return 32  
> AddMemory.call\(computer, 16\);          //right, return 32

#### 装饰器

由于JavaScript的所有对象都是动态的，即使内置的函数，我们都可以重新指向。

如果我们想统计一下代码一共调用了多少次`parseInt`, 可以自己换掉内置的`parseInt`方法，让我们来演试一下。

> var count = 0;
>
> var oldParseInt = parseInt;   // save the original function
>
> window.parseInt = function\(\){  
>      count += 1;  
>      return oldParseInt.apply\(null, arguments\);  
> };



