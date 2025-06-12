1.布局
给一个盒子固定定位，宽度不定死，优先级。
添加标签，添加其余内容，实现滚轮操作即可
js
获取当前滚动位置
计算可滚动的距离
用这两个比较，x100作百分比形式，进度条。
插入盒子宽，改变盒子，随滚动变化，伸长伸短。

可视区宽高
window.innerWidth

window.innerHeight

包含滚动条的宽度
document.documentElement.clientWidth

document.documentElement.clientHeight

不包含滚动条
元素宽高
element.clientWidth element.clientHeight

是用于获取元素的可见宽度和高度的属性

不包含滚动条的宽度

element.offsetWidth element.offsetHeight

是用于获取元素的完整宽度和高度的属性

包含滚动条的宽度

element.scrollWidth element.scrollHeight

是用于获取元素内容的完整宽度和高度的属性

包含不可见的部分

元素距离
element.offsetLeft element.offsetTop
获取当前元素左边，到定位父级的上边的距离。
element.offsetParent 找到距离自身最近具有定位样式的祖先元素
滚动距离
element.scrollTop element.scrollLeft

用于获取或设置元素(页面)滚动条的垂直和水平滚动位置的属性
window.pageYOffset window.pageXOffset

用于获取文档在垂直和水平方向上相对于视口的滚动偏移量的属性。

element.clientLeft element.clienTop

用于获取元素的边框宽度和边框高度
回调函数是 JavaScript 中一个非常重要的概念，它本质上是一个作为参数传递给另一个函数的函数，当该函数完成任务后，会调用这个作为参数的回调函数。以下从几个方面详细介绍回调函数：
1. 基本概念与用途
定义：回调函数就是一个被作为参数传递到另一个函数里的函数，当这个参数函数所在的函数执行完它本身的任务后，就会执行这个回调函数。
用途：回调函数常用于处理异步操作。在 JavaScript 中，由于 JavaScript 是单线程语言，异步操作不能像同步操作那样按顺序等待结果返回，而是继续执行后续代码。当异步操作完成时，通过调用回调函数来处理其结果。例如，读取文件、网络请求等操作通常是异步的，需要使用回调函数来处理操作完成后的结果。
2级事件 元素.addEventListener(“事件名”,function)
0级事件元素绑定相同事件时,会执行后者事件函数 2级事件元素绑定相同事件时,按照顺序全部执行