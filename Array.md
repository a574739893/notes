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


- [Array.from()](#Array.from)
- [Array.isArray()](#Array.isArray)
- [Array.of()](#Array.of)
- [Array.copyWithin()](#Array.copyWithin)
- [Array.entries()](#Array.entries)
- [Array.fill()](#Array.fill)
- [Array.find()](#Array.find)
- [Array.findIndex()](#Array.findIndex)
- [Array.flat()](#Array.flat)
- [Array.flatMap()](#Array.flatMap)
- [Array.includes()](#Array.includes)
- [Array.keys()](#Array.keys)
- [Array.lastIndexOf()](#Array.lastIndexOf)
- [Array.values()](#Array.values)






<h6 id="Array.aaa" style="background:#676767;color:#fff;padding: 10px;">Array.aaa</h6>

```
//  
```
<br>
<br>


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

  


<h6 id="Array.from" style="background:#676767;color:#fff;padding: 10px;">Array.from</h6>

```
//  类数组、可迭代对象中，创建一个新数组
Array.from('foo'); 
// ["f", "o", "o"]

let s = new Set(['foo', window]); 
Array.from(s); 
// ["foo", window]

let m = new Map([[1, 2], [2, 4], [4, 8]]);
Array.from(m); 
// [[1, 2], [2, 4], [4, 8]]
```

<br>
<br>


<h6 id="Array.isArray" style="background:#676767;color:#fff;padding: 10px;">Array.isArray</h6>

```
// 用于确定是否是一个 Array
Array.isArray([1, 2, 3]);  
// true
Array.isArray({foo: 123}); 
// false
Array.isArray("foobar");   
// false
Array.isArray(undefined);  
// false
```
<br>
<br>


<h6 id="Array.of" style="background:#676767;color:#fff;padding: 10px;">Array.of</h6>

```
//  Array.of(7) 创建一个具有单个元素 7 的数组，而 Array(7) 创建一个长度为7的空数组
```
<br>
<br>


<h6 id="Array.copyWithin" style="background:#676767;color:#fff;padding: 10px;">Array.copyWithin</h6>

```
//  浅复制数组
let numbers = [1, 2, 3, 4, 5];

numbers.copyWithin(-2);
// [1, 2, 3, 1, 2]

numbers.copyWithin(0, 3);
// [4, 5, 3, 4, 5]

numbers.copyWithin(0, 3, 4);
// [4, 2, 3, 4, 5]

numbers.copyWithin(-2, -3, -1);
// [1, 2, 3, 3, 4]

[].copyWithin.call({length: 5, 3: 1}, 0, 3);
// {0: 1, 3: 1, length: 5}

// ES2015 Typed Arrays are subclasses of Array
var i32a = new Int32Array([1, 2, 3, 4, 5]);

i32a.copyWithin(0, 2);
// Int32Array [3, 4, 5, 4, 5]

// On platforms that are not yet ES2015 compliant: 
[].copyWithin.call(new Int32Array([1, 2, 3, 4, 5]), 0, 3, 4);
// Int32Array [4, 2, 3, 4, 5]
```
<br>
<br>


<h6 id="Array.entries" style="background:#676767;color:#fff;padding: 10px;">Array.entries</h6>

```
//  返回一个新的 Array iterator 对象
var array1 = ['a', 'b', 'c'];

var iterator1 = array1.entries();

console.log(iterator1.next().value);
// expected output: Array [0, "a"]
```
<br>
<br>


<h6 id="Array.every" style="background:#676767;color:#fff;padding: 10px;">Array.every</h6>

```
//  测试数组内元素是否能通过某个函数的测试
var array = [2, 3, 4];

console.log(array.every(function (value) {
	return value > 1;
}))  
// true
```
<br>
<br>

<h6 id="Array.fill" style="background:#676767;color:#fff;padding: 10px;">Array.fill</h6>

```
//  用固定值填充一个数组
[1, 2, 3].fill(4);               // [4, 4, 4]
[1, 2, 3].fill(4, 1);            // [1, 4, 4]
[1, 2, 3].fill(4, 1, 2);         // [1, 4, 3]
[1, 2, 3].fill(4, 1, 1);         // [1, 2, 3]
[1, 2, 3].fill(4, 3, 3);         // [1, 2, 3]
[1, 2, 3].fill(4, -3, -2);       // [4, 2, 3]
[1, 2, 3].fill(4, NaN, NaN);     // [1, 2, 3]
[1, 2, 3].fill(4, 3, 5);         // [1, 2, 3]
Array(3).fill(4);                // [4, 4, 4]
[].fill.call({ length: 3 }, 4);  // {0: 4, 1: 4, 2: 4, length: 3}

// Objects by reference.
var arr = Array(3).fill({}) // [{}, {}, {}];
arr[0].hi = "hi"; // [{ hi: "hi" }, { hi: "hi" }, { hi: "hi" }]
```
<br>
<br>


<h6 id="Array.aaa" style="background:#676767;color:#fff;padding: 10px;">Array.aaa</h6>

```
//  创建一个数组，包含通过函数测试的所有元素
var array = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

console.log(array.filter( function (word) {
	return word.length > 6;
}))
```
<br>
<br>



<h6 id="Array.find" style="background:#676767;color:#fff;padding: 10px;">Array.find</h6>

```
// 返回数组中通过测试函数的第一个元素的值
var array = [5, 12, 8, 130, 44];

console.log(array.find(function (element) {
	return element > 10
}))
//	12
```
<br>
<br>


<h6 id="Array.findIndex" style="background:#676767;color:#fff;padding: 10px;">Array.findIndex</h6>

```
//  返回数组中通过测试函数的第一个元素的索引
var array = [5, 12, 8, 130, 44];

console.log(array.findIndex(function (element) {
	return element > 10
}))
//	1
```
<br>
<br>



<h6 id="Array.aaa" style="background:#676767;color:#fff;padding: 10px;">Array.aaa</h6>

```
//  按照可指定的深度递归遍历数组，并将所有元素与遍历的子数组合并为一个新数组
var arr1 = [1, 2, [3, 4]];
arr1.flat(); 
// [1, 2, 3, 4]

var arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

var arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

//使用 Infinity 作为深度，展开任意深度的嵌套数组
arr3.flat(Infinity); 
// [1, 2, 3, 4, 5, 6]
```
<br>
<br>

<h6 id="Array.flatMap" style="background:#676767;color:#fff;padding: 10px;">Array.flatMap</h6>

```
//  使用映射函数映射每个元素，然后将结果压缩成一个新数组
var arr1 = [1, 2, 3, 4];

arr1.map(x => [x * 2]); 
// [[2], [4], [6], [8]]

arr1.flatMap(x => [x * 2]);
// [2, 4, 6, 8]

// 只会将 flatMap 中的函数返回的数组 “压平” 一层
arr1.flatMap(x => [[x * 2]]);
// [[2], [4], [6], [8]]
```
<br>
<br>

<h6 id="Array.forEach" style="background:#676767;color:#fff;padding: 10px;">Array.forEach</h6>

```
//  循环
var array1 = ['a', 'b', 'c'];

array1.forEach(function(element) {
  console.log(element);
});
```
<br>
<br>


<h6 id="Array.includes" style="background:#676767;color:#fff;padding: 10px;">Array.includes</h6>

```
//  判断数组是否包含一个指定的值
var array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

var pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false
```
<br>
<br>

<h6 id="Array.indexOf" style="background:#676767;color:#fff;padding: 10px;">Array.indexOf</h6>

```
//  找到给定元素的第一个索引
var beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1
```
<br>
<br>


<h6 id="Array.keys" style="background:#676767;color:#fff;padding: 10px;">Array.keys</h6>

```
//  返回一个包含数组中每个索引键的 Array Iterator 对象
var array1 = ['a', 'b', 'c'];
var iterator = array1.keys(); 
  
for (let key of iterator) {
  console.log(key); // expected output: 0 1 2
}

```
<br>
<br>


<h6 id="Array.lastIndexOf" style="background:#676767;color:#fff;padding: 10px;">Array.lastIndexOf</h6>

```
//  返回指定元素在数组中最后一个索引
var animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];

console.log(animals.lastIndexOf('Dodo'));
// expected output: 3

console.log(animals.lastIndexOf('Tiger'));
// expected output: 1
```
<br>
<br>


<h6 id="Array.map" style="background:#676767;color:#fff;padding: 10px;">Array.map</h6>

```
//  每个元素调用函数后，返回结果
var array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```
<br>
<br>


<h6 id="Array.reduce" style="background:#676767;color:#fff;padding: 10px;">Array.reduce</h6>

```
//  每个元素执行函数，将其结果汇总为单个返回值
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

// 1 + 2 + 3 + 4
console.log(array1.reduce(reducer));
// expected output: 10

// 5 + 1 + 2 + 3 + 4
console.log(array1.reduce(reducer, 5));
// expected output: 15
```
<br>
<br>


<h6 id="Array.reduceRight" style="background:#676767;color:#fff;padding: 10px;">Array.reduceRight</h6>

```
//  接受一个函数作为累加器和数组每个值（从右到左）减少为单值
const array1 = [[0, 1], [2, 3], [4, 5]].reduceRight(
  (accumulator, currentValue) => accumulator.concat(currentValue)
);

console.log(array1);
// expected output: Array [4, 5, 2, 3, 0, 1]
```
<br>
<br>


<h6 id="Array.some" style="background:#676767;color:#fff;padding: 10px;">Array.some</h6>

```
//  是否至少一个元素通过函数的测试
var array = [1, 2, 3, 4, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true

```
<br>
<br>

<h6 id="Array.some" style="background:#676767;color:#fff;padding: 10px;">Array.some</h6>

```
//  返回一个新的 Array Iterator 对象，包含每个索引的值
const array1 = ['a', 'b', 'c'];
const iterator = array1.values();

for (const value of iterator) {
  console.log(value); // expected output: "a" "b" "c"
}
```
<br>
<br>