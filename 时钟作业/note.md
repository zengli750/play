布局
第1个问题，body渐变色，不给高度显示出来，不过没倾斜角度。与老师讲的有点不一样。发现如果没有去除外边框，不给高度照样可以看到渐变色。
在 CSS 中，max - width（最大宽度）、min - width（最小宽度）、max - height（最大高度）和 min - height（最小高度）属性用于限制元素的尺寸，它们在网页布局中起着重要作用，特别是在响应式设计方面。以下是对这些属性的详细介绍：
1. max - width（最大宽度）
作用：限制元素的宽度不能超过指定的值。当元素内容或其他 CSS 属性试图使元素宽度超过 max - width 设置的值时，元素宽度将被限制在该最大值，从而防止元素过度扩展。
语法：max - width: value;，其中 value 可以是具体的长度值（如 px、em、rem 等）、百分比（%）或关键字 none（表示无限制）。
示例：

css
div {
  max - width: 500px;
  background - color: lightblue;
}

在这个例子中，无论 div 内部内容如何，其宽度最大为 500 像素。如果内容较少，div 宽度会自适应变小。
2. min - width（最小宽度）
作用：确保元素的宽度至少为指定的值。当元素内容或其他 CSS 属性试图使元素宽度小于 min - width 设置的值时，元素宽度将保持在该最小值，从而防止元素过度收缩。
语法：min - width: value;，value 的取值与 max - width 类似。
示例：

css
button {
  min - width: 120px;
  padding: 10px 20px;
  background - color: green;
  color: white;
}

这里的按钮宽度最小为 120 像素，即使按钮文本很短，宽度也不会小于此值。
3. max - height（最大高度）
作用：限制元素的高度不能超过指定的值。当元素内容或其他 CSS 属性试图使元素高度超过 max - height 设置的值时，元素高度将被限制在该最大值，例如防止图片或文本块过度拉伸。
语法：max - height: value;，value 同样可以是具体长度值、百分比或 none。
示例：

css
img {
  max - height: 300px;
  width: auto;
}

这使得图片高度最大为 300 像素，宽度会根据图片原始比例自动调整，避免图片在页面中占据过大的垂直空间。
4. min - height（最小高度）
作用：保证元素的高度至少为指定的值。当元素内容或其他 CSS 属性试图使元素高度小于 min - height 设置的值时，元素高度将维持在该最小值，常用于确保元素有足够的空间显示内容。
语法：min - height: value;，value 取值方式与上述属性一致。
示例：

css
textarea {
  min - height: 150px;
  width: 300px;
}

此 textarea 元素高度最小为 150 像素，用户无法将其高度调整到小于该值，保证了文本输入区域有足够空间。
5. 与其他属性的交互及应用场景
与 width 和 height 的关系：width 和 height 设置的是元素的基础尺寸，而 max - width、min - width、max - height 和 min - height 对其进行限制和补充。例如，当 width 设置为 auto 时，max - width 和 min - width 决定了元素宽度的范围；当 height 设置为 auto 时，max - height 和 min - height 决定了元素高度的范围。
响应式设计：在响应式布局中，这些属性非常有用。通过媒体查询结合 max - width 和 min - width，可以根据不同屏幕宽度调整布局。例如：

css
@media (max - width: 768px) {
  div {
    max - width: 100%;
  }
}


这段代码表示当屏幕宽度小于等于 768 像素时，div 元素的最大宽度变为 100%，即充满其父容器，适应移动设备屏幕。

图片和媒体元素：对于图片、视频等媒体元素，使用 max - width 和 max - height 可以确保它们在不同屏幕尺寸下不会超出容器边界，同时保持比例。例如：

css
video {
  max - width: 100%;
  max - height: 100%;
}


这使得视频在任何容器中都能按比例缩放，不会溢出容器。

通过合理使用 max - width、min - width、max - height 和 min - height 属性，可以创建更加灵活、健壮且适应不同设备的网页布局。

第二个问题，用了flex，但是没效果，涉及flex布局放哪里?怎么放？确认应用 display: flex 的元素：Flex 布局需要将 display: flex 应用到要作为容器的元素上，该容器的直接子元素会成为 Flex 项目。例如，如果你想让一组列表项水平排列，应该将 display: flex 应用到包含这些列表项的父元素（如 <ul> 元素）上，而不是列表项（<li> 元素）本身。

检查是否有冲突的 CSS 属性：其他 CSS 属性可能会与 Flex 布局冲突。例如，给 Flex 项目设置了固定的 width 和 height，且这些值与 Flex 布局的空间分配规则冲突。另外，float、position（除 static 外）等属性会使元素脱离文档流，从而破坏 Flex 布局的正常行为。确保 Flex 容器及其项目没有应用这些可能产生冲突的属性，或者根据需求进行适当调整。
检查浏览器兼容性：虽然 Flex 布局在现代浏览器中得到了广泛支持，但某些旧版本浏览器可能存在兼容性问题。可以通过添加浏览器前缀（如 -webkit -、-moz - 等）来提高兼容性。不过，随着浏览器的更新换代，这种情况已经越来越少见。
align-items: center;align-items 属性设置 Flex 容器内所有 Flex 项目在交叉轴（与主轴垂直的轴，其方向取决于flex - direction属性）上的对齐方式为居中对齐。
justify-content: center;1. 在 Flexbox 布局中的应用
主轴与交叉轴概念：在 Flexbox 布局中，flex - direction 属性决定主轴方向。默认值 row 下，主轴为水平方向，从左到右；当值为 column 时，主轴为垂直方向，从上到下。而与主轴垂直的方向就是交叉轴。
justify - content: center 的作用：该属性将 Flex 容器内的 Flex 项目在主轴上居中排列。这意味着项目会集中在 Flex 容器主轴方向的中间位置，项目两侧的空白空间会均匀分布。
js
为什么写时钟直接一个间隔定时器。
1. 时钟的本质需求
时钟需要周期性地更新显示，也就是每隔固定的时间间隔（通常是 1 秒，因为时间的最小常用单位展示精度一般到秒就够，当然也可以根据需求调整，比如要显示毫秒的话间隔可以设小些），获取当前最新的时间并更新到页面上对应的位置（比如 <span> 元素里显示小时、分钟、秒等信息 ）。而间隔定时器的特性就是能够按照指定的时间周期重复执行一段代码，正好契合时钟这种周期性更新的需求。
用时间间隔器后，先实例化时间,获取html指定对象，把实例化的时间对象获取时间的函数给到html的指定对象
textContent可以使用 textContent 获取指定元素及其所有后代元素的纯文本内容。它会忽略元素的标签，只返回文本信息。
document.documentElement('div', 'time') 这部分存在问题。document.documentElement 是获取文档的根元素（通常是 <html> 元素），它是一个属性，不是一个函数，不能像这样传递参数调用。如果想要获取页面中的 <div> 元素和 <time> 元素，应该使用 document.querySelector 或 document.querySelectorAll 等方法。例如，如果页面中有一个 id 为 timeDiv 的 <div> 元素，正确的获取方式是 document.getElementById('timeDiv')，如果是通过标签名获取所有 <div> 元素则可以用 document.getElementsByTagName('div')，通过类名获取可以用 document.getElementsByClassName('className')，更通用的选择器可以用 document.querySelector('选择器') 或 document.querySelectorAll('选择器')。