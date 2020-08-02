## 循环while和for

do while循环，使用较少
```javascript
do {
    // 循环体
} while (condition);
```
先执行循环体，然后判定while，如果为真，再次执行循环

for循环

```javascript
for (begin;condition;step){
    // 执行语句
}
```
for 创建无限循环
```javascript
for (;;){
    // 执行语句，无限循环
}
```
break和continue关键字，只能在循环内部使用break和continue
break/continue标签 跳出多重循环
```javascript
labelName: for (){
    // 语句
    break labelName //跳出整个循环
}
```
## switch 语句
switch语句可以替代多个if判断，它至少需要一个case语句和一个可选的default语句
```javascript
switch(x){
    case 'value1':
        // 执行代码
        break
    case 'value2':
        // 执行代码
        break
    case 'value3':
    case 'value4':
        // 多个case执行相同代码
        break
    default:
        // 执行代码
}
```
类型很关键
这里的相等是严格相等，被比较的值必须是相同的类型才能进行匹配
在使用switch case结构时，一定不要忘了break关键词的使用

## 函数
函数声明
```javascript
function Name(from,text='这是默认值参数'){
    // 函数执行语句
    alert(from+': '+text)
}

Name()  //调用函数
```
函数内部是局部变量，函数外部是全局变量，内部可以访问

后备的默认参数
```javascript
function showMessage(text){
    if (text===undefined){
        text = 'empty message'  //在函数内部通过if判断是否传入参数，来初始化变量
    }
    // 在这里就可以使用到变量text
    // 或者我们可以使用或运算符 ||
    text = text || "empty"
}
```
### 空值合并运算符 ??
a??b  用来获取列表中第一个已定义的变量（即值不是null或undefined的变量）
如果a不是null或者undefined，返回a，否则返回b
空值合并运算符?? 禁止与 &&和||一起使用

返回值 return

空值return或没有return语句的函数返回undefined

return (age>18)?true:confirm('字符')
return age>18 || confirm('字符')

## 函数表达式
```javascript
let sayHi=function(){
    alert('Hello')
}
```
函数是被储存在变量里的一个值

### 函数声明和函数表达式区别
函数表达式是在代码执行到时才被创建，并且在这一刻起可以使用
函数声明在被定义之前，它就可以调用。因为Javascript在准备运行脚本之前，会找到所有的全局函数声明，并创建这些函数，可以称其为初始化过程

严格模式下，当一个函数声明在一个代码块内时，它在该代码块内的任何位置都是可见的。但在代码块外不可见。


## 箭头函数
`let func = (arg1,arg2,...argN) => expression`

使用参数对右侧的表达式求值并返回结果

`let sayHi = () => {alert('Hello')}  //没有参数，直接写括号`
对于多行语句，使用显示return进行返回
