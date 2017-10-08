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







