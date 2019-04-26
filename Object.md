- [Object.assign()](#Object.assign)
- [Object.create()](#Object.create)
- [Object.defineProperty()](#Object.defineProperty)
- [Object.defineProperties()](#Object.defineProperties)


<br/>
<br/>
<br/>
<br/>
<br/>


<a id="Object.assign">Object.assign</a>

```
将所有可枚举属性的值从一个或多个源对象复制到目标对象。
如果目标对象中的属性具有相同的键，则属性将被源对象中的属性覆盖。后面的源对象的属性将类似地覆盖前面的源对象的属性。
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
创建一个新对象，带有指定的原型对象和属性。
```
<br/>
<br/>


<a id="Object.defineProperty">Object.defineProperty</a>
```
直接在一个对象上定义新的属性或修改现有属性，并返回该对象。
该方创建一个新的属性，如果不指定。configurable、enumerable、writable 默认值都是 false
configurable	是否可删除		(不可修改)
enumerable		for-in 循环
writable		是否可修改
value			
get
set
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
方法直接在一个对象上定义一个或多个新的属性或修改现有属性，并返回该对象。
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
