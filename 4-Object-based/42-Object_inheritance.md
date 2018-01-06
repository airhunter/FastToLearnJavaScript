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
> extend\(GoodStudent, Student\);  
> var student1 = new GoodStudent\('Luck', 24\)  
> alert\(student1.type\);   //Good

#### class继承

在ES6之前，上述方法是Javsscript继承对象的唯一方案。但从ES6开始，`class`终于被引入Javascript。

之前采用构造函数来生成实例的方法可以被`class`来改写，更符合OOP编程的风格。

> class Student{  
>      constructor\(name, age\){  
>          this.name = name;  
>          this.age = age;  
>      }
>
> say\_hello\(\){  
>     alert\('Hello, ' + this.name\);  
> }
>
> }

原先复杂的继承功能也可以被`extends`关键词取代。

> class GoodStudent extends Student{  
>     constructor\(name, grade\){  
>         super\(name\);  
>         this.grade = grade;  
>     }
>
>
> myGrade(){  
>      alert\('I am at grade ' + this.grade\);  
> }
> 
>
> }

{%raw%} {%rawend%}



