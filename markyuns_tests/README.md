#前端开发面试题 （题目列表页）


## <a name='list'>目录</a>

  1. [前言](#preface)
  1. [HTML 部分](#html)
  1. [CSS  部分](#css)
  1. [JavaScript 部分](#js)
  1. [其他问题](#other)
  1. [优质网站推荐](#web)



## <a name='preface'>前言</a>

略


## <a name='html'>HTML</a>

- Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?

> 该声明位于HTML文档最上方的位置，处于html标签之前，用于告知浏览器使用哪种HTML/XHTML规范。
不规范的声明会导致某些浏览器(IE)进入混杂模式，该模式针对一些比较古老的页面进行优化，现在已经很少见了。
它们的意义在于对文档进行有效性验证，以及告知浏览器需要使用哪种模式对页面进行渲染。

- 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

> * 行内元素： h1~h6, p, a, span, input(部分), strong, b, i, img等等

> * 块级元素： div, ul, li, 大部分的HTML5新标签如 section, article, aside, nav, header, footer, hgroup等等

> * 空元素： img, input, embed, hr, br等等

- 介绍一下CSS的盒子模型？

> 盒子模型是用于定义一般元素的渲染规则，一个Box Model包含content(内容区)，padding(内边距), border(边框)，margin(外边距)。
IE的盒子模型是border-box，W3C的盒子模型是content-box，在CSS3中加入了新的属性box-sizing可以自定义盒模型的计算规则。

- link 和@import 的区别是？

> link是在HTML中使用，@import是在CSS文件中使用。
link中外链的文件会在渲染时进行加载，@import在渲染完成时进行加载，link的文件优先级较高。

- CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？

> 首先是通配符选择器*，然后标签选择器，类选择器，id选择器，属性选择器，后代选择器等等；

> font-size, font-family, color等属性可以继承，width, height, float, position, padding, margin等属性不会继承

> 后加载的优先级比较高，选择器越精确优先级越高，然后外链的样式，页面内style标签的样式，标签内联的样式优先级从低到高，使用!important声明可以提升到最高优先级

> 新增的伪类有:nth-child(n), :last-chile, :first-chile, :last-of-type, :target, :disabled, :checked等等

- 如何居中div？如何居中一个浮动元素？

> 使用margin: 0 auto;可以居中块级元素；

> 使用left: 50%;margin-left: -50%(知道元素宽度的情况下的1/2宽);居中bfc元素。

- 浏览器的内核分别是什么?

> IE的Trident(新的Edge将会使用新内核),Mozilla的Gecko,Chrome的Blink(源于webkit),Safari的webkit,Opera原来使用Presto,现在转为Blink

- html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和
HTML5？

> 新特性，增加了LocalStorge，Geolocation等新的API，支持新的流媒体标签，表单控件更新等等

> 移除了一些有性能问题的标签如frameset,noframe，以及表示样式的标签font, center等等。

> 标签可以使用createElement来创建，可以兼容IE，一些特性只能靠polyfill来解决，或者使用比较成熟的库

> 可以通过DOCTYPE来区分，或者是从内容结构，是否调用了新的API来判断

- 语义化的理解？

>放上两个链接吧……
![](http://www.iandevlin.com/blog/2011/04/html5/html5-section-or-article)
![](http://www.zhihu.com/question/20308005/answer/17571043)

> 另外也可以有助于SEO,理清文档结构等。

- HTML5的离线储存？

> 提供了LocalStorge的接口，可以通过调用它存储一定的本地数据。

- (写)描述一段语义的html代码吧。

```
<nav>
    <ul>
        <li>Home</li>
        <li>Home</li>
        <li>Home</li>
    </ul>
</nav>
<article>
</article>
```

- iframe有那些缺点？

> 会阻塞页面的onload事件

- Label的作用是什么？是怎么用的？（加 for）

> label用于描述表单，for属性可以链接至表单的id，点击label时可以直接对链接的表单focus

- HTML5的form如何关闭自动完成功能？给不想要提示的input是设置autocomplete=off即可

> 设置属性autocomplete=off

- 请描述一下 cookies，sessionStorage 和 localStorage 的区别？

> 由于HTTP是一个无状态的协议，为了记住用户状态，可以给用户设置cookies，这样浏览器在向服务器发送请求时附带上这个cookies服务器就可以知道请求用户的状态。

> sessionStorage和localStorage都是HTML5新添加的特性，sessionStorage可以在本次会话中保存一些数据，localStorage则可以长期保存本地数据，并且它们不会每次都发送给服务器，并且拥有更大的容量和更多的接口。

- 如何实现浏览器内多个标签页之间的通信? (阿里)

> 调用本地存储如localStorage，SessionStorage等，或者使用websocket主动推送，轮询等方式。

- webSocket如何兼容低浏览器？(阿里)

> 轮询或者long pull，对服务器的负担比较大

- 页面可见性（Page Visibility）API 可以有哪些用途？

> 监测用户是否在观看这个页面，如果不是可以暂停页面上的一些效果等等

- 你是怎么切图的？

> PS切图呗………………

## <a name='css'>CSS</a>

- 列出display的值，说明他们的作用。position的值， relative和absolute定位原点是？

> block,块级元素，会从上至下的排列，遵循基本盒模型的渲染规则，类似的还有list-item等

> inline，行内元素，横向排列，一般用于渲染文字

> none, 隐藏元素，不显示，也不会在文档中占用位置

> table，表格元素，按照表格的特定渲染规则渲染，下级还有table-row,table-cell等元素

- CSS3有哪些新特性？

> 比较重要的有动画属性。另外还有渐变，阴影，文字阴影，新增的背景属性

> 过渡的transition, 变形的transform, 自定义字体，flex布局，媒体查询，新的伪类等等

- 用纯 CSS 创建一个三角形

```
.triangle {
    display: block;
    width: 0;
    height: 0;
    border: 50px solid transparent;
    border-top: 50px solid #000;
}
```

- 一个满屏 品 字布局 如何设计?*

> 这个先搁置……

- 经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hack的技巧 ？*

> 比较少遇到兼容问题……

- 为什么要初始化CSS样式。

> 因为各个浏览器的默认样式不同，有时候为了避免一些未设置的默认样式在不同浏览器中导致不同效果，首先会先初始化CSS样式

- absolute的containing block计算方式跟正常流有什么不同？*

> 正常流的containing block由最近的block element建立。absolute元素的containing由最近的非static元素建立

- CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？*

> 折叠，在表格元素中会空出一行或者一列供其它元素使用，其它元素中则会表现为hidden。

- position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？

> ……

- 对BFC规范的理解？

> block formatting context，某些特定的规则会触发生成BFC，BFC是一个独立渲染的区域，可以利用这种技术来解决一些布局的问题。

- css定义的权重？

> 标签权重为1，类权重为10，id权重为100，在此基础上越精确的选择权重越高，!important声明具有最高权重。

- 解释下浮动和它的工作原理？清除浮动的技巧

> 浮动会使元素脱离文档流移动到父级元素的最左/最右边，同时也会触发BFC。可以利用浮动进行一些布局。

> 个人觉得比较重要的一点是，浮动一开始是用来用作图文混排的。

- 用过媒体查询，针对移动端的布局吗？

> 用过。移动端的媒体查询主要是dpr查询和屏幕高宽比的查询，用来制作单页的页面。

> 页面视口宽度的查询主要还是用于制作响应式的页面。

- 使用 CSS 预处理器吗？喜欢那个？

> 使用过，较常用的是stylus。

- CSS 优化、提高性能的方法有哪些？

> CSS sprite，字体图标等，避免使用通配符

> 另外CSS选择器的查找是由右至左，所以嵌套层级较少，顶点定位比较精确的CSS选择器查询效率比较高。

- 浏览器是怎样解析CSS选择器的？

> 从最右边的选择器声明开始解析，然后向父级查找。所以嵌套较多的选择器性能较为低下。

- 这个CSS它是如何工作的？（ .mod-nav h3 span {font-size: 16px;} ）

> mod-nav类的元素下的h3中的span元素，字体大小为16px。

- 在网页中的应该使用奇数还是偶数的字体？为什么呢？

> 其实倒没有太在意过……一般来说是使用偶数字体，因为有些浏览器会将奇数大小的字体强制渲染成偶数字号，或者某些奇数字号渲染效果不太好。
不过一切以实际显示的效果为准（或者以设计稿为准）。

> 因为目前响应式的设计越来越多，字号也偏向于使用相对字号，并且设置一个根字号。所以这个问题也不用太在意。

- margin和padding分别适合什么场景使用？

> 顾名思义，margin(外边距)应当是元素与元素之间的间距，而padding(内边距)应该是元素边界与内容之间的空间，就如同一个箱子装东西应该有厚度。

- 元素竖向的百分比设定是相对于容器的宽度吗？

> 应该是，记得有看过类似的文章，求大牛解答。

- 全屏滚动的原理是什么？用到了CSS的那些属性？

> fullpage scroll?

- ::before 和 :after中双冒号和单冒号 有什么区别？解释一下这2个伪元素。

> 单引号用于伪类，表示元素的某一种特殊状态，双引号用于伪元素，用于渲染一个特殊元素。

> before和after虽然官方说法是在新的浏览器中不要使用的旧的单引号写法，但是实际使用中并没发现有什么鸟区别。

- 你对line-height是如何理解的？

> 用过PS的应该比较好理解，PS的行高就是字体顶部和下一行字体顶部之间的距离。网页中同样，不过不一定是字顶到字顶的区别。具体决定于vertical-align属性。line-height不使用单位比较好（除非一些特殊场景。）

- 设置元素浮动后，改元素的display值是多少？

> 浮动元素都以`display: block`方式渲染

- 怎么让Chrome支持小于12px 的文字？

> `-webkit-text-size-adjust: none;`

- 让页面里的字体变清晰，变细用CSS怎么做？

> `-webkit-font-smoothing: antialiased;`

- font-style属性 可以让它赋值为“oblique” oblique是什么意思？

> 斜体，一些字形不全的字体可能没有斜体的渲染，italic不管用的情况下就用oblique强制倾斜

- position:fixed;在android下无效怎么处理？

> 没遇到过，查了一下，可以通过禁止用户缩放，并且强制缩放1倍大小解决。(需要为此制作移动端网页。否则显示效果很烂)

- 如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）

> 显示器一般刷新率都为60hz，手机的常规运行帧数也是60fps，也就是说每帧大概1000ms/60≈16ms左右，动画嘛一般都要几个过渡帧，所以50ms左右应该是比较合适的最小时间间隔。

- display:inline-block 什么时候会显示间隙？(携程)

> inline-block元素之间在html文档中有换行，空格等。

> 可以把inline-block元素看作是文字，解决这个问题的方法有将html文档的标签闭合，或者为父级元素设置字号，然后使用负margin，或者是将字体大小设为0px(chrome加上-webkit-text-size-adjust: none;)

## <a name='js'>JavaScript</a>

-  用原生JS的写过东西吗？

> 写过。

-  JavaScript原型，原型链 ? 有什么特点？

> 可以通过原型来来实现javascript中的继承。通过使用new操作符或者直接使用对象的prototype属性链接，也有比较新的API如Object.create()

> Javascript在调用对象中的属性时若在本身的属性中的找不到则会向原型中查找，原型的中查找不到则向原型的原型中查找，知道查找到根对象，若没有则抛出错误。将这些对象连接起来的就是原型链。

> 它是javascript中实现继承的唯一方法。也是js最有特点最为优雅的特性之一。

-  JavaScript 有几种类型值？，你能画一下他们的内存图吗？

> （堆：原始值和 栈：引用值），内存图不会画。比如字符类型就是原始值，对象和数组则是引用值（指针）。

-  eval是做什么的？

> 将一段字符串当作是js代码执行，并且引擎会将它当作是一开始就存在于那里来解析。js性能杀手之一，不要用。

-  null，undefined 的区别？

> null表示一个空值，undefine就是未定义。

-  写一个通用的事件侦听器函数。

> what?!

-  Node.js的适用场景？

> 最早是用作后端，http服务器，web app服务器，也可以制作一些命令行工具，如一些很著名的前段库和构建工具都是使用node实现的。另外也可以用于开发桌面程序，使用比如node-webkit, electron等

-  介绍js的基本数据类型。

> Object, Array, String, Number, Boolean

-  Javascript如何实现继承？

> 使用原型

-  ["1", "2", "3"].map(parseInt) 答案是多少？

> [1, NaN, NaN]………很出名的题了

-  如何创建一个对象? （画出此对象的内存图）

> * 直接声明一个对象 var obj = {};
* Object.create()

-  谈谈This对象的理解。

> this即是指向当前执行的上下文的，是基于调用链的。不过JS里面有太多切换上下文的方法。

> obj.method()会将上下文隐式地绑定到obj上。
另外使用func.apply()或者func.call()可以显式地将this绑定到新的上下文。new操作符也是显式绑定。

> ES5中也有func.bind()方法来绑定this到新的上下文。

> ES6中的胖箭头声明 () =>则会将this绑定到函数中。

-  事件、IE与火狐的事件机制有什么区别？ 如何阻止冒泡？

> 很古老的梗了，在mozilla还叫netscape的时候使用的事件机制是事件捕获，是从上到下的触发。IE则是事件冒泡，从下到上触发。当代的浏览器和时间基本默认以冒泡方式进行（W3C的标准监听中则是同时支持两种方式的）。

> 使用stopPropagation()函数阻止冒泡（在事件的原型中）

-  什么是闭包（closure），为什么要用它？

> ES6之前js无法显式地声明块级作用域，创建作用域的方法只有函数function与try catch方法。

> 由于直接创建的变量都会变成全局变量，所以使用函数（一般是自启动函数IIFE）来创建一个作用域，在作用域中声明一些变量，使用函数来调用它们，并且创建一个暴露给外部的接口，因为函数的调用是基于词法作用域的，所以在外部运行函数也能取到闭包函数内部的数据。这样的函数就称之为闭包。

-  "use strict";是什么意思 ? 使用它的好处和坏处分别是什么？

> 使用严格模式。使用之后平时一些引擎睁一只眼闭一只眼的错误也会报错甚至导致程序崩溃。在保证代码规整或者为了保证代码规整的情况下可以使用。

-  如何判断一个对象是否属于某个类？

> instanceof操作符，判断一个对象是否是另外一个对象的实例

-  new操作符具体干了什么呢?

> 将操作符后的函数创建一个新的实例。返回一个新函数，并且将this指针绑定到这个函数上面。将返回的函数的Constractor绑定到被操作的函数上，将返回函数的prototype绑定到被操作函数的prototype上。

-  Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是？

> hasOwnProperty()

-  JSON 的了解？

> JavaScript Object Notation,js对象标记法，一种数据格式。它就是基于javascript的，所以在js中也可以十分方便地操作这种数据。


- ```
[].forEach.call($$("*"),function(a){
  a.style.outline="1px solid #"+(~~(Math.random()*(1<<24))).toString(16)
})
```

能解释一下这段代码的意思吗？

> 调用了数组的forEach方法，将this绑定到$$('*')上，并传入一个匿名函数的参数

> 这段函数的重点在`(~~(Math.random()*(1<<24))).toString(16)`部分，首先1<<24将1的二进制数左移24位，就是十进制的2的24次方，然后乘以Math.random()，会生成一个0~2的24次方的随机数，使用~~操作符取反，~操作符是将数字的二进制取反，两次操作则会返回原数字的整形，最后number.toString(16)，接受一个参数作为进制，格式转换为一个RGB颜色。

> 可以想象`$$('*')`函数通过通配符取到了页面所有的元素，然后通过forEach方法遍历其中每一个元素，forEach接受一个callback参数并对每一个元素使用callback函数，向其中传入三个参数: currentValue, index, array，这里只传入了当前值，也就是将当前元素的outline属性改变1px solid以及一个随机的RGB颜色。

> 所以这段代码的含义就是将页面的所有元素加上一个随机颜色的1px的边框。

-  js延迟加载的方式有哪些？

> html5中新加了async属性，可以放在script标签中异步加载。还有一个兼容性比较好的defer属性。

-  ajax 是什么?

-  同步和异步的区别?

-  如何解决跨域问题?

-  模块化怎么做？

-  AMD（Modules/Asynchronous-Definition）、CMD（Common Module Definition）规范区别？

-  异步加载的方式有哪些？

-  .call() 和 .apply() 的区别？

-  Jquery与jQuery UI 有啥区别？

-  JQuery的源码看过吗？能不能简单说一下它的实现原理？

-  jquery 中如何将数组转化为json字符串，然后再转化回来？

-  针对 jQuery 的优化方法？

-  JavaScript中的作用域与变量声明提升？

-  如何编写高性能的Javascript？

-  那些操作会造成内存泄漏？

-  JQuery一个对象可以同时绑定多个事件，这是如何实现的？

-  写一个无刷新的网站，并且能在浏览器前进、后退时正确响应怎么实现？

-  如何判断当前脚本运行在浏览器还是node环境中？（阿里）

-  canvas的默认大小是多少？

-  移动端最小触控区域是多大？

-  jQuery 的 slideUp动画 ，如果目标元素是被外部事件驱动, 当鼠标快速地连续触发外部元素事件, 动画会滞后的反复执行，该如何处理呢?

-  移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决？（click 有 300ms 延迟,为了实现safari的双击事件的设计）
-  Zepto的点透问题如何解决？


## <a name='other'>其他问题</a>


- 你遇到过比较难的技术问题是？你是如何解决的？

- 常使用的库有哪些？常用的前端开发工具？开发过什么应用或组件？

- 页面重构怎么操作？

- 列举IE 与其他浏览器不一样的特性？

- 99%的网站都需要被重构是那本书上写的？

- 什么叫优雅降级和渐进增强？

- WEB应用从服务器主动推送Data到客户端有那些方式？

- 对Node的优点和缺点提出了自己的看法？

- 你有哪些性能优化的方法？

- http状态码有那些？分别代表是什么意思？

- 一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？（流程说的越详细越好）

- 除了前端以外还了解什么其它技术么？你最最厉害的技能是什么？

- 你常用的开发工具是什么，为什么？

- 对前端界面工程师这个职位是怎么样理解的？它的前景会怎么样？

- 你怎么看待Web App 、hybrid App、Native App？

- 你移动端前端开发的理解？（和 Web 前端开发的主要区别是什么？）

- 加班的看法？


- 平时如何管理你的项目？

- git如何删除错误提交的文件？


- 如何设计突发大规模并发架构？


- 说说最近最流行的一些东西吧？平时常去哪些网站？


- 移动端（Android IOS）怎么做好用户体验?


- 你在现在的团队处于什么样的角色，起到了什么明显的作用？

- 你认为怎样才是全端工程师（Full Stack developer）？


- 介绍一个你最得意的作品吧？

- 你有自己的技术博客吗，常去那些技术博客？

- 最近在学什么？能谈谈你未来3，5年给自己的规划吗？

## 有趣的问题


- .A、B两人分别在两座岛上。B生病了，A有B所需要的药。C有一艘小船和一个可以上锁的箱子。C愿意在A和B之间运东西，但东西只能放在箱子里。只要箱子没被上锁，C都会偷走箱子里的东西，不管箱子里有什么。如果A和B各自有一把锁和只能开自己那把锁的钥匙，A应该如何把东西安全递交给B？

      答案：A把药放进箱子，用自己的锁把箱子锁上。B拿到箱子后，再在箱子上加一把自己的锁。
    箱子运回A后，A取下自己的锁。箱子再运到B手中时，B取下自己的锁，获得药物。


## <a name='web'>优质网站推荐</a>

1. 极客标签：     http://www.gbtags.com/


2. 码农周刊：     http://weekly.manong.io/issues/


3. 前端周刊：     http://www.feweekly.com/issues


4. 极客头条：   http://geek.csdn.net/


5. Startup News：http://news.dbanotes.net/


6. Hacker News： https://news.ycombinator.com/news


7. InfoQ：        http://www.infoq.com/


8. w3cplus：    http://www.w3cplus.com/


9. Stack Overflow： http://stackoverflow.com/



###last updated:  2015-03-25

  爱机车、爱骑行、爱旅行、爱摄影、爱阅读的理想青年，前端开发攻城师。

  我的微博：http://weibo.com/920802999
