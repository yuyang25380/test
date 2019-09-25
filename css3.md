## 一、CSS3简介
+ CSS3是CSS2的“进化”版本，在CSS2基础上，增强或新增了许多特性， 弥补了CSS2的众多不足之处，使得Web开发变得更为高效和便捷。
    + 传统网站和互联网网站的区别？
        1.  没动画   //gif图   flash
        2.  兼容移动端 //响应式     专门针对移动端开发
        3.  传统网站过多的使用小icon图片，现在网站更多的使用图形库。比如font-awesome，本身css2对样式的控制能力有限。
        4.  flash  ===》  视频或者动效都用flash实现。
    + Css新增
        1.  css3 能很容易的实现动画效果
        2.	Css3支持设备类型识别，所以可以根据设备类型做样式适配
        3.	Css3出现的时候，也出现了很多矢量图的字库，这些可以代替以前的小的icon图标，而且更灵活，速度更快。比如购物车按钮、搜索按钮、退出按钮等。。。
        4.	运用h5+css3的页面，基本不需要flash（音视频可以用h5，动画效果可以用css3）

## 1.1	CSS3的现状
1.	浏览器支持程度差，部分属性需要添加私有前缀
    见附件
2. 移动端支持优于PC端  （移动端每年都会更新新款，移动端的浏览器厂商提供的一般都是最新标准）
3.  不断改进中 （现在问题基本都出在IE8,工作中看工作需求是否需要兼容 IE8）
	IE8（要不要兼容）  chrome  firefox   qq(一般是遵循标准的)  360（兼容模式，具备两种内核）safar sougou
	如果真的需要兼容IE8   把需要降级处理的给降级处理。比如动画效果，比如圆角效果
4. 应用相对广泛  所有的手机端，尤其是微信分析的小场景小广告等都是（除了直接用视频）css3
``` 
-webkit-border-radius  radius 半径
 border-top-left-radius:10px;
border-top-right-radius:10px;
border-bottom-right-radius:10px;
border-bottom-left-radius:10px;
```

## 二、	基础知识
+ 2.1	选择器 
     CSS3新增了许多灵活查找元素的方法，极大的提高了查找元素的效率和精准度。CSS3选择器与jQuery中所提供的绝大部分选择器兼容。
+ 2.1.1	属性选择器
    其特点是通过属性来选择元素，具体有以下5种形式：
 ```
    div[attr]
div[attr=mydemo]
  div[attr*=mydemo]   //任意位置
div[attr^=mydemo]  //开始位置
div[attr$=demos]  //结束位置

 ```
 + 2.1.2	伪类选择器
    除了以前学过的:link、:active、:visited、:hover，CSS3又新增了其它的伪类选择器。
1. 结构伪类。    
```
重点通过E来确定元素的父元素。
E:first-child第一个子元素
E:last-child最后一个子元素
E:nth-child(n) 第n个子元素
E:nth-last-child(n) 同E:nth-child(n) 相似，只是倒着计算；
  	n是支持简单表达式的
     li:nth-child(2n-1){
       color: red;
   }
	n<0时无效
  选中所有的4 的倍数的li 
li:nth-child(4n){
      color: red;
    }
   选中前面五个
   li:nth-child(-1n+5){
       color: red;
   }
   选中后面五个
   li:nth-last-child(-1n+5){
	 color: red;
   }
   所有的偶数
   li:nth-child(even){
      color:red
   }
   所有的奇数
   li:nth-child(odd){
      color:blue;
   }
n可是多种形式：nth-child(2n)、nth-child(2n+1)、nth-child(-1n+5)等；
E:empty 选中没有任何子节点的E元素；注意，无法选择有空格或者回撤的标签

```
2. 目标伪类
```
E:target 结合锚点进行使用，处于当前锚点的元素会被选中；
<a href="#li3">点我</a>
<li id="li3">li3</li>
li:target{
		font-size: 30px;
		color: blue;
}

```

+ 2.1.3	伪元素（伪标签）选择器
    + E::before、E::after
    + 是一个行内元素，需要转换成块元素
    + E:after、E:before 在旧版本里是伪类，在新版本里是伪元素，新版本下E:after、E:before会被自动识别为E::after、E::before，按伪元 素来对待，这样做的目的是用来做兼容处理。
    + .clear::after{content:'';display:block;clear:both;height:0;overflow:hidden;visibility:hidden;} .clear{zoom:1;}
    + 注意： 伪标签 在js中不能被选中
    + E::first-letter文本的第一个字母或字；
    + 案例：首字下沉
    + E::first-line 文本第一行；  文本第一行高亮..
    + E::selection 可改变选中文本的样式；
+ 关于before和after
    - CSS2中 E:before或者E:after，是属于伪类的，并且没有伪元素的概念
    - CSS3中 提出伪元素的概念 E::before和E::after，并且归属到了伪元素当中，伪类里就不再存在E:before或者   E:after伪类;
    - After和before是在标签内容后面和前面添加内容，但是一般不存在通过css添加内容的情况，所以一般写成content’’，添加背景图片 做小特效。
+ 2.2	颜色
    - 一种新的颜色的表示方式
    -  rgba(255,0,0,0.1)
    - 新增了RGBA、HSLA模式，其中的A 表示透明度通道，即可以设置颜色值的透明度，相较opacity，它们不具有继承性，即不会影响子元素的透明度。
    - Red、Green、Blue、Alpha即RGBA
    - Hue、Saturation、Lightness、Alpha即HSLA
    - R、G、B 取值范围0~255
    - H 色调 取值范围0~360，0/360表示红色、120表示绿色、240表示蓝色
    - S 饱和度 取值范围0%~100%
    - L 亮度 取值范围0%~100%
    - A 透明度 取值范围0~1
    + 关于透明度：
    1. opacity只能针对整个盒子设置透明度，子盒子及内容会继承父盒子的透明度；
    2. transparent 不可调节透明度，始终完全透明
    + 什么时候用，搞清楚
	    - 一般元素透明用opacity
	    - 遮罩层rgba背景透明	
        - 制作三角的时候用transparent
+ 2.3	文本 (shadow阴影)
    - text-shadow，可分别设置偏移量、模糊度、颜色（可设透明度）。
    - 1、水平偏移量 正值向右 负值向左；
    - 2、垂直偏移量 正值向下 负值向上；
    - 3、模糊度是不能为负值；
    - 可以有多个影子，用逗号隔开
```
案例1：浮雕文字.
	bgc gray
.tu{
	     text-shadow: -1px -1px 1px #fff, 1px 1px 1px #000;
}
.ao{
	text-shadow: -1px -1px 1px #000, 1px 1px 1px #fff;
}

```
+ 2.4阴影 (box-shadow)
    `box-shadow: h-shadow v-shadow blur spread color inset;`
    - blur： 模糊半径
    - spread:  扩展范围
    - color: 颜色







