# jquery-tooltipster
jQuery插件tootip提示框,可配置,可选择样式
[中文文档地址](http://www.jq22.com/yanshi14735)

#简单样例

1.引入文件
```javascript
<head>
    <link rel="stylesheet" type="text/css" href="tooltipster/dist/css/tooltipster.bundle.min.css" />

    <script type="text/javascript" src="http://code.jquery.com/jquery-1.10.0.min.js"></script>
    <script type="text/javascript" src="tooltipster/dist/js/tooltipster.bundle.min.js"></script>
</head>
```

2.设置html

```html
想让一个元素加入工具提醒, 我们会给他加上一个类名class 'tooltip' . 
你也可以选择使用自定义的类名或选择器(请继续往下看), 由你决定. 之后, 我们将设置标题title 属性为我们想要的提示. 这里有几个栗子:
```

```javascript
// 在图片加入工具提醒:
<img src="my-image.png" class="tooltip" title="This is my image's tooltip message!" />

// 在文字加入工具提醒 (span, div or whatever):
<span class="tooltip" title="This is my span's tooltip message!">Some text</span>
```

3.激活 Tooltipster
```javascript
  <script>
        $(document).ready(function() {
            $('.tooltip').tooltipster();
        });
    </script>

```
4.自定义样式风格
样式表文件在themes文件夹里
第一个是默认样式, Tooltipster还为你提供另外五种主题风格.
![image text](https://raw.githubusercontent.com/wsb260/jquery-tooltipster/master/demo/img/img1.jpg)
```javascript
$('.tooltip').tooltipster({
    theme: 'tooltipster-noir' //使用Noir主题
});
```
5.参数说明
```javascript
参数 	可用的值 	描述
animation
	'fade',
'grow',
'swing',
'slide',
'fall' 	决定tooltips进场的动画. 除了内置的动画, 你也可以创建自定义动画在你的CSS文件. 在IE9及以下, 所有动画默认为javascript生成淡入动画. 默认值: 'fade'

animationDuration
	integer,
integer[] 	设置动画的持续时间, 以毫秒为单位. 如果你想为你的tooltips打开/关闭提供不同的持续时间, 你可以提供一个数组来表示不同的值(如:integer[400,500]). 默认值: 350
arrow
	boolean 	给你的tooltips加一个"气泡" 箭头. 默认值: true
content
	string,
jQuery object,
any 	如果设置了, 将会覆盖tooltips的内容. 如果您提供的内容不是字符串或jQuery封装的HTML元素,你需要使用'functionFormat'这个参数来格式化你的内容以达到显示效果默认值: null
contentAsHTML
	boolean 	如果tooltip的内容是字符串, 会默认显示为纯文本. 如果想将内容解析为HTML, 请将这个参数设为true. 默认值: false
contentCloning
	boolean 	如果你提供了一个JQ对象给'content'这个参数,如果这个克隆对象应该被使用,则设置此参数.默认值: false
debug
	boolean 	当你做了你不应该做的事情,tooltipster日志提醒和通知会在控制台报错,如果你设置了false便可以禁用日志记录默认值: true
delay
	integer,
integer[] 	在鼠标交互的时候,这个属性是在hover/trigger..触发tooltip开始打开或者关闭动画使用时生效(简单来说就是一个延时器)(*). 如果你想为你的tooltips打开/关闭提供不同的持续时间, 你可以提供一个数组来表示不同的值(如:integer[400,500]).默认值: 300
delayTouch
	integer,
integer[] 	在触摸交互的时候, 同上(*).如果你想为你的tooltips打开/关闭提供不同的持续时间, 你可以提供一个数组来表示不同的值(如:integer[400,500]). 默认值: [300, 500]
distance
	integer,
integer[] 	以像素为单位,远点到提醒工具的距离.如果您希望为每个边指定不同的距离，则该值可以是整数或整数数组（通常为CSS语法）。 默认值: 6
functionInit
	function 	在实例化时只被触发一次的自定义函数. Arguments. 默认值: none (null)
functionBefore
	function 	在打开工具提示之前要触发的自定义函数. 这个发方法会阻止tooltip打开如果返回false.Arguments. 默认值: none (null)
functionReady
	function 	当工具提示及其内容被添加到DOM时，将触发自定义函数. Arguments. 默认值: none (null)
functionAfter
	function 	一旦工具提示已关闭并从DOM中移除,则将定制一个函数.Arguments. 默认值: none (null)
functionFormat
	function 	格式化内容的函数.它得到两个第一个通常的参数和第三个参数的内容。它必须返回在工具提示中显示的值，无论是字符串还是jQuery封装的HTML元素（请参阅格式化部分）. 默认值: none (null)
functionPosition
	function 	当tooltip重新定位时触发的自定义函数,它给你轻微或完全修改的位置，Tooltipster是要给tooltip的能力,它将建议的放置值集设置为第三个参数.函数必须返回您可能编辑过的位置值集合（请参阅定位部分）. 默认值: none (null)
IEmin
	integer 	要运行的IE的最低版本. 默认值: 6
interactive
	boolean 	在工具提醒给用户尽可能多的交互.如果你想他们在工具提醒内容可以点击，填写表格或者其他交互，你就必须把这个参数设置为true.当使用“悬停”关闭触发器时，用户必须在开始关闭之前将光标移到工具提示上（此时间间隔由“delay”参数设置）. 默认值: false
maxWidth
	integer 	设置tooltip的最大宽度. 默认值: null (无限制)
minIntersection
	integer 	对应于箭头中心和工具提示边缘之间强制执行的最小距离. 主要用于创建大于默认主题的箭头. 默认值: 16
minWidth
	integer 	设置tooltip的最小宽度.默认值: 0 (auto width)
multiple
	boolean 	允许你把几个提示在一个单一的元素 (详见 multiple 部分). 默认值: false
plugins
	string[] 	设置使用Tooltipster的插件名. 默认值: ['sideTip']
repositionOnScroll
	boolean 	为了使tooltip尽可能长时间可见,重新定位tooltip如果它在用户滚动页面时退出视窗. 默认值: false
restoration
	'none',
'previous',
'current' 	指定在调用“销毁”方法后，是否应该在HTML元素上恢复title属性.这个属性可以省略,或是在Tooltipster之前初始化存在的值恢复，或是与字符串化值的当前内容恢复.注意：在多个工具提示的情况下在一个单一的元素，只有最后的破坏可能会触发恢复提示. 默认值: 'none'
selfDestruction
	boolean 	在这个原点从DOM移除后，设置这个参数是否将tooltip自毁.这可以防止内存泄露. 默认值: true
side
	string,
string[] 	设置tooltip在哪侧显示. 这个值可能是一个: 'top', 'bottom', 'left', 'right'. 也可以是一个数组包括多个值. 当使用数组时,这些值的顺序要考虑到回退顺序和禁用没有用到的一侧 (see the sides section). 默认值: ['top', 'bottom', 'right', 'left']
timer
	integer 	设置这个工具提醒在关闭前的显示时间(以毫秒为单位) 默认值: 0 (disabled)
theme
	string,
string[] 	设置一个将覆盖默认工具提示外观的主题. 你可以提供多个字符串的数组来同时应用多个主题Y(详见 主题部分). 默认值: empty array
trackerInterval
	integer 	设置追踪程序持续时间/毫秒(见trackOrigin 和 trackTooltip).当工具提醒被打开,即使trackOrigin和trackTooltip设置为false,追踪器运行会检查起点是否被移除,如非必要,你定的值不能太高或太低. 默认值: 500
trackOrigin
	boolean 	如果原点移动或调整大小需要复位提醒.由于此选项可能对性能有影响，我们建议您仅在需要时启用它. 默认值: false
trackTooltip
	boolean 	如果tooltip改变大小则重新配置tooltip.当尺寸受到'content'这个方法而改变尺寸，tooltip已经重新定位而不需要这个参数。由于此选项可能对性能有影响，我们建议您仅在需要时启用它。详情进入这个入口 有常见问题解答 默认值: false
trigger
	'hover',
'click',
'custom' 	设置这个触发条件，有'click','hover',还可以自定义以达到你想要的效果. 见 触发器部分 来学习如何使用自定义触发器. 默认值: 'hover'
triggerClose
	object 	当你把'trigger'设置为'custom',所有内置关闭触发器都默认不可用，此参数就是允许您激活您所选择的触发器来创建一个定制的行为，只在设置'trigger'为'custom'时有效。 详见触发器部分.
triggerOpen
	object 	类似于'triggerClose'(同上).
updateAnimation
	'fade',
'rotate',
'scale',
null 	用于打开tooltip后的后续动画设置，你可以创建自己的动画在您的CSS文件内但是要将值设为'null'. 默认值: 'rotate'
viewportAware
	boolean 	尝试将tooltip放置在屏幕打开时完全可见的地方,如果工具提示在其源于屏幕之外（使用方法调用）打开时，您可能希望将此选项设置为false。默认值: true
zIndex
	integer 	设置tooltip的z-index默认值: 9999999
```
