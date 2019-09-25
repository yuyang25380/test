### `<h1>~<h6>` 标题标签
### `<p></p>` 段落标签
### `<br>`换行标签
### `<hr>`水平线换行标签
iframe内联框架标签，画中画
  -src 内容的链接 比如src="http://www.baidu.com"
  -width/height iframe的宽和高
  -frameborder="0" 去掉默认边框
### `<a>` 超链接标签
  -href 跳转的地址
  -target:_self 默认 当前页面跳转
  -target:_blank 新的窗口打开
  -target:_parent / _top 配合内联框架使用。在父类窗口/顶级窗口跳转页面
### `<img>`
  - src 图片资源的路径
  - alt 如果图片资源不存在 则显示alt的内容 不是必须的
  - 图片的格式:  jpg/ png / gif(动图) / webp(google),使用的时候大小尽量合适的图片
+ 相对路径，基于当前的文件
	- 如果是同一级文件，直接引用
	- 如果是同级文件夹的下一集文件，则直接访问同级文件夹再访问下级，例如： img/dog.jpeg
	- 上一级文件使用../
	- 多层上一级可以使用../../ 指上一级的上一级
+绝对路径
  -本地路径： 比如：E:\web\img
  -网络路径:  比如：`https://pics6.baidu.com/feed/8c1001e93901213fab74e7b82c3660d42e2e9561.jpeg?token=be0557e2565a5fc0ac9253b9d7b773aa&s=F1F78B74062132A01F005D450300E0EA`
+一般采用相对路径。

### html基本规范（xhml语法规范）
+ html不区分大小写，但是尽量使用小写
+ html的注释不能嵌套（注释是给代码加说明的，不能在页面中显示）  语法：<!-- 注释的部分 -->
+ html的标签必须完整, 比如：<p> </p> <p> <p> </p>,明显不是成对的即使浏览器能够解析，但是是错误的！
+ html的标签是可以嵌套的，
+ 标签的属性必须加双引号，

### 字体标签
+ `<em>` 斜体，少用
+ `<strong> `加粗，表示强调
+ `<i> <b>` 单纯的表示斜体和加粗，没用语义化
+ sup 下标 比如：5<sup>2</sup>
+ sub 上标 比如：H<sub>2</sub>O

### 列表
+ 无序列表 ul li
  - 一般使用无序列表
  -前面的小黑点或者1，2，3都需要去掉，自己实现样式，方便控制。
  - list-style:nome;
  -列表可以相互嵌套
+ 有序列表 ol li
+ 自定义列表 dl dt dd

### 表单
+ `<form>` 用于包括输入框，提交数据
  - action 提交的地址，暂时不用理解
  - method 提交数据的方法 get/post，如果不写，默认是get方式
+ `<input>` 表单输入框，根据type的类型，表现形式不同
 - tyep：text 单行文本输入框
 - name: 当前表单的名称 目前必须要有，因为提交的时候后台程序需要通过name属性获取表单的内容
 - value：xx 当前表单的内容，value是提交的结果，如果设置了value,则是当前表单的默认值
+ `<input>`：type:password 密码单选框
+ `<input>`：type:radio 单选
 - name 必须要有，这里表明当前的单选输入框为一组
 - value 系需要有，因为单选按钮提交的值是value的值, value一般采用数字编码的形式表示
+ `<input>`：type:checkbox 多选
 - name 同radio
 - value 同radio
 - checked 默认选中
+ select  > option 下拉框
 - name 属性需要设置
 - value 每个option都要设置value
 - seleceted 默认选中
+ `<input>`：type:file 上传
 - 当选中的时候，实际文件没有被上传上来
 - multiple 可以实现多选
+ texttarea 多行文本输入框
 - cols/rows 文本框的宽度和高度
 - name值需要设置，value指的是标签的内部内容
+ `<input>`：type:submit 提交按钮
 + value 按钮显示的内容
 - 点击后表单被提交到 form.action 配置的地址
 - `<label>` 用于包括输入框的头部和输入框，使之成为一体。用于单选和多选
 + readonly 只读属性输入框内容不能更改
 - disabled 禁用 表单的值在提交时会被舍弃
 + `<fieldset> <legend> `可以实现表单的分组
