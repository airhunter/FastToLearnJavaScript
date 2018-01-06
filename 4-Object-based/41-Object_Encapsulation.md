# 对象的封装

在Javascript中把属性与方法封装成一个对象是很简单的。

#### 封装的原始模式

> var Student = {  
>     name : '张三',  
>     age : 24''  
> }

这样写实际上就已经完成了一个对象的封装，但这种写法有一个问题，即如果要生成一堆同类对象，这样写比较费时费力。

#### 封装改进型

> function Student\(name, age\){  
>     return {  
>         name : name,  
>         age: age  
>     }  
> }

生成对象就是函数调用即可：

> var student1 = Student\('小明',24\)
>
> var student2 = Student\('张三', 24\)

看着很像回事吧，但这种方式生成出来的实例之间没有内在联系，不能反映出他们是同一种类的对象。

#### 构造函数

通过构造函数生成的实例都会基于同一个原型对象，这在Javascript中称为构造函数模式。其与函数的区别在于，变量通过`this`绑定在实例对象上。并且生成实例需要使用`new`关键字。

> function Student\(name, age\){  
>     this.name = name;  
>     this.age = age;  
> }
>
> var student1 = Student\('小明',24\)
>
> var student2 = Student\('张三', 24\)

这时的student1与student2都会含有一个constructor属性，指向它们的构造函数。

> alert\(student1.constructor == Student\);    // true
>
> alert\(student2.constructor == Student\);    // true

通过instanceof运算符可以验证原型与实例之间的关系。

> alert\(student1 instanceof Student\);    // true
>
> alert\(student1 instanceof Student\);    // true

#### Prototype模式



