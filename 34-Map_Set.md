# Map和Set

ECMAScript 2015引入了Map和Set两种新的数据结构，Map与对象很类似，只是他的Key并不只支持字符串。Set与其它语言中的功能类似。

#### Map

Map可以有两种操作方法，一种是通过二维数组直接赋值。另一种是通过Map的内置方法来实现逐个添加Key-Value。如需要删除某个键值对，可以用delete删除。

> var m = new Map\(\[ \[1, 'Jane'\],\[2, 'Jacky'\] \]\);
>
> console.log\(m.get\(1\)\);
>
> var m = new Map\(\);  
> m.set\(1, 'Jane'\);  
> m.set\(2, ''Jacky\);
>
> console.log\(m.get\(1\)\);
>
> m.delete\(1\);
>
> console.log\(m.get\(1\)\)

#### Set

与大多数语言类似，用于存放不重复的值。

> var s = new Set\(\[1,2,3,4\]\);  
> s.add\(5\);  
> s.add\(3\);
>
> console.log\(s\);  
> s.delete\(3\);  
> console.log\(s\);



