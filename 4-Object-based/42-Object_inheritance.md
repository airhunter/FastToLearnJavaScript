# 对象的继承

对象的继承实际上就是对javascipt特殊的prototype链的利用。方法很多，目前总结下来最为完美的方法只有一种。

> function GoodStudent\(\){  
>     this.type = 'Good'  
> }
>
> function Student\(name, age\){  
>     this.name = name;  
>     this.color = color;  
> }
>
> function extend\(Child, Parent\){  
>     var F = function\(\){};  
>     F.prototype = Parent.prototype;  
>     Child.prototype = new F\(\);  
>     Child.prototype.constructor = Child;  
> }
>
> extend\(Student, GoodStudent\);  
> var student1 = new Student\('Luck', 24\)  
> alert\(student1.type\);   //Good