+ get提交
 - 参数被提交到地址提交，比如：/E:/abc?username=张三&psd=123&like=footbal
 - 不安全
 - 地址栏拼接的参数有长度限制,一般是<4k
 - 一般用于获取数据
 + post提交
  - 地址栏不显示提交内容，在请求体显示
  - 相对安全
  - 提交的数据量没有上线
  - 一般用于提交保存数据

### 转义字符
+ 空格 `&nbsp; &#160;`
+ < 大于号 `&lt; &#60;`
+ > 小于号 `&gt; &#62;`

### table 数据表格
+ table
 - align(表格的位置): left| center| right
 - border="1" 边框，同时为td生成边框
 - cellspacing：10 单元格之间的的间距
 - cellpadding：20 指单元格内文字与边框的距离
 - bgcolor: 设置表格背景颜色
+ tr
 - bgcolor: 当前行的背景颜色
 - align：left | center | right 文字对齐方式
+ th
+ td
 - colspan：表格所占据的列
 - rowspan：表格所占的行

 ##  css
 > css全称层叠样式表(Cascading Style Sheets),用于实现页面的样式.

 ### 书写样式
 +  行内样式   `<p style="color:red;" >我是一个p标签</p>`
 +  内部样式   `<style>  p{color:red;}</style>`
 +  引入样式   `<link rel="stylesheet" href="style.css">`
 +  区别
    - 行内样式 严重耦合 用的非常少
    - 内部样式 测试使用 但是当前页面的样式只能当前页面使用
    - 引入样式 上线时使用. 可以多个页面复用外部样式.

### css选择器
+ 简单选择器
    - 标签选择器
    - id选择器 
    - class选择器
  
  ```
  /* 标签选择器 */
        p{
            color：red；
        }
        /* id选择器 */
		#h3{
			color: orange;
		}
        /* class选择器 */
        .header{
            color:blue;
        }
  ```
+ 复杂选择器
    - 交集选择器
    - 并集选择器
    - 后代选择器
    - 通配符
```
/*标签p 和.p1的交集*/
p.p1 {
	color: red;
}
.p2.danger {
	color: blue;
}
/*并集选择器 都被选中*/
.p1,
.p2 {
	font-size: 30px;
}
/*后代选择器 空格*/
.p3 a {
	color: red;
}
/** 通配符 选择所有标签*/
* {
	/*background-color: pink;*/
}
```
## CSS 继承性

