## 条件分支 if和？

布尔转换

- 数字 `0`、空字符串 `""`、`null`、`undefined` 和 `NaN` 都会被转换成 `false`。因为他们被称为 “falsy” 值。
- 其他值被转换为 `true`，所以它们被称为 “truthy”。

else和else if

条件运算符 ？三元运算符

```javascript
let result = condition ? value1:value2
// 判断条件为真，返回value1，否则返回value2
```

## 逻辑运算符

或|| 与&& 非！



|| 或

或运算寻找第一个真值

```javascript
result = value1||value2||value3
// 从左到右依次计算操作数，遇到真值就返回，如果都是false则返回最后一个值
```

 **短路求值** 

```javascript
true || alert('不会打印')
false || alert('会打印')
// 因为或运算符遇到真值就返回，所以第一行直接返回了，短路效果
```

&& 与

与寻找第一个假值

```javascript
result = value1&&value2&&value3
// 从左至右计算操作数，遇到假值就返回，如果都是true则返回最后一个值
```

```javascript
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```

&&优先级高于||

！非

取相反布尔值

两个非运算将某个值转换为布尔类型

```javascript
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```

内置的Boolean函数可以转换数据为布尔类型

！非运算符的优先级高于与和非，所以它总是在&&和||之前执行

