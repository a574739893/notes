- [JSON.stringify()](#JSON.stringify)
- [JSON.parse()](#JSON.stringify)




# JSON.stringify
```
JSON.stringify() 方法是将一个JavaScript值(对象或者数组)转换为一个 JSON字符串

JSON.stringify({});                        // '{}'
JSON.stringify(true);                      // 'true'
JSON.stringify("foo");                     // '"foo"'
JSON.stringify([1, "false", false]);       // '[1,"false",false]'
JSON.stringify({ x: 5 });                  // '{"x":5}'

JSON.stringify({x: 5, y: 6});              
// "{"x":5,"y":6}"
```

# JSON.parse
```
JSON.parse() 方法用来解析JSON字符串，构造由字符串描述的JavaScript值或对象。

```
