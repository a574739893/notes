- 转换
	- [toString()](#toString)
	- [valueOf()](#valueOf)
	- [toLocaleString()](#toLocaleString)
	- [join()](#join)
- 堆、栈
	- [push()](#push)
   	- [pop()](#pop)
   	- [shift()](#shift)
   	- [unshift()](#unshift)
- 排序
   	- [reverse()](#reverse)
   	- [sort()](#sort)
- 操作
   	- [concat()](#concat)
   	- [splice()](#splice)
   	- [slice()](#slice)
- 位置
   	- [indexOf()](#indexOf)
   	- [lastIndexOf()](#lastIndexOf)
- 迭代
   	- [every()](#every)
   	- [filter()](#filter)
   	- [map()](#map)
   	- [some()](#some)
   	- [forEach()](#forEach)
- 归并
   	- [reduce()](#reduce)
   	- [reduceRight()](#reduceRight)



<br>
<br>
<br>
<br>
<br>

<h6 id="toString" style="background:#676767;color:#fff;padding: 10px;">toString</h6>

```
//  返回数组中每个值的字符串形式拼接，以逗号分隔的字符串
var color = ["red", "blue", "green"];
console.log(color.toString());  // red,blue,green
```

<br>
<br>

<h6 id="valueOf" style="background:#676767;color:#fff;padding: 10px;">valueOf</h6>

```
//  返回 Array 对象的原始值
var array = [1, 2, 3];
var array2 = array.valueOf();
console.log(array2);    // Array(3) [ 1, 2, 3 ]
```
<br>
<br>

<h6 id="toLocaleString" style="background:#676767;color:#fff;padding: 10px;">toLocaleString</h6>

```
//  把数组转换为本地字符串
var array = [1, 2, 3];
var array2 = array.toLocaleString();
console.log(array2) //  1, 2, 3
```
<br>
<br>


<h6 id="join" style="background:#676767;color:#fff;padding: 10px;">join</h6>

```
//  通过指定的分割符进行分割，然后返回一个字符串
var array = [1, 2, 3];
var array2 = array.jon(".");
console.log(array2); // 1.2.3
```
<br>
<br>

<h6 id="push" style="background:#676767;color:#fff;padding: 10px;">push</h6>

```
//  向数组末尾添加元素，并返回
var array = [1, 2, 3];
array.push(4, 5, 6);
console.log(array)  // Array(6) [ 1, 2, 3, 4, 5, 6 ]
```

<br>
<br>

<h6 id="pop" style="background:#676767;color:#fff;padding: 10px;">pop</h6>

```
//  删除数组最后一个元素，并返回
var array = [1, 2, 3];
array.pop();
console.log(array)  // Array [ 1, 2 ]
```

<br>
<br>

<h6 id="shift" style="background:#676767;color:#fff;padding: 10px;">shift</h6>

```
//  把数组第一个元素删除，并返回第一个元素的值
var array = [1, 2, 3];
array.shift();
console.log(array); // Array [ 2, 3 ]
```

<br>
<br>

<h6 id="unshift" style="background:#676767;color:#fff;padding: 10px;">unshift</h6>

```
//  向数组开头添加一个或多个元素，并返回
var array = [1, 2, 3];
array.unshift(4, 5, 6);
console.log(array); // Array(6) [ 4, 5, 6, 1, 2, 3 ]
```

<br>
<br>

<h6 id="reverse" style="background:#676767;color:#fff;padding: 10px;">reverse</h6>

```
//  颠倒数组中元素的顺序
var array = [1, 2, 3];
array.reverse(4, 5, 6);
console.log(array); // Array(3) [ 3, 2, 1 ]
```

<br>
<br>

<h6 id="sort" style="background:#676767;color:#fff;padding: 10px;">sort</h6>

```
//  对数组的元素进行排序
var array = [10, 5, 40, 25, 1000, 1];
array.sort();
console.log(array); // Array(6) [ 1, 1000, 25, 40, 5, 10 ]
```

<br>
<br>

<h6 id="concat" style="background:#676767;color:#fff;padding: 10px;">concat</h6>

```
//  用于连接两个或多个数组
var array = [1, 2, 3];
var array2 = [4, 5];
var array3 = [6, 7];

console.log(array2.concat(array, array3)); Array(7) [ 4, 5, 1, 2, 3, 6, 7 ]
```

<br>
<br>

<h6 id="splice" style="background:#676767;color:#fff;padding: 10px;">splice</h6>

```
//  添加/删除
//  如果是删除，返回被删除的元素（数组）
var array = [1, 2, 3];
array.splice(1, 1);
console.log(array); //  Array [ 1, 3 ]
array.splice(1, 0, 4);
console.log(array); //  Array(3) [ 1, 4, 3 ]
```

<br>
<br>

<h6 id="slice" style="background:#676767;color:#fff;padding: 10px;">slice</h6>

```
//  从以有的数组中返回选定的元素
var array = [1, 2, 3];
var array2 = array.slice(0, 2);
console.log(array2) //  Array [ 1, 2 ]
```

<br>
<br>
https://www.jianshu.com/p/24547d4e565f
  