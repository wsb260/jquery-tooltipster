# jquery-tooltipster
jQuery插件tootip提示框,可配置,可选择样式

#简单样例

1.引入文件
```javascript
<head>
    <link rel="stylesheet" type="text/css" href="tooltipster/dist/css/tooltipster.bundle.min.css" />

    <script type="text/javascript" src="http://code.jquery.com/jquery-1.10.0.min.js"></script>
    <script type="text/javascript" src="tooltipster/dist/js/tooltipster.bundle.min.js"></script>
</head>
'''

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
