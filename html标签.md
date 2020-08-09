js暂告一段落，来看看html标签

水平线标签  <hr />
水平分割线，可以在视觉上将文档分成各个部分

换行 <br />

div标签和span标签

div标签：可以把标签中的内容分割为独立的区块。必须单独占一行
div标签具有align属性 可以设置区块的位置 div是容器级标签，里面什么都能放
span标签：和div作用一致，但不换行  span是文本级标签，里面只能放置文字、图片、表单元素
span里不能放p、h、ul、dl、ol、div

div标签负责布局、结构、分块，css负责样式。

<u> 下划线
<s> 中划线
<i> 斜体标记
<b> 粗体标签
<a> 超链接
通过瞄点实现回到顶部的效果

超链接属性 href打开链接，title悬停文本，target打开方式 _self当前页打开，_blank在新标签页打开
将a标签放置在p标签内
dl dt dd
table tr td

内嵌框架<iframe>标签
div  p  h1  span   a   img   ul   ol    dl    input

## HTML5
新增语义标签
<section> 表示区块
<article> 表示文章、评论、帖子、博客
<header> 表示页眉
<footer> 表示页脚
<nav> 表示导航
<aside> 表示侧边栏
<figure> 表示媒介分组
<mark> 表示标记
<progress> 表示进度
<time> 表示日期

H5中的表单
email 只能输入email格式。自动带有验证功能。
tel 手机号码。
url 只能输入url格式。
number 只能输入数字。
search 搜索框
range 滑动条
color 拾色器
time 时间
date 日期
datetime 时间日期
month 月份
week 星期

## 音频
<audio src="..mp3" autoplay controls> 使用audio标签来播放音频
<video> 标签来播放视频

## DOM操作
获取元素
document.querySelector("selector") 通过CSS选择器获取符合条件的第一个元素。
document.querySelectorAll("selector") 通过CSS选择器获取符合条件的所有元素，以类数组形式存在。
类名操作
Node.classList.add("class") 添加class
Node.classList.remove("class") 移除class
Node.classList.toggle("class") 切换class，有则移除，无则添加
Node.classList.contains("class") 检测是否存在class

