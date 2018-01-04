# 对象内置方法

hasOwnProperty\(\)用于判断一个属性是否是对象自身拥有的，而不是通过继承得到的。

> var computer = {  
>      host : '192.168.100.101'  
> }
>
> console.log\(computer.hasOwnProperty\('host'\)\);           //true  
> console.log\(computer.hasOwnProperty\('toString'\)\);      //false



