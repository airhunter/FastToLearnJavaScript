# 对象的方法

JavaScript并不是一个面向对象语言，因为他对面向对象三个特性的支持并不完整。所以导致了它在对象这部分内容时的特性很奇怪。其中一点就是this的应用。

在JavaScript中为一个对象添加一个方法是一件很简单的事情。

> var computer = {  
>     host : '192.168.100.90',  
>     memory : 16,  
>     addMemory : function\(x\){  
>         this.memory += x;  
>         return this.memory;  
>     }  
> };

这个时候this的作用与其它面向对象语言的特性一致。

让我们换一种写法，然后看看this的奇怪特性。

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

为什么会有这些问题？因为this指向的是当前对象。当单独调用addMemory时，this指向着全局对象，即window。而把对象方法赋值给foo变量，this的指向仍然不正确。最重要的是，它不会报错。只是返回NaN或者其它你意料之外的值，至于this到底指向哪里，完全取决于你的代码是怎么写的。想完全绕过这个问题目前是不可能的，好在ECMA已经发现了这个问题，所以当你以use strcit开始书写代码的话，那么当这种情况发生时，会直接报错。而不是返回什么NaN。