[css 中可以和不可以继承的属性总结](https://www.cnblogs.com/thislbq/p/5882105.html)

## CSS 层叠性

样式冲突，必然只有一个样式生效。

## CSS 权重问题

-   行内样式 > id 选择器 > class 选择器 >标签选择器
-   复杂选择器权重计算
    -   行内样式 1000
    -   id 选择器 100
    -   class 选择器 10
    -   标签选择器 1
    -   通配符/继承属性 0
-   如果两个选择器是一样的，遵循就近原则。
-   如果写了相同的选择器，希望某个选择器权重更高，添加 class 类名，使用交集选择器即可。

```css
.header .nav .nav-item {
	color: red;
}
.header .nav .nav-item.active {
	color: blue;
}
```

## CSS 常见单位

-   px 像素单位，用于表示标签的宽和高，或者字体的大小。
-   百分比，通常用来表示长度或高度，相较于父类元素的百分比。
-   em 基于当前字体的倍数。

```css
p {
	text-indent: 2em;
}
```

-   颜色
    -   预定义颜色：blue、yellow、pink、purple、red 等。
    -   十六进制：每两位表示一种颜色的深度，分别表示 red、green、blue，比如：#ff00ff。
    -   rgb: rgb(0,0,255) ==> 绿色。rgb 和十六进制是可以相互转换的。
    -   rgba: rgba(0,0,255,0.5)。跟 rgb 一样，a 是透明度：0~1，0.5==> .5

```shell
十六进制==> 十进制换算
十进制：  0  1  2  3  4  5  6  7  8  9
十六进制：0  1  2  3  4  5  6  7  8  9   a(10)  b(11)   c(12)  d(13)   e(14)   f(15)
比如： 1e  ==>  1*16 + e ==> 16+ 14 = 30;
    ff ==> f * 16 + f ==> 15*16 + 15 = 255;
比如一个颜色是 aabbcc ==> abc, #00ffaa ==> #0fa
```

## CSS 常用属性

| 属性名称         | 属性作用     | 值                                                                                 |
| ---------------- | ------------ | ---------------------------------------------------------------------------------- |
| width / height   | 宽高         | px 百分比 em 等                                                                    |
| background-color | 背景颜色     | color                                                                              |
| cololr           | 字体颜色     | color                                                                              |
| font-size        | 字体大小     | px em 等                                                                           |
| text-align       | 文字对齐方式 | center left right                                                                  |
| text-indent      | 首行缩进     | px em 等                                                                           |
| font-family      | 字体         | 微软雅黑 Microsoft YaHei、黑体 SimHei、Arial 等                                    |
| font-weight      | 字体加粗     | 100-900.加粗 700-900/ bolder lighter normal                                        |
| font-style       | 字体样式     | Italic 斜体 / normal 正常                                                          |
| line-height      | 行高         | 单位： px /倍数 / 百分比 ;- 设置文字的行间距- 单行文字垂直居中 ：行高=父类盒子高度 |
| font             | 字体缩写     | `font:italic bolder 20px/1.2 'Arial','Microsoft YaHei' 

## CSS书写规范
开始就形成良好的书写规范，是你专业化的开始。
### 空格规范
+ 【强制】 选择器 与 { 之间必须包含空格。
	- 示例： .selector { }
+ 【强制】 属性名 与之后的 : 之间不允许包含空格， : 与 属性值 之间必须包含空格
	- 示例：
font-size: 12px;
## css选择器规范
+ 【强制】 当一个 rule 包含多个 selector 时，每个选择器声明必须独占一行。
+ 示例：
```
/* good */
.post,
.page,
.comment {
line-height: 1.5;
}
/* bad */
.post, .page, .comment {
line-height: 1.5;
}
```
+ 【建议】 选择器的嵌套层级应不大于 3 级，位置靠后的限定条件应尽可能精确。
+ 示例：
```
/* good */
#username input {}
.comment .avatar {}
/* bad */
.page .header .login #username input {}
.comment div * {}
```

## 属性规范
+ 【强制】 属性定义必须另起一行
+ 
示例：
```
/* good */
.selector {
margin: 0;
padding: 0;
}
/* bad */
.selector { margin: 0; padding: 0; }
```
+ 【强制】 属性定义后必须以分号结尾。
+ 示例：
```
/* good */
.selector {
margin: 0;
}
/* bad */
.selector {
margin: 0
}
```

## 标签的表现形式

-   块状标签：独占一行，宽高有效。比如：`div` `p` `h1~h6` `form` `table` `hr` `br` `ul>li` `ol>li` `dl>dt/dd`
-   行内块标签：可以同一行显示，宽高有效。比如: `input` `select` `img` `button`
-   行内标签：可以同一行显示，但是宽高无效。比如：`a` `span` `strong` `del` `ins` `em` `i` `b`
-   `display:` 修改元素的性质。
    -   block：设置元素为块元素
    -   inline：设置元素为行内元素
    -   inline-block：设置元素为行内块元素
    -   转换的必要性：比如可以把`a`标签转换为块状元素，设置宽高，使用户可点击的区域增大，进而实现一个按钮的样式。

## 背景图片属性

| 属性名称              | 属性作用           | 值                                                          |
| --------------------- | ------------------ | ----------------------------------------------------------- |
| background-color      | 背景图片颜色       | color                                                       |
| background-image      | 背景图片           | url(‘1.png’);                                               |
| background-repeat     | 平铺方式           | repeat 、 no-repeat 、 repeat-x 、 repeat-y                 |
| background-position   | 图片位置           | left、 right、 top、 bottom、 center                        |
| background-attachment | 背景滚动           | scroll、fixed (注意：基于 body 的定位）                     |
| background            | 简写（顺序不能错） | background: green url(1.jpg) no-repeat center center fixed; |

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<title>Document</title>
		<style>
			body {
				background-image: url("img/banner.jpg");
				background-repeat: no-repeat;
				background-position: left top;
				/*是否跟最滚动*/
				background-attachment: fixed;
			}
			.d1 {
				width: 100%;
				height: 400px;
				/*background-color: green;*/
				/*background-image: url('img/bf.png');*/
				/*background-repeat: no-repeat;*/
				/*center 默认的是x轴  y轴默认居中*/
				/*跟数学的坐标系是不同的，x轴为正 ，y轴向下正 */
				/*background-position: -35px 30%;*/
				background: green url("img/bf.png") no-repeat right 200px fixed;
				/*如果设置了fixed 那么背景图片的位置将会基于body*/
				/*background-attachment:fixed;*/
				/*精灵图片 雪碧图 做案例的时候再补充*/
				background-color: purple;
			}
			.d2 {
				widows: 100%;
				height: 1000px;
				background-color: pink;
				/*透明度 ： 0~1  */
				opacity: 0.5;
			}
		</style>
	</head>
	<body>
		<!-- div 是一个标签，不表示任何的内容，没有自带样式。只是用于划分结构 -->
		<div class="d1"></div>
		<div class="d2"></div>
	</body>
</html>
```

## 盒子模型

> CSS 处理网页时，它认为每个元素都包含在一个不可见的盒子里。包含内容区域、padding（内边距）、border（边框）、margin（盒子与盒子的距离）。

> 所有的页面的元素都可以看成是一个盒子，占据一定的页面空间。

![](/media/hezi.jpg)

### padding

-   `padding:10px 20px 30px 40px;` 这样会设置元素的上、右、下、左四个方向的内边距。
-   `padding:10px 20px 30px;` 分别指定上、左右、下四个方向的内边距。
-   `padding:10px 20px;` 分别指定上下、左右四个方向的内边距。
-   `padding:10px;` 同时指定上左右下四个方向的内边距。
-   同时在 css 中还提供了 `padding-top`、`padding-left`、`padding-right`、`padding-bottom` 分别用来指定四个方向的内边距。
-   改变元素的大小。

```html
<style>
	.d1 {
		width: 300px;
		height: 300px;
		background-color: green;
		/*padding: 50px  100px 30px 80px;
			padding-left: 100px;*/
		padding: 100px;
	}
</style>
```

### margin

-   设置方法和`padding`类似，同样也提供了四个方向的 `margin-top/margin-right/margin-bottom/margin-left`。
-   `margin: xxx auto;`可以使块状元素水平居中。
-   `嵌套崩塌`：两个盒子发生嵌套的时候，给子类设置 margin 会给父类造成一种崩塌现象，子类元素的 margin-top 没有效果，而是直接作用到父类元素。

```
解决方案：
1. 父类 overflow: hidden;
2. 父类 设置极小的 padding 或者 border；
```

-   `margin重叠`： 如果垂直方向上两个块状元素同时设置了 margin-bottom 和 margin-top，那么这两个值将会发生重叠，不会累加，哪个值大用哪个。
-   margin-top/margin-bottom 对于行内元素无效。

```html
<style>
	.d2 {
		width: 200px;
		height: 200px;
		background-color: red;
		/*margin: 100px;
		margin-top: 200px;*/
		/*d2将会左右居中*/
		margin: 100px auto;
	}
</style>
<!-- ======================= -->
<!-- 当两个盒子发生嵌套的时候，给子类设置maring会给父类造成一种崩塌现象，子类的margin-top没有效果，而直接作用到父类 -->
<!-- 解决方案： 1. 父类  overflow: hidden
			   2. 父类 设置极小的padding -->
<div class="box">
	<div class="inner-box"></div>
</div>

<hr />

<!-- 如果垂直两个块状元素同时设置了margin-bottom和margin-top,那么这两个值将会发生重叠,不会累加，哪个值大用哪个 -->
<div class="box2"></div>
<div class="box3"></div>
```

### border

-   可以在元素周围创建边框，边框是元素可见框的最外部。
-   `border:1px solid red;` 分别指定了边框的宽度、颜色和样式，是一种缩写：`border-width border-style border-color`。
-   `border-style:` `none (默认) / dashed(虚线) / dotted（点） / solid(实线) / double(双实线)`。
-   可以单独设置某一条边框：`border-right: 20px solid blue;`
-   改变元素的大小。

```html
<style>
	.d1 {
		width: 200px;
		height: 200px;
		background-color: green;
		/*简写属性*/
		/*border: 10px solid red;*/
		border-width: 10px;
		border-style: solid;
		border-color: red;
		/*右边单独添加20像素*/
		border-right: 20px solid blue;
	}
</style>
```

+ 影响盒子大小的因素
    - border
    - padding  特殊: 继承的盒子在父内元素宽度范围内,padding的值不会影响该盒子的大小
+ display 我们可以通过修改display的值来修改元素的性质
    - block 设置元素为块元素
    - inline 设置元素为行内元素
    - inline-block: 设置元素为行内块元素
    - none: 隐藏元素
    - 转换的必要性: 比如可以把a标签转换为块状元素,进而实现一个按钮的样式.

## 显示和隐藏

-   `display:none;` 隐藏元素，不再在文档中占据位置。
    -   显示：可以将 display 设置为其他属性值，不为 none 即可。
-   `visibility:hidden;` 隐藏元素，隐藏后其在文档中所占的位置会依然保持，不会被其他元素覆盖。

```html
<style>
	.baidu {
		/*display 可以改变元素的表现形式*/
		display: inline-block;
		width: 300px;
		height: 300px;
		background-color: pink;
	}
	.p1 {
		/*display:none;*/
		visibility: hidden;
	}
</style>
```

## overflow

`overflow` 指定标签里面的内容超出了样式的宽度和高度时如何处理。

-   visible：默认值
-   scroll：添加滚动条
-   auto：根据需要添加滚动条
-   hidden：隐藏超出盒子的内容

```html
<style>
	.d1 {
		width: 200px;
		height: 200px;
		background-color: green;
		overflow: auto;
		/*overflow: scroll;
			overflow: hidden;*/
	}
</style>
```

## 文档流

-   块状元素独占一行
-   行内元素可以同一行显示，自左向右，如果不够会自动换行
-   自上而下的展示
-   脱离文档流：浮动和定位

## 浮动

> 浮动指的是使元素脱离原来的文本流，在父元素中浮动起来。

-   浮动使用 float 属性。
-   可选值：
    -   none：不浮动
    -   left：向左浮动
    -   right：向右浮动

### 浮动的表现形式

-   当一个元素浮动以后，其下方的元素会上移。元素中的内容将会围绕在元素的周围。
-   浮动会使元素完全脱离文本流，也就是不再在文档中在占用位置。
-   元素设置浮动以后，会一直向上漂浮直到遇到父元素的边界或者其他浮动元素。
-   元素浮动以后即完全脱离文档流，这时不会再影响父元素的高度。也就是浮动元素不会撑开父元素。
-   浮动元素默认会变为块元素，即使设置 display:inline 以后其依然是个块元素。
-   块级元素和行内元素都可以浮动，当一个行内元素浮动以后将会自动变为一个块级元素。
-   当一个块级元素浮动以后，宽度会默认被内容撑开，所以当漂浮一个块级元素时我们都会为其指定一个宽度。

### 浮动的影响

如果子类元素设置了浮动，而父类元素没有设置高度，或者高度比子类元素小，那么子类元素脱离了文档流，就无法把父类盒子撑开。那么整个文档的结构将受到破坏。

-   清除浮动的影响：
    -   严格计算父类盒子高度
    -   clear: left/right/both 不允许当前元素的 left/right/both 有浮动元素。
        -   在浮动元素的最后面追加一个空的 div,设置 clear:both 即可清除浮动的影响。
-   因为浮动会对文档流造成影响，所以能用流式布局就不要使用浮动。

```
补充：
1.display：inline-block 标签的换行符会被显示为空格。
2.float:right 会改变标签的前后顺序。
```

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<title>Document</title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}
			.header {
				width: 100%;
				height: 100px;
				background-color: green;
			}
			.content {
				width: 100%;
				/*height: 500px;*/
				background-color: pink;
			}
			/*同级要浮动，都浮动*/
			.content .aside {
				float: left;
				width: 200px;
				height: 300px;
				background-color: red;
			}
			.content .main {
				float: left;
				width: 800px;
				height: 900px;
				background-color: gray;
			}
			.footer {
				width: 100%;
				height: 100px;
				background-color: black;
			}
			/*不允许当前元素左右出现浮动元素  这样可以清除浮动的影响*/
			.clr {
				clear: both;
			}
		</style>
	</head>
	<body>
		<div class="header"></div>
		<div class="content">
			<div class="aside"></div>
			<div class="main"></div>
			<div class="clr"></div>
		</div>
		<div class="footer"></div>
	</body>
