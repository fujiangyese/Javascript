## 原型继承
我们有一个 user 对象及其属性和方法，并希望将 admin 和 guest 作为基于 user 稍加修改的变体。我们想重用 user 中的内容，而不是复制/重新实现它的方法，而只是在其至上构建一个新的对象。
原型继承这个语言特性可以帮我们实现这一需求

```javascript
let animal = {
    eats:true
}
let rabbit = {
    jumps:true
}
rabbit.__proto__ = animal  //使rabbit继承animal中的属性
// 现在rabbit也具有eats属性了
console.log(rabbit.eats)  //true
```
作为一种常见的解决方案，所有描述特定对象状态的属性，都应该被写入该对象中。

## Class基本语法

```javascript
class MyClass {
    constructor(){}
    method1(){}
    method2(){}
}
// constructor方法在实例化的时候会自己调用执行，因此可以在constructor中初始化对象属性
```

```javascript
class User {
    constructor(name){
        this.name = name
    }
    sayHi(){
        alert(this.name)
    }
}
let user = new User('名字') //输入一个名字传递给constructor构造函数初始化
user.sayHi()
```
### 类的方法之间没有逗号，在类中不需要逗号
在Javascript中，类是一种函数
alert(typeof User) // function

1. 类必须通过new来调用实例化对象
2. 类方法不可枚举
3. 类中总是使用 use strict 在类中的代码都将自动进入严格模式

类表达式
就像函数一样，类可以在另外一个表达式中被定义，被传递，被返回，被赋值
```javascript
let User = class {
    sayHi(){
        alert("Hello")
    }
}
```
类表达式如果有名字，则该名字只在类内部可见 let User = class MyClass {}  MyClass类名仅在类中可见

按需创建类
```javascript
function makeClass(phrase) {
  // 声明一个类并返回它
  return class {
    sayHi() {
      alert(phrase);
    };
  };
}

// 创建一个新的类
let User = makeClass("Hello");

new User().sayHi(); // Hello
```
makeClass根据传入的参数返回一个类表达式，可以直接调用这个类对象中的方法

getters/setters
类里面可能包括getters/setters

这里使用get/set实现user.name的示例
```javascript
class User {
    constructor(name){
        this.name = name
    }
    get name(){
        return this._name
    }
    set name(value){
        if (value.length<4>){
            alert('Name is too short')
            return
        }
        this._name = value
    }
}
let user = new User("John")
alert(user.name)
user = new User("")  // Name is too short
```
分别使用到set和get函数来设置和获取name属性  和python中的语法有点像

>Class字段
类字段是一种允许添加任何属性的语法
我们可以直接在类中添加一个变量属性
```javascript
class User {
    name = "John"
    sayHi(){
        alert(`Hello ${this.name}`)
    }
}
new User().sayHi() // Hello John   类中直接添加的属性要通过类名直接访问
let user = new User()
alert(user.name)  // John
```
>使用类字段制作绑定方法
如果一个对象被传递到某处，或者在另一个上下文，则this将不再是对其对象的引用
```javascript
class Button {
  constructor(value) {
    this.value = value;
  }

  click() {
    alert(this.value);
  }
}

let button = new Button("hello");

setTimeout(button.click, 1000); // undefined
```
这种情况被称为丢失this，解决方法有两种
1. 传递一个包装函数，例如 setTimeout(()=>button.click(),1000)
2. 将方法绑定到对象，例如在constructor中

类字段提供了另一种非常优雅的语法
```javascript
class Button {
    constructor(value){
        this.value = value
    }
    click = ()=>{
        alert(this.value)
    }
}
let button = new Button("hello")
setTimeout(button.click,1000)  //这里就是将方法click方法绑定到了click字段上
```

## 类继承

>extends关键字
class Rabbit extends Animal
>重写方法
在当前类下写上相同函数名方法，实现重写
但是通常情况下，我们希望在父类的基础之上进行调整或者扩展功能。我们在我们的方法中做一些事儿，但是在它之前之后或在过程中调用父类的方法
CLass为此提供了super关键字
- super.method() 来调用一个父类的方法
- super(类名) 来调用一个父类的constructor构造函数（注意只能在当前类的constructor函数中使用）

>总结
1. 想要扩展一个类：class Child extends Parent：
这意味着 Child.prototype.__proto__ 将是 Parent.prototype，所以方法会被继承。
2. 重写一个 constructor：
在使用 this 之前，我们必须在 Child 的 constructor 中将父 constructor 调用为 super()。
3. 重写一个方法：
我们可以在一个 Child 方法中使用 super.method() 来调用 Parent 方法。

箭头函数没有自己的 this 或 super，所以它们能融入到就近的上下文中，像透明似的。
子类的constructor必须调用super()先对父类进行初始化