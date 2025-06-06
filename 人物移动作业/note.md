图片居中
position: absolute;
top: 0;
left: 0;
right: 0;
bottom: 0;
margin: auto;

js
获取dom对像
let img=document.querySelector('')
检验获取没有
console.log（）
当自己不知道的是啥是用它判断，检验。查找问题。
通过style属性操作css
x[0].style.backgroundColor = ‘red’

随机颜色 <script> function setcolor(){ var letter = ‘0123456789ABCDEF’ var x = ‘#’ for(var i = 0;i<6;i++){ x += letter[Math.floor(Math.random()*16)] } console.log(x) return x; } var x = document.querySelector(‘body’) x.style.backgroundColor = setcolor() </script>

通过id获取 返回一个值 只能获取一个 <div id=“box1” class=“box”>box</div> var x = document.getElementById(‘box1’) console.log(x)

通过类名找到html元素 获取多个 var x = document.getElementsByClassName(‘box’) console.log(x)

通过标签名查找html元素 获取多个 var x = document.getElementsByTagName(‘div’) console.log(x)

获取html标签 document.documentElement

获取head标签 document.head

获取body标签 document.body

获取title标签 document.title

 注意：document.documentElement.onkeydown = function(event){}
 // 无论用户再页面哪个位置按下键盘 都会触发这个事件处理函数
 键盘事件：onkeydown onkeypress 键按下 <!-- onkeypress 不包含特殊键 -->
 将函数赋值给一个变量
        var b = function(){
            var y = 5;
            y++;
            return y
        }
        console.log(b())
 “把监听键盘事件与html绑定”给事件处理函数处理。
 event.key event.code 它们提供了关于被按下或释放的键的信息，但它们在表示键盘按键的方式上有所不同。“Enter”、“Escape”

 S 的 transform 属性中，涉及到沿 y 轴移动（使用 translateY 函数 ）时，向上移动数值为负，这主要基于以下的坐标系统原理：
笛卡尔坐标系统
CSS 中的坐标系统借鉴了数学上的笛卡尔坐标系统。在二维笛卡尔坐标系统中，水平方向是 x 轴，垂直方向是 y 轴。坐标原点 (0, 0) 位于平面的中心位置（在网页布局中，对于一个元素而言，通常是元素的中心 ）。

x 轴方向：正方向是从左向右，负方向是从右向左。
y 轴方向：正方向是从上向下，负方向是从下向上。

例如，当你使用 transform: translateY(50px); 时，元素会相对于其原始位置沿 y 轴正方向（也就是向下 ）移动 50 像素；而 transform: translateY(-50px); 则会使元素沿 y 轴负方向（即向上 ）移动 50 像素。
与常规视觉习惯的联系
这种设定虽然和我们日常习惯的 “向上为正” 的认知在一定程度上有所不同（比如在描述高度增加等情况时 ），但在图形绘制和坐标体系中是有逻辑依据的：

图形绘制顺序：在绘制图形或渲染页面元素时，浏览器等渲染引擎是按照从上到下、从左到右的顺序进行处理的。y 轴正方向向下，符合这种渲染的先后顺序逻辑。当数值增大，元素在渲染流中位置靠下，表现为向下移动。
一致性和规范性：遵循笛卡尔坐标系统的规范，能让 CSS 的 transform 等相关属性在处理元素位置、旋转、缩放等操作时，有统一且严谨的规则。这样无论是开发者编写代码，还是浏览器进行渲染，都能依据明确的标准，减少混乱和错误。

移动人有没有办法，卡在一个盒子出不去。