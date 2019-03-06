# 1.js基础
## 1.1	 6种数据类型 
* number 
* string  
* null  
* undefined  
* object  
* Boolean
## 1.2	 类型检测
* typeof instanceof prototype.toString constructor
## 1.3	原型链 
* 原型链，类似于面向对象中的基类与子类的关系
* 使用in查找属性会查找至末端原型链，所以只查找当前对象的属性应当使用hasOwnProperty，
* Object.create 使用现有的对象作为原型作为新创建对象的_proto_
* 对象上的propertyIsEnumerable是否可枚举属性决定是否可通过for...in循环枚举，但是hasOwnProperty可以查找到，就是可以先for…in查找对象的全部属性，再使用hasOwnProperty作为条件过滤当前原型的属性
* Object.defineProperty()可以定义对象的属性
* Get set 方法，可以用来做对象的安全性处理，使用getOwnPropertyDescriptor方法获取属性描述
* 对象标签：分三种，_proto_, class(getType方法), extensible(isExtensible方法)
* 对象序列化： JSON.stringify,将对象变为字符串，但是undefined无法序列化，JSON.parse将字符串变为对象
## 1.4	数组 
### 1.4.1.循环
* 	普通for循环和for…in区别是for循环只查找原型上的元素并且是顺序查找，for…in无序并且会查找到原型链上的属性
### 1.4.2.	稀疏数组
 * 就是数组长度大于实际元素个数
### 1.4.3.	数组方法：
* 1．数组也有Array.prototype,也在原型链上提供了多的方法
* 2．Join方法 数组转为字符串.
* 3．Reverse方法 数组倒排，改变原数组
* 4．Sort方法 数组排序 针对英文字母排序，如果要针对数字的话，需要传入一个排序函数，升序则需要传入一个负数，降序传入一个正数，同时也改变了原函数 
* 5．Concat方法 数组合并，一维数组合并传入一维数组还是一维数组，传入二维数组无法将第二个子数组变为一维数组
* 6．Slice方法 数组切割，负数索引从尾部开始，-1就是最后一位元素
* 7．Splice方法 数组拼接 可以减少也可以增加数组元素
* 8．Map方法 数组映射array.map(function(x){ Return x+10 }) 不改变原数组
* 9．Filter方法	数组筛选 不改变元素组
* 10．Every&some方法 数组判断全部和部分的区别
* 11．Reduce·& reduceright reduce是数组中相邻两个元素做操作
#### 1.5	函数
1.	函数声明 以function XX（）{}
2.	函数表达式 var xx=function() {}; 
(function(){})() ; 立即执行
return function() {}
3.	函数构造器 var xx= Function(‘X’, ‘X’, ’XXXXX’)
4.	函数声明会被前置 函数放在上下文任意地方都可以
5.	函数中没有使用return时，返回值为this的内容，如果使用了return 则以return为主
6.	Call: 传入多个参数，apply传入一个参数为数组
7.	Arguments 函数实参，如果未传，则无法对arguments做操作
8.	函数科里化， 把函数拆成多个单元
9.	Bind bind()方法主要就是将函数绑定到某个对象，bind()会创建一个函数，函数体内的this对象的值会被绑定到传入bind()中的第一个参数的值，例如：f.bind(obj)，实际上可以理解为obj.f()，但是使用new时会忽略bind，返回this
## 1.6	闭包
    在函数lazy_sum中又定义了函数sum，
    
    并且，内部函数sum可以引用外部函数lazy_sum的参数和局部变量，
    
    当lazy_sum返回函数sum时，相关参数和变量都保存在返回的函数中，这种称为“闭包（Closure）”， 
    
    每次调用都会返回一个新的函数
    
    返回闭包时牢记的一点就是：返回函数不要引用任何循环变量，或者后续会发生变化的变量。

## 1.7	es3执行上下文

### 1.VO 变量对象 AO活动对象 

    变量对象VO是与执行上下文相关的特殊对象,
    
    用来存储上下文的函数声明，函数形参和变量。
    
    在global全局上下文中，变量对象也是全局对象自身，
    
    在函数上下文中，变量对象被表示为活动对象AO。

## 1.8	OOP  面向对象程序设计
    继承 XX.prototype.XX:在构造函数的prorotype上赋予新的属性值 
    
    使用 yy.prototype = Object.create(XX.prototype)
    
    yy. prototype.constructor = yy（保持一致性）
    
    这样就可以完成子类yy对父类XX的继承
    模拟重载：利用arguments获得实参个数和类型模拟函数重载



