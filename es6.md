- [Symbol](#Symbol)



<a id="Symbol">Symbol</a>
```
// 新的数据类型
// 不能使用 new
// 在所有使用可计算属性名的地方，都能使用 Symbol

Symbol.for() 首先在全局搜索有没有改参数名称的 Symbol 值，如果有，就返回这个 Symbol 的值，否则就新建并返回一个该名称的 Symbol 的值

Symbol.keyFor方法检测该Symbol是否已创建
```

<br/>
<br/>


#### Set、Map
作用：
	如果需要使用非数组性索引，就会用非数组对象创建所需的数据结构

Set 常被用来检查对象中是否存在某个键名
Map 集合常被用来获取已存的信息


