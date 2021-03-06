# 高阶函数

#### map

如果需要把一个数组中的每个元素的平方数保存起来，形成一个新的数组可以使用map方法。

> var arr = \[1,2,3,4,5,6,7\];
>
> arr.map\(function\(x\){  
>      return x\*x;}\);

#### reduce

如果需要将一个函数的结果作为下一次调用函数的入参，那么可以用reduce。

> var arr = \[1,2,3,4,5,6,7,8,9,10\];
>
> arr.reduce\(function\(x,y\){ return x \* y;}\);

#### filter

用于把数组的某些元素过滤掉，然后返回剩下的元素。filter的入参函数可以有三个参数，按顺序依次是元素本身，元素索引，数组本身。

> var arr = \[1,2,3,4,5,6,7,8,9\];
>
> arr.filter\(function\(x\){ return x % 2 === 0;}\);

#### sort

sort函数可以直接使用，这时使用其内置的算法进行排序，但其结果一般情况下都不会是你想要的。因为其内置的方法会先将数值转换字符串，然后再对字符串排序……好在我们可以用自定义的函数替换之。

另一个特点是sort函数不同与上述高阶函数，他会修改数组本身的数据。

> var arr = \[89,20, 1, 60, 70\];
>
> arr.sort\(function\(x ,y\){  
>     if \(x &lt; y\) return -1;  
>     else if\(x &gt; y\) return 1;  
>     else return 0;}\);
>
> console.log\(arr\);



