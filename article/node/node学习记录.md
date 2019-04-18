## 模块 export和import
```javascript
// export
'use strict';

let s = 'hello'
let s1 = 'GoodBye'


module.exports = {
    greet: function greet(name) {
        console.log(s + ',' + name + '!')
    },
    goodBye: function goodBye(name) {
        console.log(s1 + ',' + name + '!')
    }
}
```
```javascript
// import
'use strict';
// 引入hello模块:
// import { greet, GoodBye } from './module/hello'
// 需要引入整个export的对象，使用其方法和变量,继承时不加括号
// 如果要输出一个键值对象{}，可以利用exports这个已存在的空对象{}，并继续在上面添加新的键值；
//
// 如果要输出一个函数或数组，必须直接对module.exports对象赋值。
//
// 所以我们可以得出结论：直接对module.exports赋值，可以应对任何情况：


let greet1 = require('./module/hello').greet
// 或者
// let greet1 = require('./module/hello')
// 错误写法
// let greet1 = require('./module/hello').greet()

console.log('this is a node program!')

let name = 'Lemony'

greet1(name)
```

## 基本模块
1. global 全局对象，在浏览器中为window
2. process Node的进程对象（下一次事件响应中执行代码，可以调用process.nextTick()） 
```javascript
// process.nextTick()将在下一轮事件循环中调用:
process.nextTick(function () {
    console.log('nextTick callback!');
});
console.log('nextTick was set!');
```

## fs
参考src/module/module.js

## 流 stream
参考src/module/module.js

## HTTP 
参考src/module/http-module.js




