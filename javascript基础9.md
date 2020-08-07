## 属性标志和属性描述符
我们知道对象可以储存属性
到目前为止，属性对我们来说只是一个简单的键值对。但是对象属性实际上是更灵活且更强大的东西
在本章中，我们将学习其他配置选项，在下一章中，我们将学习如何将它们无形地转换为getter/setter函数

属性标志
对象属性除了value外，还有三个特殊的特性，就是所谓的标志
writable 可以修改
enumerable 可以被循环
configurable 可以被删除

## 属性的getter和setter
有两种类型的对象属性
第一种是数据属性
第二种是访问器属性  本质上是用于获取和设置值的函数，但从外部代码来看就像常规属性

getter和setter
访问器属性由getter和setter方法表示。在对象字面量中，它们用get和set表示
使用get和set关键字可以设置和读取属性

```javascript
let user = {
    name:"John",
    surname:"Smith",
    get fullName(){
        return `${this.name} ${this.name}`
    }
    set fullName(value){
        [this.name,this.surname] = value.split(" ")
    }
}
alert(user.fullName)
user.fullName = "Alice Cooper"
// 设置了set就可以对属性进行修改
```

访问器描述符
get 一个没有参数的函数，在读取属性时工作
set 带有一个参数的函数，当属性被设置时调用
enumerable 与数据属性的相同
configurable 与数据属性的相同

使用defineProperty创建一个fullName访问器，我们可以使用get和set来传递描述符
```javascript
let user = {
  name: "John",
  surname: "Smith"
};

Object.defineProperty(user, 'fullName', {
  get() {
    return `${this.name} ${this.surname}`;
  },

  set(value) {
    [this.name, this.surname] = value.split(" ");
  }
});

alert(user.fullName); // John Smith

for(let key in user) alert(key); // name, surname
```


