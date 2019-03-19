一.this

   1.this 关键字是 JavaScript 中最复杂的机制之一。this 被自动定义在所有函数的作用域中。

2. this 特点
    函数的调用方式决定了 this 的值，运行期间绑定
    每次函数被调用时 this 的值也可能会不同
    this 不能被赋值
    this 不进行作用域传递

二.this绑定规则

​    1.绑定规则
​        默认绑定
​        隐式绑定
​        显示绑定
​        new绑定

2.  独立函数调用。可以把这条规则看作是无法应用其他规则时的默认规则。

    使用非严格模式，this 会绑定到全局对象 window 上。
    使用严格模式， this 会绑定到 undefined。

3. 函数嵌套时，需注意 this 不进行作用域传递。

4. 函数嵌套时，this 绑定
    变量 _this、that、self  锁定  this
    bind() 锁定

5. 调用位置是否有上下文对象。
    函数作为对象的方法调用时，函数上下文指向这个对象。

    数组中存放函数，被数组索引调用。this上下文指向这个数组。

6. 对象属性引用链中只有最顶层或者说最后一层会影响调用位置。

7. 使用 call()、apply()、bind() 方法显示改变 this 的指向为指定对象。

8. new 来调用函数，或者说发生构造函数调用时，会自动执行下面的操作。
    创建（或者说构造）一个全新的对象。
    这个新对象会被执行 [[ 原型 ]] 连接。
    这个新对象会绑定到函数调用的 this。
    如果函数没有返回其他对象，那么 new 表达式中的函数调用会自动返回 this (新对象)。

9. new 绑定 > 显式绑定 > 隐式绑定 > 默认绑定

10. 判断 this 的顺序
     函数是否在 new 中调用？如果是的话 this 绑定的是新创建的对象。
     函数是否通过 call、apply、bind调用？如果是的话 this 绑定的是指定的对象。
     函数是否在某个上下文对象中调用（隐式绑定）？如果是的话，this 绑定的是那个上下文对象。
     如果都不是的话，使用默认绑定。如果在严格模式下，就绑定到 undefined，否则绑定到全局对象。

    