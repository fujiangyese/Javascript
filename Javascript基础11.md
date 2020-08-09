## 静态属性和静态方法

我们可以把一个方法赋值给类的函数本身，这样的方法被称为静态方法
在一个类中，他们以static关键字开头
```javascript
class User {
  static staticMethod() {
    alert(this === User);
  }
}

User.staticMethod(); // true
```
静态方法要直接通过类名来进行调用

静态属性
静态属性看起来就像常规的类属性，但是它们前面加上static关键字

```javascript
class Article {
    static publisher = "Levi Ding"  //静态属性
}
alert(Article.publisher)
```
静态方法被用于实现属于整个类的功能。它与具体的类实例无关。
静态属性被用于当我们想要存储类级别的数据时，而不是绑定到实例。

## 私有的和受保护的属性和方法
使用前置下划线标记私有属性，通过get和set来设置和访问私有属性

## 扩展内建类
内建的类，例如 Array，Map 等也都是可以扩展的（extendable）。
内建类没有静态方法继承

## 类检查instanceof
```javascript
obj instanceof Class
```

## Mixin模式
主要是因为Javscript中只能单继承，所以有了这个东西，跳过
