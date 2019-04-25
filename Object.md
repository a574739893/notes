# Object.assign
```
Object.assign(target, source)
将所有可枚举属性的值，从一个或多个源对象复制到目标对象，它将返回目标对象
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

const returnedTarget = Object.assign(target, source);
console.log(target);
//  expected output: Object { a: 1, b: 4, c: 5 };
console.log(target === returnedTarget);
//  true
```




# Object.getOwnPropertySymbols
```
Object.getOwnPropertySymbols(obj)
参数
  obj 要返回Symbol 属性的对象
返回值
  在给定对自身上找到所有的 Symbol 属性的数组
```
