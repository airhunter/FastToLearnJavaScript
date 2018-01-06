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
> var student1 = new Student\('小明',24\)
>
> var student2 = new Student\('张三', 24\)

这时的student1与student2都会含有一个constructor属性，指向它们的构造函数。

> alert\(student1.constructor == Student\);    // true
>
> alert\(student2.constructor == Student\);    // true

通过instanceof运算符可以验证原型与实例之间的关系。

> alert\(student1 instanceof Student\);    // true
>
> alert\(student1 instanceof Student\);    // true

#### Prototype模式

构造函数的问题是如果对象中包括一些类属性，或者函数，每次通过构造函数生成的对象都实际上是复制一份内容。会多占用不少内存。

> function Student\(name, age\){  
>     this.name = name;  
>     this.age = age;  
>     this.say\_hello = function\(\){alert\('Hello' + this.name\);};  
> }
>
> var student1 = new Student\('小明',24\)
>
> var student2 = new Student\('张三', 24\)
>
> {% raw %} alert\(student1.say\_hello == student1.say\_hello\) // false{% rawend %}

每个构造函数都有一个prototype属性，指向另一个对象。这个对象的所有属性和方法都会被构造函数的实例继承。所以我们可以把希望每个实例都不会变更的属性或方法定义在prototype对象上。
> function Student\(name, age\){  
>     this.name = name;  
>     this.age = age;  
> }
> Student.prototype.say\_hello = function\(\){alert\('Hello' + this.name\);}; 
>
> var student1 = new Student\('小明',24\)
>
> var student2 = new Student\('张三', 24\)
>
> {% raw %} alert\(student1.say\_hello == student1.say\_hello\) // true{% rawend %}

#### 常用函数

**isPrototypeOf()**
用来验证实例与某个prototype对象的关系
> alert(Student.prototype.isPrototypeOf(student1))

**hasOwnProperty()**
用来验证属性是否是本地属性还是继承自prototype对象。
> alert(student1.hasOwnProperty('name')); //true

**in**
可用来遍历对象的所有属性，也可以用来判断某个实例是否含有某个属性。
> alert('name' in student1) //true
> for(var prop in student1){
>  console.log('student1[' + prop + ']=' + student1[prop]);
> }




