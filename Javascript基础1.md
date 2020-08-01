## 基础运算符，数学

术语：一元运算符、二元运算符、运算元

一元运算符：负号取反

二元运算符：负号做减法

%取余 **求幂  `a* ***b` 表示a的b次方

在计算时，字符串会进行自动转换

一元运算符先于二元运算符作用

++a 和 a++

++a的返回值加一，a++返回值不变

不管是++a还是a++   a的值都会加1



减号会把字符转成数字计算  减法只能用于数字，它会使空字符串转换为0

加号会把数字转成字符拼接

## 值的比较

比较结果为Boolean  true或者false

不同类型间的比较，字符串会被转化为数字

alert('2'>1)   //true

```javascript
let a=0
alert(Boolean(a))  //false
let b='0'
alert(Boolean(b))  //true  数字0看做false没有东西，字符串看做有值存在
```

严格相等

==普通的相等性检查   在进行比较时会做类型转换

===严格相等运算符   在进行比较时不会做类型转换

当使用数学式或其他比较方法< > <= >=时， `null/undefined` 会被转化为数字：`null` 被转化为 `0`，`undefined` 被转化为 `NaN`。 

```javascript
alert( null >= 0 ); // (3) true
```

undefined不应该被与其他值进行比较

null只与undefined相等

null == undefined









