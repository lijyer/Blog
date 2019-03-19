一.JS对象与属性

1.JavaScript 对象
 对象是一种复合值：将很多值复合在一起（包括原始类型值、对象、函数）
 对象是若干无序属性的集合，可以直接通过属性名来访问对象的属性（键值对）
 函数作为某一个对象的属性时，称其为该对象的方法

2.对象的重要性
 一切数据都是通过变量（标识符）保存
 对象将相应的数据封装在一起统一管理

3.属性的重要性
 操作数据就是操作对象的属性

4.对象分类
 内置对象（native object）
由 ECMAScript 规范定义的对象或构造器对象（数组、函数等）
 宿主对象（host object）
由 JavaScript 解析器所嵌入的宿主环境定义的（如：window、document）
 自定义对象（user-defined object）
运行中的用户自定义JS代码创建的对象

5.属性的种类
 数据属性（Property）
 对象中的普通属性，从字符串的键到值的映射，是最常见的属性类型。
 访问器属性（Accessor）
类似于读、写属性的特殊方法，访问器可以计算属性的值。
 内置属性（Internal  property）
只存在于ECMAScript语言规范中，不能直接访问，有可能存在间接访问方式。规范将内置属性的键置于方括号中。比如[[Scope]]、[[Prototype]]
__proto__可以访问[[Prototype]]

6.对象和属性操作

 定义对象
 定义属性
 访问属性
 添加属性
 修改属性
 删除属性
 遍历属性

7.属性访问方式
 对象名.属性名
 对象名["属性名"]

8.（.）点操作符
 属性的键必须是标识符

9.（[]）中括号操作符
 通过表达式计算并强制转换为字符串类型的键访问属性

二.数据属性

1.数据属性的特性
 value（属性的值）：对应属性的值
 writable（可写特性）	：确定属性是否可改写性
 configurable（可配置特性）：确定属性是否能删除和其他特性是否可配置
 enumerable（可枚举特性）：属性是否可枚举

2.属性描述符（property descriptor）
 属性特性描述符是一个用来查看对象属性的特性的对象，该对象包含4个属性，对应4个特性
 封装了属性特性的对象，方便实现数据属性特性的设置和查询

3.Object.defineProperty(obj, prop, descriptor)
obj —— 要在其上定义属性的对象。
prop —— 要定义或修改的属性的名称。
descriptor —— 将被定义或修改的属性描述符

4.Object.getOwnPropertyDescriptor(obj,prop) 方法
 返回指定对象上一个自有属性对应的属性描述符。
 obj —— 需要查找的目标对象
 prop —— 目标对象内属性名称

5.Object.getOwnPropertyDescriptors(obj) 
 获取一个对象的所有自身属性的描述符

6.enumerable：枚举性
 一般来说，系统创建的属性不可枚举，而用户创建的属性可枚举。
通常不应该给内置原型和对象添加属性和方法。如果需要添加，应该设置属性不可枚举，避免破坏现有代码
 枚举的主要目的是判断 for-in 循环中的那些属性应该被忽略。

7.枚举性影响的操作
 for-in 循环
 Object.keys()
 JSON.stringify()

8.obj.propertyIsEnumerable(prop) 
返回一个布尔值，表示指定的属性是否可枚举。

9.configurable：可配置特性
 确定属性是否能删除和其他特性是否可配置

10.定义属性
如果属性不存在，会创建一个新的属性，它的特性由描述符指定，若果未指定，则使用默认值。

如果属性已经存在，会更新描述符指定的属性特性。但是描述符中的特性没有对应的特性，则特性不变。



三.访问器属性

 1.访问器属性的特性
 get：读取属性时调用的函数，该函数计算读取的结果，默认是 undefined
 set: 设置属性值时调用的函数，该函数接受设置的值作为参数，默认是undefined
 configurable（可配置特性）：确定属性是否能删除和其他特性是否可配置
 enumerable（可枚举特性）：属性是否可枚举

2.属性特性
 get   set
 value  writeable
 configurable
 enumerable

3.设置属性特性
 Object.defineProperty()   Object.defineProperties()

4.获取属性特性
 Object.getOwnPropertyDescriptor() Object.getOwnPropertyDescriptors()

5.设置属性的一些特性，设置权限，保护属性，比如 Math.PI。

6.访问器属性可用于对数据的一些计算，比如数据验证。

7.对属性的封装、判断、校验、默认值等操作。