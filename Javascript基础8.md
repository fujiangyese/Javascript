## 调度：setTimeout和setInterval
有时我们不想立即执行一个函数，而是等待一段时间再执行，我们可以使用两种方式实现
setTimeout设置超时执行
setInterval重复运行函数，一段间隔之后再次执行
```let timerId = setTimeout(func,delay,arg1,arg2)```
func表明要执行的函数
delay执行延时，单位为毫秒
arg1,arg2,要传入被执行函数的参数列表
```javascript
function sayHi(){
    console.log('Hello')
}
setTimeout(sayHi,1000) //1秒之后执行sayHi函数
```
使用clearTimeout(括号里传入调度器名称)来取消调度
使用clearInterval(括号里传入调度器名称)来取消调度

## 装饰者模式和转发,call/apply
真难理解，跳过，不过和装饰器看起来有点像

## 函数绑定

丢失this
一旦方法被传递到与对象分开的某个地方——this就丢失了
```javascript
let user = {
  firstName: "John",
  sayHi() {
    alert(`Hello, ${this.firstName}!`);
  }
};

setTimeout(user.sayHi, 1000); // Hello, undefined!
```
解决方案1：包装器

解决方案2：bind
func.bind(user) func函数绑定对象，this=user。所有的参数都被原样传递给了初始的func

## 深入理解箭头函数
箭头函数没有this，如果访问this就会从外部获取
```javascript
let group = {
    title:"Our Group",
    students = ["John","Pete","Alice"],
    showList(){
        this.students.forEach(student=>alert(this.title+":"+student))
    }
}
group.showList()
```
这里的forEach中使用了箭头函数，所以其中的this.title其实和外部方法showList的完全一样。那就是group.title。



