## 原始类型的方法

在Javascript中有7种原始类型 string,number,bigint,boolean,symbol,null,undefined
关于对象的最好的事儿之一是，我们可以把一个函数作为对象的属性存储到对象中。

str.toUpperCase()  //转换成全大写
num.toFixed(2)  //保留小数位数

String、Number、Boolean进行数据类型间的转换
原始类型不是对象，它们不能储存额外的数据

Math.random() 返回一个0到1的随机数，不包括1
Math.pow(n,power) 返回n给定的power次幂
123e6  ==  123000000
123-e6 ==  0.00000123
parseInt parseFloat 可以从字符串中读取数字
num.toString(base) 将数字转换为给定的base系统中的字符串

## 字符串
字符串长度 str.length 使用length属性返回字符串长度
str[0]获取第一个字符，没获取到返回undefined
for (char of str) 遍历字符
字符串不可变，也就是不能 str[0]='a'
通常是将新的拼接字符串赋值给原来的变量

改变大小写函数
toUpperCase()
toLowerCase()

查找子字符串
使用str.indexOf(substr,pos) 从给定的pos位置开始查找，找到了返回字符所在起点索引值，没找到返回-1

在if判断中要检查返回值不为-1
```javascript
let str = "Widget with id";

if (str.indexOf("Widget") != -1) {
    alert("We found it"); // 现在工作了！
}
```
includes()
endsWith()
startsWith()

slice()切片
str.slice(起点,结束)
str.trim()删除字符串前后的空格

## 数组

对象允许存储键值对集合
数组Array就是Python中的列表
let array = []

pop/push,shift/unshift
push向末尾增加一个元素
pop从末端取出一个元素
shift删除第一个元素并返回
unshift在数组开始位置增加元素


push/pop 方法运行的比较快，而 shift/unshift 比较慢。

使用for of 遍历数组中的数据
```javascript
let fruits = ['Apple','Orange','Plum']
for (let fruit of fruits){
    alert(fruit)
}
// 常规遍历，通过循环变量做索引值
for (let i=0;fruits.length;i++){
    alert(fruits[i])
}
```
length属性可以求出数组的长度
清空数组最简单的方法 arr.length=0

创建指定长度的数组
let arr = new Array(2)  //创建两个长度的数组

多维数组
String函数可以将数组整个内容以字符串形式返回

## 数组方法

splice
删除元素
arr.splice(0,3)  //从索引值0开始，删除3个元素
插入元素
arr.splice(2, 0, "complex", "language");
从索引值2开始插入2个元素

concat合并数组
arr.concat([1,2],[3,4])

遍历forEach

arr.forEach(function(item,index,array){//do something})

forEach方法允许对数组的每一个元素都运行一个函数

在数组中搜索
indexOf/lastIndexOf/includes
arr.indexOf(item)  返回item在arr中的索引值，没找到返回-1
arr.includes(item) 返回布尔值

find/filter/map

reverse函数点到arr数组的顺序

split函数对字符串进行切割

arr.join(';') join函数对数组进行拼接

Array.isArray(arr)  判读arr是不是一个数组，返回布尔值

## 可迭代对象

## Map and Set （映射和集合）
Map允许任何类型的键

new Map() 创建map
map.set(key,value)  存储键值对
map.get(key)  获取键对应的值
map.has(key)  判断是否有key
map.delete(key)  删除指定键值对
map.clear()  清空map
map.size 返回当前元素个数

map.set 调用都会返回 map 本身，所以我们可以进行“链式”调用

map的迭代
map.keys()
map.values()
map.entries() [key,value]

map保留插入的顺序

Object.fromEntries  从Map创建对象

```javascript
let prices = Object.fromEntries([
    ['banana',1],
    ['watermelon',2],
])
// 现在 prices = {banana:1,watermelon:2}
```

## Set

值的集合，里面没有键，每个元素只能出现一次

主要方法：
new Set(iterable)  //创建一个可以迭代的set
set.add(value)
set.delete(value)
set.has(value)
set.clear()
set.size

Set 迭代
使用for ... of 或forEach来遍历Set

```javascript
set.forEach((value,valueAgain,set)=>{
    alert(value)
})
```
forEach的回调函数有三个参数，value，valueAgain，set对象

set.keys() 遍历返回所有的值

## 转换对象
对象缺少数组存在的许多方法，例如 map 和 filter 等。

如果我们想应用它们，那么我们可以使用 Object.entries，然后使用 Object.fromEntries：

使用 Object.entries(obj) 从 obj 获取由键/值对组成的数组。
对该数组使用数组方法，例如 map。
对结果数组使用 Object.fromEntries(array) 方法，将结果转回成对象。

Object.entries(对象)方法可以将对象转换为数组
然后使用map函数处理
最后使用Object.fromEntries(array) 将数组转换回对象

## 解构赋值
```javascript
let arr = ["Ilya","Kantor"]
let [firstName,lastName] = arr

Object.entries(对象)

交换两个变量的值
[guest, admin] = [admin, guest]  //单行赋值法
let [name1, name2, ...rest] = ["Julius", "Caesar", "Consul", "of the Roman Republic"]
```
...rest可以接收剩下的元素
对象解构
```javascript
let options = {
  title: "Menu",
  width: 100,
  height: 200
};

let {title, width, height} = options;

alert(title);  // Menu
alert(width);  // 100
alert(height); // 200
```
为了告诉 JavaScript 这不是一个代码块，我们可以把整个赋值表达式用括号 (...) 包起来

## 日期和时间

### 创建

```javascript
let now = new Date(); alert(now)
getFullYear()
获取年份（4 位数）
getMonth()
获取月份，从 0 到 11。
getDate()
获取当月的具体日期，从 1 到 31，这个方法名称可能看起来有些令人疑惑。
getHours()，getMinutes()，getSeconds()，getMilliseconds()
获取相应的时间组件。
以上的所有方法返回的组件都是基于当地时区的
```
同时也有基于UTC时区的时间
getUTCHours()

Date.now()返回当前的时间戳

对一个字符串使用Date.parse(str)，可以从字符串中读取到时间，并返回对应时间戳

### Javascript中的时间戳以毫秒为单位，而不是秒

## JSON方法, toJSON
JSON.stringify(对像) 将对象转换为JSON字符串
JSON.parse(JSON字符串) 将JSON字符串转换为对象或其他数据类型

```javascript
let str = '{"title":"Conference","date":"2017-11-30T12:00:00.000Z"}';

let meetup = JSON.parse(str, function(key, value) {
  if (key == 'date') return new Date(value);
  return value;
});

alert( meetup.date.getDate() ); // 现在正常运行了！
```
给parse函数增加第二个参数，使用new Date让返回的日期字符串变成时间格式




