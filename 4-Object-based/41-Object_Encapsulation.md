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