</html>
```

## 定位

> 通过 `position` 属性可以实现元素的定位。元素定位之后，需要通过设置 left/right 和 top/bottom 值对元素定位。

-   position 属性可以把一个元素放置到网页中的任何位置。
-   可选值：

    -   static（默认）
    -   relative
    -   absolute
    -   fixed
    -   sticky

### `relative` 相对定位

相对元素本身的位置定位。

-   每个元素在页面的文档流中都有一个自然位置。相对于这个位置对元素进行移动就称为相对定位。周围的元素完全不受此影响。
-   当开启了相对定位以后，可以使用 top、right、bottom、left 四个属性对元素进行定位。
-   如果不设置元素的偏移量，元素位置不会发生改变。
-   相对定位不会使元素脱离文本流。元素在文本流中的位置不会改变。
-   相对定位不会改变元素原来的特性。
-   相对定位会使元素的层级提升，使元素可以覆盖文本流中的元素。

```css
.d1 {
	position: relative;
	left: 100px;
	top: 100px;
	width: 200px;
	height: 200px;
	background-color: green;
}
```

### `absolute` 绝对定位

指使元素相对于`视口`或离他最近的祖先定位元素进行定位。

-   当开启了绝对定位以后，可以使用 top、right、bottom、left 四个属性对元素进行定位。
-   绝对定位会使元素完全脱离文本流。
-   绝对定位的块元素的宽度会被其内容撑开。
-   绝对定位会使行内元素变成块元素。
-   一般使用绝对定位时会同时为其父元素指定一个相对定位，以确保元素可以相对于父元素进行定位。

```css
.d1 {
	/*有绝对的事情吗？绝对的值必须有参照物*/ /*如何才能既保证父类有定位元素 而且父类不会再原来的位置偏移*/ /*子绝父相*/
	position: relative;
	left: 0;
	top: 0; /* left: 100px; top: 100px;*/
	margin-left: 100px;
	width: 400px;
	height: 400px;
	background-color: green;
}
.d11 {
	position: absolute;
	left: 100px;
	top: 100px;
	width: 150px;
	height: 150px;
	background-color: red;
}

