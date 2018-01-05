# 对象的封装

在Javascript中把属性与方法封装成一个对象是很简单的。

#### 封装的原始模式

> var Student = {  
>     name : '张三',  
>     gender : 24''  
> }

这样写实际上就已经完成了一个对象的封装，但这种写法有一个问题，即如果要生成一堆同类对象，这样写比较费时费力。

#### 封装改进型

> function Student\(name, gender\){  
>     return {  
>         name : name,  
>         color: color  
>     }  
> }





