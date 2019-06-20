- 转换
	- [Array.prototype.toString()](#Array.prototype.toString)
	- [Array.prototype.toLocaleString()](#Array.prototype.toLocaleString)
	- [Array.prototype.join()](#Array.prototype.join)
- 堆、栈
	- [Array.prototype.push()](#Array.prototype.push)
	- [Array.prototype.pop()](#Array.prototype.pop)
	- [Array.prototype.shift()](#Array.prototype.shift)
	- [Array.prototype.unshift()](#Array.prototype.unshift)
- 排序
	- [Array.prototype.reverse()](#Array.prototype.reverse)
	- [Array.prototype.sort()](#Array.prototype.sort)
- 操作
	- [Array.prototype.concat()](#Array.prototype.concat)
	- [Array.prototype.splice()](#Array.prototype.splice)
	- [Array.prototype.slice()](#Array.prototype.slice)
- 位置
	- [Array.prototype.indexOf()](#Array.prototype.indexOf)
- 迭代
	- [Array.prototype.every()](#Array.prototype.every)
	- [Array.prototype.filter()](#Array.prototype.filter)
	- [Array.prototype.map()](#Array.prototype.map)
	- [Array.prototype.some()](#Array.prototype.some)
	- [Array.prototype.forEach()](#Array.prototype.forEach)
- 归并
	- [Array.prototype.reduce()](#Array.prototype.reduce)
	- [Array.prototype.reduceRight()](#Array.prototype.reduceRight)


- [Array.from()](#Array.from)
- [Array.isArray()](#Array.isArray)
- [Array.of()](#Array.of)
- [Array.prototype.copyWithin()](#Array.prototype.copyWithin)
- [Array.prototype.entries()](#Array.prototype.entries)
- [Array.prototype.fill()](#Array.prototype.fill)
- [Array.prototype.find()](#Array.prototype.find)
- [Array.prototype.findIndex()](#Array.prototype.findIndex)
- [Array.prototype.flat()](#Array.prototype.flat)
- [Array.prototype.flatMap()](#Array.prototype.flatMap)
- [Array.prototype.includes()](#Array.prototype.includes)
- [Array.prototype.keys()](#Array.prototype.keys)
- [Array.prototype.lastIndexOf()](#Array.prototype.lastIndexOf)
- [Array.prototype.values()](#Array.prototype.values)






<br>
<br>
<br>
<br>
<br>


<h6 id="Array.prototype.toString" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.toString</h6>

```
//  返回数组中每个值的字符串形式拼接，以逗号分隔的字符串
var color = ["red", "blue", "green"];
console.log(color.toString());  // red,blue,green
```

<br>
<br>

<h6 id="Array.prototype.toLocaleString" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.toLocaleString</h6>

```
//  把数组转换为本地字符串
var array = [1, 2, 3];
var array2 = array.toLocaleString();
console.log(array2) //  1, 2, 3

```
<br>
<br>


<h6 id="Array.prototype.join" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.join</h6>

```
//  通过指定的分割符进行分割，然后返回一个字符串
var array = [1, 2, 3];
var array2 = array.jon(".");
console.log(array2); // 1.2.3
（使用四中不同的分隔符连接元素）（连接类数组对象）
```
<br>
<br>

<h6 id="Array.prototype.push" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.push</h6>

```
//  向数组末尾添加元素，并返回
var array = [1, 2, 3];
array.push(4, 5, 6);
console.log(array)  // Array(6) [ 1, 2, 3, 4, 5, 6 ]
（合并两个数组）（像数组一样使用对象）
```
<br>
<br>

<h6 id="Array.prototype.pop" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.pop</h6>

```
//  删除数组最后一个元素，并返回
var array = [1, 2, 3];
array.pop();
console.log(array)  // Array [ 1, 2 ]
```

<br>
<br>

<h6 id="Array.prototype.shift" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.shift</h6>

```
//  把数组第一个元素删除，并返回第一个元素的值
var array = [1, 2, 3];
array.shift();
console.log(array); // Array [ 2, 3 ]
```

<br>
<br>

<h6 id="Array.prototype.unshift" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.unshift</h6>

```
//  向数组开头添加一个或多个元素，并返回
var array = [1, 2, 3];
array.unshift(4, 5, 6);
console.log(array); // Array(6) [ 4, 5, 6, 1, 2, 3 ]
```

<br>
<br>

<h6 id="Array.prototype.reverse" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.reverse</h6>

```
//  颠倒数组中元素的顺序
var array = [1, 2, 3];
array.reverse(4, 5, 6);
console.log(array); // Array(3) [ 3, 2, 1 ]
```

<br>
<br>

<h6 id="Array.prototype.sort" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.sort</h6>

```
//  对数组的元素进行排序
var array = [10, 5, 40, 25, 1000, 1];
array.sort();
console.log(array); // Array(6) [ 1, 1000, 25, 40, 5, 10 ]
```
（创建、显示及排列数组）（对非ASCII字符排序）（使用映射改善排序）
<br>
<br>

<h6 id="Array.prototype.concat" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.concat</h6>

```
//  用于连接两个或多个数组
var array = [1, 2, 3];
var array2 = [4, 5];
var array3 = [6, 7];

console.log(array2.concat(array, array3)); Array(7) [ 4, 5, 1, 2, 3, 6, 7 ]
```

<br>
<br>

<h6 id="Array.prototype.splice" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.splice</h6>

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

<h6 id="Array.prototype.slice" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.slice</h6>

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


<h6 id="Array.prototype.copyWithin" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.copyWithin</h6>

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


<h6 id="Array.prototype.entries" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.entries</h6>

```
//  回一个新的Array Iterator对象，该对象包含数组中每个索引的键/值对。
var array1 = ['a', 'b', 'c'];

var iterator1 = array1.entries();

console.log(iterator1.next().value);
// expected output: Array [0, "a"]
```
<br>
<br>


<h6 id="Array.prototype.every" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.every</h6>

```
//  测试数组所有元素是否能通过某个函数的测试
var array = [2, 3, 4];

console.log(array.every(function (value) {
	return value > 1;
}))  
// true
```
<br>
<br>

<h6 id="Array.prototype.fill" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.fill</h6>

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


<h6 id="Array.prototype.find" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.find</h6>

```
// 返回数组中通过测试函数的第一个元素的值
var array = [5, 12, 8, 130, 44];

console.log(array.find(function (element) {
	return element > 10
}))
//	12
（用对象的属性查找数值里的对象）（寻找数组中的质数）
```
<br>
<br>


<h6 id="Array.prototype.findIndex" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.findIndex</h6>

```
//  返回数组中通过测试函数的第一个元素的索引
var array = [5, 12, 8, 130, 44];

console.log(array.findIndex(function (element) {
	return element > 10
}))
//	1
（寻找数组中首个质数元素的索引）
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

<h6 id="Array.prototype.flatMap" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.flatMap</h6>

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
（归纳（reduce）与合并（concat））
```
<br>
<br>

<h6 id="Array.prototype.forEach" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.forEach</h6>

```
//  循环
var array1 = ['a', 'b', 'c'];

array1.forEach(function(element) {
  console.log(element);
});
（对象复制函数）
```
<br>
<br>


<h6 id="Array.prototype.includes" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.includes</h6>

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
（fromIndex大于等于数组长度）（计算出的索引小于0）（作为通用方法的 includes()）
```
<br>
<br>

<h6 id="Array.prototype.indexOf" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.indexOf</h6>

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
（找出指定元素出现的所有位置）（判断一个元素是否在数组里，不在则更新数组）
```
<br>
<br>


<h6 id="Array.prototype.keys" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.keys</h6>

```
//  返回一个包含数组中每个索引键的 Array Iterator 对象
var array1 = ['a', 'b', 'c'];
var iterator = array1.keys(); 
  
for (let key of iterator) {
  console.log(key); // expected output: 0 1 2
}
（索引迭代器会包含哪些没有对应元素的索引）
```
<br>
<br>


<h6 id="Array.prototype.lastIndexOf" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.lastIndexOf</h6>

```
//  返回指定元素在数组中最后一个索引
var animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];

console.log(animals.lastIndexOf('Dodo'));
// expected output: 3

console.log(animals.lastIndexOf('Tiger'));
// expected output: 1
（查找所有元素）
```
<br>
<br>


<h6 id="Array.prototype.map" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.map</h6>

```
//  创建一个新数组，每个元素调用函数后，返回结果
var array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
（求数组中每个元素的平方根）（使用map重新格式化数组中的对象）
（使用一个包含一个参数的函数来mapping（构建）一个数组数组）
（一般的map方法）（querySelectorAll 应用）（使用技巧案例）
```
<br>
<br>


<h6 id="Array.prototype.reduce" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.reduce</h6>

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
（数组中所有值的和）（累加对象数组里的值）（将二位数组转化为一维）（计算数组中每个元素出现的次数）（按属性对object分类）
（使用扩展运算符和initialValue绑定包含在对象数组中的数组）（数组去重）（按顺序运行Promise）（功能型函数管道）
```
<br>
<br>


<h6 id="Array.prototype.reduceRight" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.reduceRight</h6>

```
//  接受一个函数作为累加器和数组每个值（从右到左）减少为单值
const array1 = [[0, 1], [2, 3], [4, 5]].reduceRight(
  (accumulator, currentValue) => accumulator.concat(currentValue)
);

console.log(array1);
// expected output: Array [4, 5, 2, 3, 0, 1]
（求数组所有值的和）（扁平化一个元素为数组的数组）（reduce 与 reduceRight 之间的区别）
```
<br>
<br>


<h6 id="Array.prototype..some" style="background:#676767;color:#fff;padding: 10px;">Array.prototype..some</h6>

```
//  是否至少一个元素通过函数的测试
var array = [1, 2, 3, 4, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true
（使用箭头函数测试数组中的元素）（判断数组元素中是否存在某个值）（使用箭头函数判断数组元素中是否存在某个值）（将任意值转换成布尔值）
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


<h6 id="Array.prototype.filter" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.filter</h6>

```
//  创建新数组，包含通过提供函数测试的所有元素
function isBigEnough(element) {
  return element >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered is [12, 130, 44]
（筛选提出所有较小的值）（过滤 JSON 中无效条目）（在数组中搜索）
```
<br>
<br>


<h6 id="Array.prototype.flat" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.flat</h6>

```
//  按照指定深度递归遍历数组，并将所有元素与遍历的子元素中的元素合并为一个新数组返回
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

（扁平化嵌套数组）（扁平化与空项）
```
<br>
<br>



<h6 id="Array.prototype.values" style="background:#676767;color:#fff;padding: 10px;">Array.prototype.values</h6>

```
//  返回一个新的 Array Iterator 对象，该对象包含数组每个索引的值
const array1 = ['a', 'b', 'c'];
const iterator = array1.values();

for (const value of iterator) {
  console.log(value); // expected output: "a" "b" "c"
}
（另一种迭代方式）
```
<br>