/* 结构 */
/* <div class="d1">
	<div class="d11"></div>
</div> */
```

### fixed 固定定位

元素会被锁定在屏幕的某个位置上，当访问者滚动网页时，固定元素会在屏幕上保持不动。 (相对于视口定位)

-   固定定位不占据原来的位置，会脱离文档流。
-   给元素设置固定定位之后，元素位置从浏览器左上角出发。 - 可以将行内元素转换块元素。

```css
.zx {
	position: fixed;
	right: 100px;
	bottom: 200px;
	width: 200px;
	height: 200px;
	background-color: red;
}

/* <a class="zx" href="#">
	w shi a
</a> */
```

### sticky 粘性定位

粘性定位可以被认为是相对定位和固定定位的混合。元素在跨越特定阈值前为相对定位，之后为固定定位。

```css
#one {
	position: sticky;
	top: 10px;
}
```

在网页滚动到元素 top 距离小于 10px 之前，元素为相对定位。之后，元素将固定在与顶部距离 10px 的位置，直到 网页回滚到阈值以下。

### z-index

-   当元素开启定位以后就可以设置 z-index 这个属性。默认是 0。
-   z-index 可以指定一个整数作为参数，值越大元素显示的优先级越高，也就是 z-index 值较大的元素会显示在网页的最上层。

```css
.d1,
.d2,
.d3 {
	position: fixed;
	left: 0;
	top: 0px;
	width: 200px;
	height: 200px;
	background-color: green;
}
.d1 {
	z-index: 9;
}
.d2 {
	left: 30px;
	top: 30px;
	background-color: blue;
	z-index: 2;
}
.d3 {
	left: 80px;
	top: 80px;
	background-color: red;
	z-index: 0;
}

/* <div class="d1">
	d1
</div>
<div class="d2">
	d2
</div>
<div class="d3">
	d3
</div> */
```

## 规避脱标流

> 经验： 一般布局采用标准流，如果标准流布局实现不了用浮动。定位一般用于解决小范围的某个标签的位置。

-   能用标准流（没有脱标）解决就不用浮动
-   解决不了就考虑有浮动（页面布局类型，“不完全脱标”）
-   浮动解决不了用定位（小图标，完全脱标，不影响内容）

## 结束

> html 和 css 基础内容基本概况完毕，当然只掌握这些内容是不够的。只要跟着老师的教程走，耐心学，三四个案例下来就可以完全掌握页面基础知识。期间对于类命名，组织规则及实现技巧，都会一一说到。





  
