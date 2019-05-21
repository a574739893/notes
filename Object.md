- 创建 
  - [Object.assign()](#Object.assign)
  - [Object.create()](#Object.create)

- 修改
  - [Object.defineProperty()](#Object.defineProperty)
  - [Object.defineProperties()](#Object.defineProperties)

- 转换
  - [Object.entries()](#Object.entries)
  - [Object.fromEntries()](#Object.fromEntries)

- 限制
  - [Object.freeze()](#Object.freeze)
  - [Object.preventExtensions()](#Object.preventExtensions)
  - [Object.seal()](#Object.seal)
  - [Object.isExtensible()](#Object.isExtensible)
  - [Object.isFrozen()](#Object.isFrozen)
  - [Object.isSealed()](#Object.isSealed)

- 检测
  - [Object.getOwnPropertyDescriptor()](#Object.getOwnPropertyDescriptor)
  - [Object.getOwnPropertyDescriptors()](#Object.getOwnPropertyDescriptors)
  - [Object.get​OwnProperty​Names()](#Object.get​OwnProperty​Names)
  - [Object.getOwnPropertySymbols()](#Object.getOwnPropertySymbols)
  - [Object.getPrototypeOf()](#Object.getPrototypeOf)
  - [Object.keys()](#Object.keys)
  - [Object.values()](#Object.values)
  - [Object.is()](#Object.is)

- prototype
  - [Object.prototype.hasOwnProperty()](#Object.prototype.hasOwnProperty)
  - [Object.prototype.isPrototypeOf()](#Object.prototype.isPrototypeOf)
  - [Object.prototype.propertyIsEnumerable()](#Object.prototype.propertyIsEnumerable())
  - [Object​.prototype​.toLocale​String()](#Object​.prototype​.toLocale​String)
  - [Object​.prototype​.toString()](#Object​.prototype​.toString)




```
// 创建新属性，如果不指定  configurable = enumerable = writable = false 

// 数据属性       访问器属性
// configurable   configurable      是否可删除   (不可修改)
// enumerable     enumerable        for-in 循环
// writable                         是否可修改
// value          
//                Get
//                Set
```


<br/>
<br/>
<br/>
<br/>
<br/>


<a id="Object.assign">Object.assign</a>

```
// 将所有可枚举属性的值从一个或多个源对象复制到目标对象。
// 如果目标对象中的属性具有相同的键，则属性将被源对象中的属性覆盖。后面的源对象的属性将类似地覆盖前面的源对象的属性。

let obj1 = { a: 0 , b: { c: 0}}; 
let obj2 = Object.assign({}, obj1); 
console.log(JSON.stringify(obj2)); // { a: 0, b: { c: 0}} 

obj1.a = 1; 
console.log(JSON.stringify(obj1)); // { a: 1, b: { c: 0}} 
console.log(JSON.stringify(obj2)); // { a: 0, b: { c: 0}} 

obj2.a = 2; 
console.log(JSON.stringify(obj1)); // { a: 1, b: { c: 0}} 
console.log(JSON.stringify(obj2)); // { a: 2, b: { c: 0}}
 
obj2.b.c = 3; 
console.log(JSON.stringify(obj1)); // { a: 1, b: { c: 3}} 
console.log(JSON.stringify(obj2)); // { a: 2, b: { c: 3}} 

// 深克隆
obj1 = { a: 0 , b: { c: 0}}; 
let obj3 = JSON.parse(JSON.stringify(obj1)); 
obj1.a = 4; 
obj1.b.c = 4; 
console.log(JSON.stringify(obj3)); // { a: 0, b: { c: 0}}

```


<br/>
<br/>
<a id="Object.create">Object.create</a>


```
// 创建一个新对象，带有指定的原型对象和属性。
// 参数二，添加到新创建对象的可枚举属性(即自身定义的属性，不是原型链上的)
var o;

// 创建一个原型为null的空对象
o = Object.create(null);


o = {};
// 以字面量方式创建的空对象就相当于:
o = Object.create(Object.prototype);


o = Object.create(Object.prototype, {
  // foo会成为所创建对象的数据属性
  foo: { 
    writable:true,
    configurable:true,
    value: "hello" 
  },
  // bar会成为所创建对象的访问器属性
  bar: {
    configurable: false,
    get: function() { return 10 },
    set: function(value) {
      console.log("Setting `o.bar` to", value);
    }
  }
});


function Constructor(){}
o = new Constructor();
// 上面的一句就相当于:
o = Object.create(Constructor.prototype);
// 当然,如果在Constructor函数中有一些初始化代码,Object.create不能执行那些代码


// 创建一个以另一个空对象为原型,且拥有一个属性p的对象
o = Object.create({}, { p: { value: 42 } })

// 省略了的属性特性默认为false,所以属性p是不可写,不可枚举,不可配置的:
o.p = 24
o.p
//42

o.q = 12
for (var prop in o) {
   console.log(prop)
}
//"q"

delete o.p
//false

//创建一个可写的,可枚举的,可配置的属性p
o2 = Object.create({}, {
  p: {
    value: 42, 
    writable: true,
    enumerable: true,
    configurable: true 
  } 
});
```
<br/>
<br/>


<a id="Object.defineProperty">Object.defineProperty</a>
```
// 直接在一个对象上定义新的属性或修改现有属性，并返回该对象。
// 该方创建一个新的属性，如果不指定。configurable、enumerable、writable 默认值都是 false

var obj = new Object();
Object.defineProperty(obj, 'name', {
    configurable: false,
    writable: true,
    enumerable: true,
    value: '张三'
})
```


<br/>
<br/>

<a id="Object.defineProperties">Object.defineProperties</a>

```
// 方法直接在一个对象上定义一个或多个新的属性或修改现有属性，并返回该对象。

var obj = new Object();
Object.defineProperties(obj, {
    name: {
        value: '张三',
        configurable: false,
        writable: true,
        enumerable: true
    },
    age: {
        value: 18,
        configurable: true
    }
})

console.log(obj.name, obj.age) // 张三, 18

```

<br/>
<br/>

<a id="Object.entries">Object.entries</a>

```
// 返回一个给定对象自身可枚举属性的键值对数组。
// 可返回不可枚举属性

const obj = { foo: 'bar', baz: 42 };
console.log(Object.entries(obj)); // [ ['foo', 'bar'], ['baz', 42] ]

// array like object
const obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.entries(obj)); // [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]

// 具有随机键排序的对象数组
const anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.entries(anObj)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a'] ]

// getFoo是不可枚举的属性
const myObj = Object.create({}, { getFoo: { value() { return this.foo; } } });
myObj.foo = 'bar';
console.log(Object.entries(myObj)); // [ ['foo', 'bar'] ]

// 非对象参数将被强制转换为对象
console.log(Object.entries('foo')); // [ ['0', 'f'], ['1', 'o'], ['2', 'o'] ]

// 优雅地遍历键值
const obj = { a: 5, b: 7, c: 9 };
for (const [key, value] of Object.entries(obj)) {
  console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
}

// 或者，使用数组附加功能
Object.entries(obj).forEach(([key, value]) => {
console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
});

```

<br/>
<br/>


<a id="Object.fromEntries">Object.fromEntries</a>
```
// 把键值对列表转换成一个对象

// Map 转化为 Object
const map = new Map([ ['foo', 'bar'], ['baz', 42] ]);
const obj = Object.fromEntries(map);
console.log(obj); // { foo: "bar", baz: 42 }

// Array 转化为 Object
const arr = [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ];
const obj = Object.fromEntries(arr);
console.log(obj); // { 0: "a", 1: "b", 2: "c" }

// 对象转换
const object1 = { a: 1, b: 2, c: 3 };

const object2 = Object.fromEntries(
  Object.entries(object1)
  .map(([ key, val ]) => [ key, val * 2 ])
);

console.log(object2);
// { a: 2, b: 4, c: 6 }
```

<br/>
<br/>

<a id="Object.freeze">Object.freeze</a>

```
// 冻结一个对象，被冻结的对象不能被修改；不能添加新属性、删除已有属性、修改已有属性
// 深冻结函数

obj1 = {
	internal: {}
}

function deepFreeze(obj) {
	var propNames = Object.getOwnPropertyNames(obj);
	propNames.forEach( (item) => {
		var prop = obj[item];

		if ( typeof prop == "object" && prop !== null ) {
			deepFreeze(prop);
		}
	})

	return Object.freeze(obj);
}

deepFreeze(obj1);

```

<br/>
<br/>


<a id="Object.isFrozen">Object.isFrozen</a>
```
// 判断一个对象是否被冻结。

```

<a id="Object.preventExtensions">Object.preventExtensions</a>
```
// 让一个对象不能再添加新的属性
// 返回一个不可扩展的对象

var obj = {};
var obj2 = Object.preventExtensions(obj);
obj === obj2;  // true
 
// 字面量方式定义的对象默认是可扩展的.
var empty = {};
Object.isExtensible(empty) //=== true

```


<a id="Object.isExtensible">Object.isExtensible</a>
```
// 判断一个对象是否可以添加新的属性

var empty = {};
Object.isExtensible(empty); // === true

// ...可以变的不可扩展.
Object.preventExtensions(empty);
Object.isExtensible(empty); // === false

// 密封对象是不可扩展的.
var sealed = Object.seal({});
Object.isExtensible(sealed); // === false
```


<a id="Object.seal">Object.seal</a>
```
// 阻止添加新属性，并将所有现有属性为不可配置。当前属性只有可写才可以改变

const object1 = {
  property1: 42
};

Object.seal(object1);
object1.property1 = 33;
console.log(object1.property1);
// expected output: 33

delete object1.property1; // 密封时无法删除
console.log(object1.property1);
// expected output: 33
```

<a id="Object.isSealed">Object.isSealed</a>
```
// 判断一个对象是否被密封

// 新建的对象默认不是密封的.
var empty = {};
Object.isSealed(empty); // === false

// 如果你把一个空对象变的不可扩展,则它同时也会变成个密封对象.
Object.preventExtensions(empty);
Object.isSealed(empty); // === true

// 但如果这个对象不是空对象,则它不会变成密封对象,因为密封对象的所有自身属性必须是不可配置的.
var hasProp = { fee: "fie foe fum" };
Object.preventExtensions(hasProp);
Object.isSealed(hasProp); // === false

// 如果把这个属性变的不可配置,则这个对象也就成了密封对象.
Object.defineProperty(hasProp, "fee", { configurable: false });
Object.isSealed(hasProp); // === true

// 最简单的方法来生成一个密封对象,当然是使用Object.seal.
var sealed = {};
Object.seal(sealed);
Object.isSealed(sealed); // === true

// 一个密封对象同时也是不可扩展的.
Object.isExtensible(sealed); // === false
```

<br/>
<br/>

<a id="Object.getOwnPropertyDescriptor">Object.getOwnPropertyDescriptor</a>
```
// 返回对象上一个自有属性对应的描述符 
// (自有属性是直接赋予该对象的属性，不需要从原型链上进行查找)

var o, d;

o = { get foo() { return 17; } };
d = Object.getOwnPropertyDescriptor(o, "foo");
// d {
//   configurable: true,
//   enumerable: true,
//   get: /*the getter function*/,
//   set: undefined
// }

o = { bar: 42 };
d = Object.getOwnPropertyDescriptor(o, "bar");
// d {
//   configurable: true,
//   enumerable: true,
//   value: 42,
//   writable: true
// }

o = {};
Object.defineProperty(o, "baz", {
  value: 8675309,
  writable: false,
  enumerable: false
});
d = Object.getOwnPropertyDescriptor(o, "baz");
// d {
//   value: 8675309,
//   writable: false,
//   enumerable: false,
//   configurable: false
// }
```

<br/>
<br/>

<a id="Object.getOwnPropertyDescriptors">Object.getOwnPropertyDescriptors</a>
```
// 获取一个对象所有的自身属性描述符

```

<br/>
<br/>


<a id="Object.getOwnPropertySymbols">Object.getOwnPropertySymbols</a>
```
// 返回一个对象自身所有 Symbol 属性的数组
var obj = {};
var a = Symbol("a");
var b = Symbol.for("b");

obj[a] = "localSymbol";
obj[b] = "globalSymbol";

var objectSymbols = Object.getOwnPropertySymbols(obj);

console.log(objectSymbols.length); // 2
console.log(objectSymbols)         // [Symbol(a), Symbol(b)]
console.log(objectSymbols[0])      // Symbol(a)
```

<br/>
<br/>

<a id="Object.keys">Object.keys</a>
```
// 返回其枚举自身属性的对象

var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr)); // console: ['0', '1', '2']


var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj)); // console: ['0', '1', '2']

// 具有随机键排序的对象数组
var anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.keys(anObj)); // console: ['2', '7', '100']

// getFoo is a property which isn't enumerable
var myObj = Object.create({}, {
  getFoo: {
    value: function () { return this.foo; }
  } 
});
myObj.foo = 1;
console.log(Object.keys(myObj)); // console: ['foo']
```
<br/>
<br/>

<a id="Object.values">Object.values</a>
```
// 返回一个数组，其元素是在对象上找到的可枚举属性值
var obj = { foo: 'bar', baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.values(obj)); // ['a', 'b', 'c']

// array like object with random key ordering
// when we use numeric keys, the value returned in a numerical order according to the keys
var an_obj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.values(an_obj)); // ['b', 'c', 'a']

// getFoo is property which isn't enumerable
var my_obj = Object.create({}, { getFoo: { value: function() { return this.foo; } } });
my_obj.foo = 'bar';
console.log(Object.values(my_obj)); // ['bar']

// non-object argument will be coerced to an object
console.log(Object.values('foo')); // ['f', 'o', 'o']

```
<br/>
<br/>

<a id="Object.prototype.hasOwnProperty">Object.prototype.hasOwnProperty</a>
```
// 用来检测一个对象是否含有特定的自身属性，该方法会忽略掉原型链继承的属性
var foo = {
    hasOwnProperty: function() {
        return false;
    },
    bar: 'Here be dragons'
};

foo.hasOwnProperty('bar'); // 始终返回 false

// 如果担心这种情况，可以直接使用原型链上真正的 hasOwnProperty 方法
({}).hasOwnProperty.call(foo, 'bar'); // true

// 也可以使用 Object 原型上的 hasOwnProperty 属性
Object.prototype.hasOwnProperty.call(foo, 'bar'); // true

```

<br/>
<br/>

<a id="Object.get​OwnProperty​Names">Object.get​OwnProperty​Names</a>
```
// 返回一个数组，由对象所有自身属性的属性名
var arr = ["a", "b", "c"];
console.log(Object.getOwnPropertyNames(arr).sort()); // ["0", "1", "2", "length"]

// 类数组对象
var obj = { 0: "a", 1: "b", 2: "c"};
console.log(Object.getOwnPropertyNames(obj).sort()); // ["0", "1", "2"]

// 使用Array.forEach输出属性名和属性值
Object.getOwnPropertyNames(obj).forEach(function(val, idx, array) {
  console.log(val + " -> " + obj[val]);
});
// 输出
// 0 -> a
// 1 -> b
// 2 -> c

//不可枚举属性
var my_obj = Object.create({}, {
  getFoo: {
    value: function() { return this.foo; },
    enumerable: false
  }
});
my_obj.foo = 1;

console.log(Object.getOwnPropertyNames(my_obj).sort()); // ["foo", "getFoo"]
```

<br/>
<br/>


<a id="Object.getPrototypeOf">Object.getPrototypeOf</a>
```
// 返回对象的原型
// 内部 [[ Prototype ]] 属性的值
var proto = {};
var obj = Object.create(proto);
Object.getPrototypeOf(obj) === proto; // true

var reg = /a/;
Object.getPrototypeOf(reg) === RegExp.prototype; // true
```

<br/>
<br/>

<a id="Object.is">Object.is</a>
```
// 判断两个值是否相同

    两个值都是 undefined
    两个值都是 null
    两个值都是 true 或者都是 false
    两个值是由相同个数的字符按照相同的顺序组成的字符串
    两个值指向同一个对象
    两个值都是数字并且
        都是正零 +0
        都是负零 -0
        都是 NaN
        都是除零和 NaN 外的其它同一个数字

//  == 运算符会做隐式类型转换，Object.is 不会
Object.is('foo', 'foo');     // true
Object.is(window, window);   // true

Object.is('foo', 'bar');     // false
Object.is([], []);           // false

var foo = { a: 1 };
var bar = { a: 1 };
Object.is(foo, foo);         // true
Object.is(foo, bar);         // false

Object.is(null, null);       // true

// 特例
Object.is(0, -0);            // false
Object.is(0, +0);            // true
Object.is(-0, -0);           // true
Object.is(NaN, 0/0);         // true
```


<a id="Object​.prototype​.isPrototypeOf">Object​.prototype​.isPrototypeOf</a>
```
  // 测试一个对象是否存在于另一个对象的原型链上
function Foo() {}
function Bar() {}
function Baz() {}

Bar.prototype = Object.create(Foo.prototype);
Baz.prototype = Object.create(Bar.prototype);

var baz = new Baz();

console.log(Baz.prototype.isPrototypeOf(baz)); // true
console.log(Bar.prototype.isPrototypeOf(baz)); // true
console.log(Foo.prototype.isPrototypeOf(baz)); // true
console.log(Object.prototype.isPrototypeOf(baz)); // true
```

<br/>
<br/>


<a id="Object.prototype​.propertyIsEnumerable">Object.prototype​.propertyIsEnumerable</a>
```
// 返回一个布尔值，表示指定属性是否可枚举
var o = {};
var a = [];
o.prop = 'is enumerable';
a[0] = 'is enumerable';

o.propertyIsEnumerable('prop');   //  返回 true
a.propertyIsEnumerable(0);        // 返回 true
```

<br/>
<br/>

<a id="Object.prototype​.toLocale​String">Object.prototype​.toLocale​String</a>

```
// 返回调用 toString() 的结果

```

<br/>
<br/>


<a id="Object.prototype​.toString">Object.prototype​.toString</a>

```
// 返回表示该对象的字符串

```