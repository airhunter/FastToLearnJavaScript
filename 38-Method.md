# 对象的方法

JavaScript并不是一个面向对象语言，因为他对面向对象三个特性的支持并不完整。所以导致了它在对象这部分内容时的特性很奇怪。其中一点就是this的应用。

在JavaScript中为一个对象添加一个方法是一件很简单的事情。

> var computer = {  
>     host = '192.168.100.90';  
>     memory = 16;  
>     addMemory : function\(x\){  
>         this.memory += x;  
>         return this.memory;  
>     }  
> };





