# 数组内置方法

#### IndexOf

indexOf\(\)与String同名方法类似，可以用来查找指定元素的位置。

#### slice

slice\(\)相当于String中的substring\(\)，它截取数组指定的部分，产生一个新的数组。如果不传入任何参数，那么相当于复制了整个数组。

> var arr = \[1,2,3,4,5,6,7,8\];  
> arr.slice\(0, 3\);  
> arr.slice\(3\);

#### push和pop

push\(\)用来向数组未尾添加元素，注意是可以添加多个无素。pop\(\)用于把数组最后一个元素删除，并返回删除的那个元素。

> var arr = \[1,2,3,4\];  
> arr.push\(5,6,7\);  
> arr.pop\(\);

#### unshift和shift

向数组头部添加元素与删除元素。

> var arr = \[12,3,4\];  
> arr.unshift\(5,6\);  
> arr.shift\(\);

#### sort

与很多语言中数组或列表的同名方法类似，用于排序数据元素。

#### reverse

reverse\(\)反转数组中的每一个元素。与其它很多语言中的同名方法类似。

#### splice

splice\(\)添加删除元素的万能方法，并返回删除的元素。

> var arr = \[1,2,3,4,5,6\];
>
> arr.splice\(2,3,7,8\); 从索引2开始删除3个元素，然后再添加7,8到索引2位置上。整个语句会返回删除的\[3,4,5\]
>
> console.log\(arr\);   // \[1,2,7,8,6\]

#### concat

用于连接两个数组，返回一个新的数组。

> var arr = \[1,2,3,4\];  
> var news = arr.concat\(\['A', 'B'\]\);

#### join

用于将数组中的所有元素用指定的分隔符连接起来，返回连接后的字符串。

> var arr = \[1,2,3,4,5,6\];  
> console.log\(arr.join\(','\)\)  // '1,2,3,4,5,6'


