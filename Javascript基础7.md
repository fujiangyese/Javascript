## Rest参数和Spread语法
...rest 用来接收多个参数，返回数组形式

Spread语法

```javascript
let arr = [3, 5, 1];

alert( Math.max(...arr) ); // 5（spread 语法把数组转换为参数列表）
```
同时可以使用spread语句来合并数组
```javascript
let arr = [1,2,3]
let arr2 = [4,5,6]
let merged = [...arr,...arr2]
```
同时也可以使用spread将字符串转换为字符数组
Array.from 适用于类数组对象也适用于可迭代对象。
Spread 语法只适用于可迭代对象。

使用spread来复制数组和对象的副本
```javascript
let arr = [1,2,3]
let arrCopy = [...arr]  //将数组元素解包，然后添加到另一个数组中
let obj = {a:1,b:2}
let objCopy = {...obj}
```
这种方式比使用 let arrCopy = Object.assign([], arr); 来复制数组，或使用 let objCopy = Object.assign({}, obj); 来复制对象写起来要短得多。

## 闭包

代码块
{...} 代码块内部的变量只在该代码块内是可见的
不能在同一个代码块中对同一个变量使用let重复声明

## 旧时的var

let、var、const
var只有函数作用域和全局作用域
let有块级作用域
变量提升
var声明变量提升至函数顶部
声明会被提升，但是赋值不会，所以在变量被赋值之前使用，变量的值为undefined

## 全局对象
全局对象提供可在任何地方使用的变量和函数。
在浏览器中，它的名字是window，对node.js而言，它的名字是global
globalThis 被作为全局对象的标准名称加入到了 JavaScript 中

## 函数对象，NFE
属性"name"
function.name  返回函数的名字
属性"length"
function.length  返回函数的入参个数
为函数对象内部属性添加函数方法
```javascript
function makeCounter() {
  let count = 0;

  function counter() {
    return count++;
  }

  counter.set = value => count = value;

  counter.decrease = () => count--;

  return counter;
}
```


