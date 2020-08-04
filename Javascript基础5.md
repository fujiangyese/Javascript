## 对象Object
就是Python中的字典
{"键":"值"}
```javascript
// 构建对象
let user = new Object();  // 构造函数方法
let user = {};  // 字面量方法
```
对象里面的数据叫做属性，通过点号读取属性值
```javascript
let user = {'name':'老王',age:30}
alert(user.name)
alert(user['name'])
```
属性的键可以不加引号，读取值有两种方法，一种是直接使用点号调用属性，另一种是使用中括号，括号里用引号包裹键(同Python)
使用=对键赋值
使用delete关键字删除属性

const声明的对象内部是可以修改的
const只是固定了这个对象的内存地址，对象内部的属性值可以修改

属性值简写
在构造函数内部，返回的对象键和值名字相同，省略值
```javascript
function makeUser(name, age) {
  return {
    name: name,
    age: age,
    // ……其他的属性
  };
}

let user = makeUser("John", 30);
alert(user.name); // John
```
删除对象中的属性，使用delete关键字
delete user.name

属性存在性测试，in操作符
`"key" in object`
左边的属性名需要使用引号包裹，判断它是否在对象中

for ... in 循环
遍历对象中所有的键
```javascript
for (key in object){
    // 具体操作
}
```

## 对象的拷贝引用
使用assign函数合并多个对象
```javascript
let a = {name:'大象'}
let b = {age:18}
Object.assign(dest, [src1, src2, src3...])
// 将所有属性都拷贝到user上  拷贝之后原属性会被覆盖
Object.assign(user,a,b)
// 拷贝原属性到新对象中并返回
let clone = Object.assign({}, user);
```

## 垃圾回收

## 对象方法，this
```javascript
let user = {
    sayHi(){
        alert("Hello")
    }
}
let user = {
    sayHi:function(){
        alert('Hello')
    }
}
// 两种定义方法效果相同
```
方法中的this
this的值就是在点之前的这个对象，即调用该方法的对象

```javascript
let user = {
    name:"John",
    age:30,
    sayHi(){
        // this指的是当前的user对象
        alert(this.name)
    }
}
```
this不受限制，可以用于任何函数
在没有对象的情况下调用this，this的值为undefined

箭头函数没有自己的this
箭头函数从外部的上下文获取this
```javascript
let user = {
    firstName = "Ilya",
    sayHi(){
        let arrow = () => alert(this.firstName);
        arrow();
    }
}
user.sayHi();
```

## 构造器和操作符 new

构造函数：与常规函数相同，但是命名以大写字母开始，只能由new操作符执行
```javascript
function User(name){
    this.name = name
    this.isAdmin = false
}
let user = new User('Jack')
alert(user.name)
alert(user.isAdmin)
```

## 构造器模式测试
在一个函数内部可以使用new.target属性来检查它是否被new调用，常规调用它为空，new调用等于该函数
```javascript
function User(name){
    if (!new.target){
        return new User(name)
    }
    this.name = name
}
```
 ## 可选链 ?.
 可选链是一种访问嵌套对象属性的放错误的方法。即使中间的属性不存在，也不会出现错误
 `user?.address?.street`
 ?.使其前面的值成为可选值，但不会对其后面的起作用
 ?. 检查左边部分是否为 null/undefined，如果不是则继续运算。

 ## Symbol 类型
 对象的属性键只能是字符串类型或者Symbol类型。
 Symbol的值表示唯一的标识符
 可以使用Symbol()函数来创建这种类型的值
 `let id = Symbol('id');  括号里面可以给它一个描述`
 Symbol不会被自动转换为字符串，可以使用toString()函数强制实现转换

## 对象——原始值转换
对象到数字转换
1. 显示转换 Number函数
`let num = Number(obj)`
2. 数学运算和比较
`let n = +obj`

valueOf toString





