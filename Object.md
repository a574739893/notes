- [Object.assign()](#Object.assign)
- [Object.create()](#Object.create)
- [Object.defineProperty()](#Object.defineProperty)
- [Object.defineProperties()](#Object.defineProperties)
- [Object.entries()](#Object.entries)
- [Object.freeze()](#Object.freeze)
- [Object.isFrozen()](#Object.isFrozen)
- [Object.preventExtensions()](#Object.preventExtensions)
- [Object.isExtensible()](#Object.isExtensible)
- [Object.seal()](#Object.seal)
- [Object.isSealed()](#Object.isSealed)



<a id="Object.aaaa">Object.aaaa</a>
```
// 

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

// Deep Clone 
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
var o;

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
```
<br/>
<br/>


<a id="Object.defineProperty">Object.defineProperty</a>
```
// 直接在一个对象上定义新的属性或修改现有属性，并返回该对象。
// 该方创建一个新的属性，如果不指定。configurable、enumerable、writable 默认值都是 false
// configurable	是否可删除		(不可修改)
// enumerable		for-in 循环
// writable		是否可修改
// value			
// get
// set
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
const obj = { foo: 'bar', baz: 42 };
console.log(Object.entries(obj)); // [ ['foo', 'bar'], ['baz', 42] ]

// array like object
const obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.entries(obj)); // [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]

// array like object with random key ordering
const anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.entries(anObj)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a'] ]

// getFoo is property which isn't enumerable
const myObj = Object.create({}, { getFoo: { value() { return this.foo; } } });
myObj.foo = 'bar';
console.log(Object.entries(myObj)); // [ ['foo', 'bar'] ]

// non-object argument will be coerced to an object
console.log(Object.entries('foo')); // [ ['0', 'f'], ['1', 'o'], ['2', 'o'] ]

// iterate through key-value gracefully
const obj = { a: 5, b: 7, c: 9 };
for (const [key, value] of Object.entries(obj)) {
  console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
}

// Or, using array extras
Object.entries(obj).forEach(([key, value]) => {
console.log(`${key} ${value}`); // "a 5", "b 7", "c 9"
});

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
```
