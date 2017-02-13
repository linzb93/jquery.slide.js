# slide.js

##简介
slide.js是一个Web端基于jquery的轻量轮播插件，可实现web端的单页滚动、多页滚动、焦点轮播和无缝滚动等效果。

Demo:https://linzb93.github.io/demo/jquery.slide/



## 最近更新

V3.0 (2016年12月10日)



## 兼容性

兼容IE7及以上的浏览器。



##使用方法

###引入文件

- jQuery.js(1.8.0+)
- jquery.slide.css
- jquery.slide.js

```html
<link rel="stylesheet" type="text/css" href="jquery.slide.css">
...
<script type="text/javascript" src="jquery-1.8.0.min.js"></script>
<script type="text/javascript" src="jquery.slide.js"></script>
```

###HTML结构
```html
<div class="slide">
	<div class="slide-wrapper">
		<ul>
			<li>Slide 1</li>
			<li>Slide 2</li>
			<li>Slide 3</li>
			<li>Slide 4</li>
			<li>Slide 5</li>
			<li>Slide 6</li>
			<li>Slide 7</li>
		</ul>
	</div>
	<a href="javascript:;" title="" class="prev"><</a>
	<a href="javascript:;" title="" class="next">></a>
	<div class="page"></div>
</div>
```

###JavaScript
```javascript
//配置参数
var mySlide = $('.slide').slide({
	speed: 500,
	prev: '.prev',
	next: '.next',
  	autoplay: 3000,
	pagination: '.page'
});

//使用轮播的方法
$('.btn').on('click', function() {
  mySlide.stop();
});
```



## API

### 配置参数

| 参数               | 类型              | 默认值              | 含义                    | 备注                                       |
| ---------------- | --------------- | ---------------- | --------------------- | ---------------------------------------- |
| wrapper          | String          | '.slide-wrapper' | 轮播列表的父元素              | selector                                 |
| dir              | String          | 'h'              | 滚动方向                  | ‘h’: 水平方向；'v':竖直方向                       |
| speed            | Number          | 500              | 滚动速度                  | 单位ms                                     |
| prev             | String          | ''               | 前翻页按钮                 | selector                                 |
| next             | String          | ''               | 后翻页按钮                 | selector                                 |
| effect           | String          | 'fade'           | 轮播模式                  | 'fade': 焦点；'slide': 单页；'carousel':多页； 'marquee':无缝；'return': 来回滚动 |
| perGroup         | Number          | 1                | 显示数量                  |                                          |
| slidePerView     | Number          | 1                | 每次滚动的数量               |                                          |
| autoPlay         | Number          | 0                | 轮播时间间隔                | 大于0时有效，建议大于speed值。                       |
| pagination       | String / Object | 往下看              | 分页器                   | 值为String类型时，表示收到的是selector。              |
| selector         | String          | ''               | 分页器的选择器               | pagination的对象属性开始                        |
| type             | String          | 'dot'            | 分页器的类型                | ‘dot’: 点；‘num’:数字；'image': 图片；'progress':进度条；'outer': 页面上已有元素 |
| event            | String          | 'click'          | 分页器切换事件               | 'click':点击；'mouseover/mousemove/hover/mouseenter':悬浮；‘’:无事件绑定。pagination的对象属性结束 |
| lazyload         | Boolean         | false            | 图片懒加载                 | 值为false表示不使用懒加载。如果图片地址在img标签里，请用data-src存放地址；如果是作为background,请用data-bg存放地址。 |
| enableShowWidget | Boolean         | false            | 鼠标悬停在轮播上方显示控件，移出时隐藏控件 |                                          |
| css3             | Boolean         | false            | 是否使用css3动画执行轮播        | 默认不使用                                    |
| easing           | String          | 'swing'          | 轮播速度曲线                | 如果需要改动这个参数建议引入jquery.easing.js。如果你想使用无缝滚动效果，easing的值建议设置成'linear'。 |
| beforeCreate     | function        | $.noop           | 创建轮播前执行的函数            |                                          |
| created          | function        | $.noop           | 创建轮播后执行的函数            |                                          |
| beforeSlide      | function        | $.noop           | 执行轮播前触发的函数            | 支持传入参数，第一个参数表示当前轮播页的index，第二个参数表示当前轮播页。  |
| slided           | function        | $.noop           | 执行轮播后触发的函数            | 同上。                                      |

### 方法

| 名称                | 功能                            |
| ----------------- | ----------------------------- |
| stop              | 暂停轮播                          |
| play              | 继续轮播                          |
| destroy           | 销毁轮播（包括移除绑定事件）                |
| rebuild           | 重置轮播                          |
| slidePrev         | 向前滚动                          |
| slideNext         | 向后滚动                          |
| slideTo(number)   | 滚动到指定位置                       |
| setOption(object) | 改变配置参数。eg: set({speed: 1000}) |



## 更新日志

[CHANGELOG.md](https://github.com/linzb93/slide/blob/master/doc/CHANGELOG.md)



## License

MIT licensed

Copyright (C) 2017 linzb93
