

#  超链接技巧

```html
<base target="_blank">
	页面的所有跳转，在新窗口打开
<a href="#" target="_self">
	默认页面在当前窗口打开
```

# 锚点的使用

```html
设置锚点
<h3 id="md"></h3>
同页面的跳转
<a href="#md">链接到锚点</a>
不同页面的跳转
<a href="xxxxxxxxxxxx.html#md">链接08页面的锚点</a>
```

# 特殊字符

```html
&lt;小于号
&gt;大于号
&nbsp;空格
&yen;￥的标志
&copy;©的标志
<hr />水平线
<br />换行
```

# 图像标签img 属性

```html
<img src="来源" title="鼠标悬停时显示的内容" alt="图片不能显示时替换的文本"
```

# 表单控件

```html
<form action="1.php" name="reg" method="post">
    action收集的信息提交给那个文件处理 
```

```html
<label for="user">昵称: <input type="text" id="user"></label>
```

- label for="input id的值",当点击label里边文字的时候,input获取了光标焦点

```html
用户名: <input type="text" value="孙悟空" name="username" maxlength="6"  />
```

```html
密码: <input type="password" name="pwd" maxlength="6" />
```

```html
单选框： <input type="radio" name="gender" > 
```

```html
多选框：<input type="checkbox">
多选框：<input type="checkbox">

```

```html
下来菜单：
<select>
			    	<!-- 下拉菜单选项 -->
			   		<option>1995</option>
			   		<option selected="selected">1996</option>
			   		<option>1997</option>
</select>
```

```html
上传信息: <input type="file">
```

```html
点击注册的属性<input type="submit" value="立即注册">
```

```html
没有点击的属性<input type="button" value="普通按钮">
```

```html
图片按钮<input type="image" src="images/btn.png">
```

```html
重置按钮<input type="reset">
```

```css
<!-- 邮箱控件 必须包含@-->
		邮箱: <input type="email">
		<br><br>
		<!-- 电话号码控件 语义化-->
		电话: <input type="tel">
		<br><br>
		<!-- 搜索控件 语义化-->
		搜索: <input type="search">
		<br><br>
		<!-- 数字控件 -->
		数字: <input type="number">
		<br><br>
		<!-- 网址控件 输入的内容必须包含http://-->
		网址: <input type="url">
		<br><br>
		<!-- 时分控件 -->
		时间: <input type="time">
		<br><br>
		<!-- 日期控件 -->
		日期: <input type="date">
		<br><br>
		<!-- 周控件 -->
		周: <input type="week">
		<br><br>
		<input type="submit">
```

```css
<form action="1.php">
		<!-- placeholder 占位符 
			autofocus 自动获取光标焦点
			autocomplete  自动完成
			autocomplete="on" 默认值 输入框会记住输入的内容
						="off"  输入框不会记住输入的内容
		    required 必填项 (输入的内容不能为空)

		-->
		<input type="text" placeholder="大傻瓜" autofocus autocomplete="off" required>
		<br><br>
		<input type="submit">
	</form>
```



# 边框的线型

```css
solid  实线； dotted  点线；  dashed  曲线； double 	双线 
```

# 表格边框合并

```css
border-collapse: collapse;
*表格边框合并, 该属性只能用在表格上
```

# 获取光标状态

```css
/*:focus  伪类  获取光标焦点的状态  通常配合input使用*/
		.username input:focus {
			background-color: red;
		}
```

# 外边距塌陷

当上下相邻的两个块元素相遇时，如果上面的元素有下外边距margin-bottom，下面的元素有上外边距margin-top，则他们之间的垂直间距不是margin-bottom与margin-top之和，而是两者中的较大者。这种现象被称为相邻块元素垂直外边距的合并（也称外边距塌陷）。

对于两个嵌套关系的块元素，如果父元素没有上内边距及边框，则父元素的上外边距会与子元素的上外边距发生合并，合并到父元素上,合并后的外边距为两者中的较大者，即使父元素的上外边距为0，也会发生合并。

解决 overflow：hidden。可以为父元素添加overflow:hidden。触发了BFC, 块级格式化上下文, 独立的布局区域,不会受到外部因素的干扰

# 盒子阴影

```css
/*盒子阴影
				第1个值阴影的水平偏移量,正值向右,负值向左
				第2个值阴影的垂直偏移量,正值向下,负值向上
				第3个值阴影的模糊范围
				第4个值是阴影的大小
				第5个值是阴影的颜色
				阴影默认是外阴影
			*/
			/*box-shadow: 20px -10px 20px 2px #666;*/
			/*内阴影 inset*/
			/*box-shadow: inset 0px 0px 120px 2px red;*/
			/*多组阴影之间用逗号隔开*/
			box-shadow: 20px -10px 20px 2px #666, inset 0px 0px 120px 2px red;
```

# 盒子透明度

```css
rgba(255, 255,255, .5);
opacity: .5;
```

# 浮动的特点

```css
/*浮动的特点*/

​            /*1.浮动的元素会脱离标准流的控制,不占据原来的位置

​              2.浮动可以使(块)元素在一行上显示

​              3.浮动只能浮动到父元素的左边和右边,受到父元素内边距的控制

​              4.浮动元素顶对齐, 代码换行没有缝隙

​              5.浮动元素不会影响上边标准流里的块元素,只会影响下边的元素

​              6.浮动元素有了行内块元素的显示特点

​                ◆块元素浮动之后,不会默认父元素的宽度了,默认宽高0, 内容会撑开宽高

​                ◆行内元素浮动之后,可以设置宽高了

​            */
```

# 清除浮动的原因

-   清除浮动是为了解决父元素不能设置高度, 里边的子元素浮动之后不能撑开父元素高度的问题

# 清除浮动的方法

```css
1/*给浮动元素的父元素(亲爹),使用overflow: hidden;清除浮动, 触发了BFC	,块级格式化上下文, 独立的布局区域, 不受到外部因素的干扰
弊端, 子元素出了父元素的范围(边界),多了部分的会被隐藏掉*/
2/*给浮动元素的父元素(亲爹), 调用.clearfix:after 伪元素清除浮动*/
		.clearfix:after {
			content: '';
			display: block;
			height: 0;
			/*显示模式为隐藏*/
			visibility: hidden;
			clear: both;
		}
		/*为了兼容ie6-7清除浮动*/
		.clearfix {
			*zoom: 1;
		}
3/*给浮动元素的父元素(亲爹), 调用clearfix 双伪元素清除浮动*/
		.clearfix:before, .clearfix:after {
			content: '';
			display: table;
		}
		.clearfix:after {
			clear: both;
		}
		.clearfix {
			*zoom: 1;
		}
```

# 伪元素

```css
/*:hover 伪类 ::before 前伪元素, 
			::before 前伪元素是在元素的里边的前边插入伪元素,可以当做行内元素对待
			可写成:before
		*/
		.box:before {
			/*content 为必写属性, 否则伪元素不生效*/
			content: '前伪元素';
			display: block;
			background-color: green;
			color: #fff;
		}
		/*::after 后伪元素, 在在元素的里边的后边插入伪元素,可以当做行内元素对待
			可写成:after  
		*/
		.box:after {
			content: '后伪元素';
			background-color: red;
			color: #fff;
		}
```

# 绝对定位

```css
/*绝对定位
				1.绝对定位的元素脱标了,不占据原来的位置
				2.绝对定位的元素, 所有父元素没有定位,位置偏移基于浏览器
				3.绝对定位的元素,如果父元素有定位,位置偏移基于离他最近的使用了定位的父元素位置偏移
				4.绝对定位的元素有了行内块的显示特点
					◇绝对定位的块元素,不会默认父元素的宽了,默认宽高0, 内容会撑开宽高
					◇绝对定位的行内元素可以设置宽高了

			*/
```

# 绝对定位

```css
/*固定定位
				1.固定定位的元素脱标,不占据原来的位置
				2.固定定位的元素位置偏移基于浏览器可视窗口
				3.固定定位的元素有了行内块元素的显示
				    ◆固定定位的块元素不会默认父元素的宽度了,默认宽高为0,内容会撑开宽高
				    ◆固定定位的行内元素可以设置宽高了
			*/
```

# 定位盒子的居中显示！！！

```css
1.son {
			position: absolute;
			/*向右走父元素宽度的一半*/
			left: 50%;
			/*向左走自身宽度的一半*/
			margin-left: -50px;
			/* left: 0; */
			/*bottom: 0;*/
			/*向下走父元素高度的一半*/
			top: 50%;
			/*向上走自身高度的一半*/
			margin-top: -50px;
			width: 100px;
			height: 100px;
			background-color: #f00;
			/*margin: 0 auto; 只能使标准流里的块元素水平居中*/
			/*margin: 0 auto;*/
		}
2.son {
			/*这种方法,子元素必须设置宽高,被内容撑开的宽高无效*/
			position: absolute;
			left: 0;
			right: 0;
			top: 0;
			bottom: 0;
			margin: auto;
			width: 100px;
			height: 100px;
			background-color: #f00;
		}
3.son {
      width: 600px;
      height: 300px;
      background-color: red;
      position: absolute;
      /* 相对于父亲 宽高 */
      top: 50%;
      left: 50%;
      /* 相对于自身 宽高 */
      transform: translate(-50%, -50%);
    }
```

# 元素显示与隐藏

```css
.red {
			/*隐藏对象,隐藏之后不占位置*/
			/*display: none;*/
			/*对象隐藏, 隐藏之后还占据位置*/
			visibility: hidden;
			background-color: #f00;
		}
```

# 元素移除的处理

```css
/*visible 溢出可见
			  scroll 不管内容是否溢出都生成滚动条
			  auto 内容溢出生成滚动条,不溢出不生成滚动条
			  hidden 溢出隐藏
			*/
			overflow: hidden;
			/*溢出的内容不占位置*/
```

# 鼠标样式

```css
	/*
			  鼠标样式
			  default 默认值 小白
			  pointer 小手
			  move    移动
			  text    文本
			  not-allowed 禁止
			  help  帮助
			 */
			cursor: not-allowed ;
```

# 轮廓线清除

```css
input {
			/*清除轮廓线*/
			outline: 0;
		}
		textarea {
			/*禁止文本域拖拽*/
			resize: none;
		}
```

# 单行文本省略号实现

```css
.box {
			width: 200px;
			height: 300px;
			background-color: #ccc;
			/*文字强制一行显示*/
			white-space: nowrap;
			/*溢出隐藏*/
			overflow: hidden;
			/*溢出省略号*/
			text-overflow: ellipsis;
			/*实现单行文本省略号,white-space: nowrap;overflow: hidden;text-overflow: ellipsis; 缺一不可*/
		}
```

# 清除图片的缝隙

```css
.box img {
			/*清除图片底部的缝隙,只需要将vertical-align的值设置为除了baseline(基线以外的值)都可以, 或者将图片转换为块元素,也能清除图片底部的缝隙
			top 顶对齐
			middle 垂直居中对齐
			bottom 底对齐
			*/
			/*vertical-align: middle;*/
			/* display: block; */

		}
```

# 输入框占位符

```css
input {
			color: red;
		}
		/*占位符选择器,修改占位符的样式*/
		input::placeholder {
			color: yellow;
		}
	  <!-- 占位符, 当输入内容的时候,占位符消失, 删除输入的内容,占位符出现 -->
	<input type="text" placeholder="金装大灰狼">
```

# 背景线型渐变

```css
background-image: linear-gradient(to right, red, green, blue, yellow, orange, pink);
background: linear-gradient(to right, red, green, blue, yellow, orange, pink);


/* 起始方向，颜色1，颜色2，...*/
background: -webkit-linear-gradient(30deg, red, blue);

/* 1.必须有私有前缀*/
/* 2.起始方向：可以为方向名词left 或 deg度数，默认从上到下*/
/* 3.颜色个数：最少2两个颜色*/
```

# 伪类选择器的使用

first-child

**选择父元素的第一个子元素E。** 

last-child

**选择父元素的最后一个子元素E**。

nth-child(n)

**匹配父元素的第n个子元素E，假设该子元素不是E，则选择器无效。** 

nth-last-child(n)

**匹配父元素的倒数第n个子元素E，假设该子元素不是E，则选择器无效。** 

nth-of-type(n)

**匹配同类型中的第n个同级兄弟元素E。** 

该选择器总是能命中父元素的第n个为E的子元素，不论第n个子元素是否为E 

# flex布局（圣杯布局）

```css
display:flex;
flex-direction:row /* 默认值 从左到右 */
flex-direction:column  从上到下
```

```css
justify-content:center  在主轴居中对齐
justify-content:space-around  平分剩余空间
justify-content:space-between  先贴两边 再平分剩余空间
flex-wrap:nowrap;子元素不会换行
flex-wrap：wrap ；会换行
```

```css
子项为单行
align-items center 	  在侧轴居中
align-items stretch 	侧轴拉伸
```

```css
align-content:flex-start  默认值 侧轴头部开始排列
align-content:flex-end   侧轴尾部开始排列
align-content:center  侧轴中间显示
align-content:sapce-around 侧轴平分剩余空间
align-content:space-between  先分布两头  在平分剩余空间
align-content:streth  默认值 子项元素高度平分父元素高度
```

- align-content：需要设置换行；
- space-around和 space-between：把多行都看成单独的整体，整体之间有剩余空间平分。
- stretch：在侧轴方向上会拉伸；

# rem布局

em布局的核心：rem+媒体查询；

- rem：唯一控制；只要盒子用rem作为单位，**当 HTML字体大小发生改变，使用rem单位元素都会发生改变；**
- 媒体查询：把屏幕划分不同档位，等待变化；
- rem+媒体查询加在一起：划分屏幕，等待变化；变化谁？变化唯一控制 rem（HTML字体大小）
- 引用flexible.js  文件 

# 响应式布局

- 已经学习：单独制作移动端3，基础班PC端；
- 响应式通过一份代码，三个端显示；响应不同的终端，显示不同的布局（排版）效果；

利用bootstrap框架  栅格系统  响应式工具

# js转数据类型

- - - Number()：
      - "abc100"---->NaN;
    - parseInt()、parseFloat()：
      - 转成功，字符串前面的组成部分有数字；
      - true/null/undefined  转为NaN；
  - 结果：数字（0,1,10，NaN）
- 转字符串：相当于给你要转的这个数据左右两边加单双引号；
  - String(NaN)  :  ------>"NaN";
  - .toString()  :   null undefined 不能用；
- 转布尔值：
  - Boolean（）：结果返回布尔值；
  - 转false6种情况
    - 空字符串：“”
    - 数字：0、NaN；
    - null、undefined
    - false

# 操作符的优先级

 // 1. 第一优先级：()
  // 2. 第二优先级：++ -- !
  // 3. 第三优先级： * /  %
  // 4. 第四优先级： + -
  // 5. 第五优先级： > >= < <=
  // 6. 第六优先级： == != === !==
  //  7. 第七优先级： &&
  //   8. 第八优先级： ||
  //   9. 第九优先级： = += -= *= /= %=  

# 分支结构

- switch-case结构：主要用于多个**固定值**之间的判断，只能做固定值的判断

```
switch （数据）{
  case 固定值1: 
    // 当 数据 === 固定值1 时执行的代码; 先看类型，看值；
    
    // 表示当前 情况结束；
    break;
        
  case 固定值2: 
    // 当数据 === 固定值2时执行的代码;
    // break;
        
  case 固定值3: 
    // 当数据 === 固定值3时执行的代码;
    break;
  // 中间还可以写多个判断
  
  
  default : 
    // 当数据和上面的所有固定值都不相等的时候执行的代码
    break;
}
```

# 三元表达式

a > b ? a : b;  true 返回a的结果  作为整个表达式的结果  

​			false 返回b的结果 作为整个表达式的结果

# while循环

```
// 定义一个变量，从1开始
var num = 1;

// 定义一个总和，一开始是0，没有加任何数之前，都是0；
var sum = 0;


// 使用循环让num不断的自增
while (num <= 100){
  sum = sum + num;
  num++;
}
```

# for循环

```
// 定义一个总和
var sum = 0;
// 先求出1-10之间的偶数
for(var i =1; i <= 10; i++){
  // console.log(i);
  // 判断i是否是2的倍数
  if(i % 2 === 0){
    console.log(i + '是偶数');
    // 把偶数相加
    // sum = sum + i;
    sum += i;
  }
}
```

# break和continue

总结：这个地方只是用for做终止

- break用于结束整个循环
- continue用于结束整个循环中的一次，**结束当前这次循环**；
- break和continue**后面的代码都不会执行**，执行前面的代码；

# 作用域！！！

- 作用域：作用范围，能生效的范围；
- 为什么要学作用域？**目前，我们要分清楚自己的声明的变量在哪个作用域下，也就是生效的范围是多大；配合下面预解析的知识，经常是面试比较常问的基础题**；
- 全局：
  - 全局作用域：能在页面的任何位置都可以访问
  - 全局变量：在全局作用哉下声明的变量；
- 局部：
  - 局部作用域：只能在局部的作用域范围进行访问；
  - 局部变量：在局部作用域下声明的变量；

```js
var a = 10;
function f1(){
  console.log(a);
}
f1();// 变量a在函数外定义，可以在函数内使用




function f2(){
  var b = 20;
}
// 变量b在函数内定义，在函数外无法访问，报错： b is not defined
console.log(b); 
```

# 预解析 面试题！！！

提前、解析（分析）会把**初始化的声明的变量、函数**（不包括函数表达式），全部提升到**当前作用域**的最顶端；

```js
fn();// 正常执行
function f1(){
  console.log(1);
}
fn(); // 正常执行


f2();// 报错 ： f2 is not a function
var f2 = function(){
  console.log(2);
}
// function 关键字定义的函数，可以在定义之前使用，函数表达式的不行
```

```js
// 观察下面的代码，说出执行结果
var num = 10;
fun();
console.log(num);


function fun() {
  console.log(num);
  var num = 20;
}

// ------------------------------------------------------------变量提升的演示
// 预解析：先把你声明变量、函数先全部提升到你当前的作用域的最顶端；
var num;

function fun() {
    var num;
    console.log(num);
    num = 20;
}

// 赋值；
num = 10;
// 函数调用；
fun(); // 输出 undefined；
console.log(num);
```

```js
  var num = 10;
  fun();
  console.log(num);


  function fun() {
    console.log(num);
    num = 20;
  }


// 预解析完成：执行
 var num;
 function fun() {
    // 进入函数内部执行前，预解析：
    // 考虑num 是谁的num？局部变量？全局的变量？
    console.log(num);
    // 改变是全部的num
    num = 20;
 }



  num = 10; 
  fun();
  // 看当前作用域里有没有num
  console.log(num);
```

# 简单数据类型和复杂数据类型

简单类型

```js
var a = 10;
var b = a;
b = 20;
console.log(a,b); //输出 10，20 也就是说，a的值不会受到b的值的改变而影响
```

**简单类型数据存储在内存的栈空间中，复杂类型的数据存储在内存的堆空间中**

![](.\assets\001.png)

![](.\assets\002.png)

- 当另一个数据发生变化，会根据变量找到对应的**栈内存**上盒子的内容，进行修改；
- **此时，简单类型的的变量赋值给另一个变量，当另一个变量改变了，不会影响原来的变量

![](./assets/003.png)

复杂数据类型

```js
var obj1 = {
  name : '狗蛋'
};
var obj2 = obj1;
obj2.name = '翠花';

// 输出 两个翠花 ， 也就是说，obj1的name属性受到了obj2的name属性影响
console.log(obj1.name,obj2.name); 
```

- 复杂类型在内存的储存，赋值给其他变量，也是把格子内的内容复制了一份，**
- **格子里是地址；相当于两个对象内容存的是同一份地址；**

![](.\assets\004.png)

当另一个变量发生变化时，**修改的是同一个堆内存地址上的数据，所以obj1和obj2修改的其实是同一个对象

![](.\assets\005.png)

```js
// 形参与实参
 // 简单数据类型
 function f1(b) {
    b = 2;
 }
 var a = 1;
 f1(a)
 console.log(a);


  // 复制数据类型
  function f2(o) {
    o.name = '翠花';
  }
  var a = {
    name: '狗蛋'
  }
  f2(a);
  // 最终a的name属性是多少？翠花
  console.log(a.name);
```

# 获取时间戳

```js
语法：
var date = new Date( );
var date = date.getdate（ ）；获取日期
var xq= date.getday（ ）；获取星期
date.getMilliseconds( ) ；获取毫秒
获取时间戳
date.valueOf( );
date.getTime( );
1*date;
Date.now( );

```

- 获取随机唯一ID值   时间戳*随机数

# 随机数字的获取

```js
Math.random( )  取0-1随机小数
Math.floor( ) 向下取整
Math.ceil( ) 向上取整
Math.round( )  把一个浮点数进行四舍五入取整
Math.abs(x)  求一个数的绝对值 正数
Math.max(x,y...)  求多个数字中的最大值，同理 Math.min(x,y...);
```

# 数组的方法

```js
arr.push()  数组后面添加元素，返回值是添加数组后的长度   改变原来数组

arr.unshift（）   数组前面添加元素，返回值是添加数组后的长度   改变原来数组

arr.pop （）数组后面删除一个元素，返回值是被删除的元素   改变原来数组

arr.shift（）数组前面删除一个元素，返回值是被删除的元素   改变原来数组

arr.splice（n，m，...） n是开始的下标，m是移除的个数，后面是加需要加的元素
返回值是移除的元素的数组，如果无移除元素 返回值{}！！！原来的数组改变

arr.slice（n，m）n代表开始截取的下标，包括，m代表：结束截取的下标，不包括 ;
返回值是截取的新的数组  不会改变原来数组
n=0, m=0  全部截取 成立新的数组 不改变原来数组

arr.slice(n);
只输入一个数字  截取的是下标n到length的所有元素
返回值是截取的元素组成的新数组   不改变原来数组

var res = arr.indexOf(元素);！！!
元素存在  返回下标
元素不存在  返回-1
arr.findIndex！！!
var res = arr.findIndex(function(item) {
    return item > 50;
  });
 把满足条件的第一个元素的的下标返回，如找不到，返回-1；
```

```js
数组的复制

1，var new_arr = arr.concat( );；
2，var new_arr = arr.slice( );
3，var new_arr =  [  ];
arr.forEach(function(item,index) {
new_arr.push(item)  };
4，var new_arr = arr.filter(function(item, index) {
  return item;
  });
5方法五
var new_arr = arr.filter(function(item, index, arr) {
   满足条件的元素要返回
   条件成立的话（true ,false），会把满足条件的元素返回；
  直接使用的元素，隐式转化；
  return arr.indexOf(item) != -1;
  });
```

```js
数组的遍历
forEach(function(val, index, arr))	循环遍历数组
filter(function(val, index, arr))	筛选数组符合条件的 ，return出返回条件的元素  成为新的数组
some(function(val, index, arr)) 	查找符合条件的  找到就终止函数 返回值为布尔值
```

# 字符串方法

```js
var res = str.indexOf("abc");  字符串元素查找
元素存在  返回下标
元素不存在  返回-1

var res_2 = str.charAt(2);    查询下标出的字符，返回字符

var res_3 = str.charCodeAt(0);   返回 下标出的字符的ASCII 码值；

var res = str.concat("--------", '88888');返回新数组  原来数组不变

  
var res = str.substring/slice(0, 3);
第一个参数：截取开始的下标，包括
第二个参数：截取结束的下标，不包括
返回值是截取元素组成的新的数组  不会改变原来数组


var res = str.substr(2, 2);    从下标2开始，截取2个
返回值是截取元素组成的新数组  不改变原来数组


str.trim()  删除字符串两侧的空白符
```

# 数组字符串互转

```
数组转字符串
var arr = ['刘备','关羽','张飞'];
var str = arr.join('|'); 
console.log(str);  //  刘备|关羽|张飞
字符串转数组
var str = '刘备|关羽|张飞';
var arr = str.split('|');
console.log(arr);
```



# 获取元素的方法

```
document.getElementById("id名")  
document.querySelector("css选择器");
$("")

```

# 元素节点获取、修改、添加、删除的属性与方法

```js
父.children	获取父元素下所有子元素的一个集合    伪数组
元素.parentNode	获取父元素
元素.nextElementSibling  	获取下一个兄弟元素
元素.previousElementSibling 	获取上一个兄弟元素
innerHTML	可以获取标签内的HTML结构，也也可以设置HTML结构
innertext 	修改节点内容
document.createElement ("标签名")	创建指定的节点	带引号的新标签名	一个元素对象  需要一个变量接受
父.appendChild（子元素）	指定一个父元素， 从后添加子元素	标签名	
父.insertBefore（新的子元素，某个子元素）	在某个子元素之前，插入新的子元素	新的标签名，从哪里插入的标签名	
父元素.removeChild（子元素）	删除子元素	要删除的子元素	

```

```
$('CSS选择器')用法都可以	直接获取对应的元素
$('li:first')	获取第一个元素 
$('li:last')	获取最后一个元素
$(li:eq(1))	获取第n个元素，索引从0开始
$('li:odd')	获取索引是奇数的元素 
$('li:even')	获取索引是偶数的元素

jQ.parent()/jQ.parents("选择器")	对象的直接父元素/对象的而所有的父元素
jQ对象.children()	直接子元素
jQ对象.find('选择器')	所有的后代元素
jQ对象.siblings('选择器')	获取兄弟元素
jQ对象.nextAll()	获取当前元素之后的所有同级元素
jQ对象.prevtAll()	获取当前元素之前的所有同级元素
jQ对象.hasClass("nav")	判断当前元素是否有某个类名，存在返回true
jQ对象.eq(2)	相当于:eq选择器，索引从0开始

```

# 类名标签 获取、修改、添加、删除的属性与方法

```

.checked 开关属性	"ck.checked = true;ck.checked = false;"

.nodeName	 返回 DOM节点的标签名（e.target.nodeName ）

.disabled	按钮禁用属性    disabled="true"

data-src	data-src="./images/01.jpg          (img.src= btn_2.dataset.src;)

classList.add("类名1","类名2"...)	给元素对象添加一个或者多个类名，不会影响原来的类名；带引号的类名

classList.remove("类名1","类名2"...)	给元素删除一个或者多个类名，	带引号的类名

classList.toggle("类名")	切换类名	带引号的类名

元素.getAttribute("属性名")	获取属性名下的属性值	带引号的类名

元素.setAttribute("属性名,"属性值)	添加或者修改属性值	带引号的类名属性值

元素.removeAttribute("属性名")	删除某个属性	带引号的类名

var res = window.getComputedStyle(元素对象)； res.width 获取到属性值得字符串"
具体的属性 无论是行内的还是样式设置的

```

```

$('div').css('属性名')    	获取对应属性的值
$('div').css('属性','值')	$('div').css('属性','值')  设置单个样式
$('div').css({'属性'：'值','属性'：’值‘})	  同时设置多个样式
	
$('div').addClass('类名‘);	添加类
$('div').removeClass('类名');	删除类
$('div').toggleClass('类名');	切换类


jQ对象.prop('属性')	获取元素本身固有的属性值
jQ对象.prop('属性', 值)	设置元素本身固有的属性和值
jQ对象.attr('自定义属性');	获取元素自定义属性值
jQ对象.attr('自定义属性', 值);	设置元素自定义属性和值
jQ对象.val()  	 获取 表单控件中的值
jQ对象.val(值) 	 设置 表单控件中的值
jQ对象.text()	获取标签中的内容，特点与原生js中的    innertext 一样
jQ对象.text(值) 	 给标签设置值
jQ对象.html() 	获取标签中的内容，特点与原生js中的    innerHtml一样
jQ对象.html(值) 	给标签设置值，可以设置标签

$('html标签')	创建元素
jQ对象.append(创建的元素)	将创建的元素添加到父元素的结束位置
jQ对象.prepend(创建的元素)	将创建的元素添加到父元素的开始位置
jQ对象.after(创建的元素)	将创建的元素作为当前元素的兄弟元素，在当前元素的后面
jQ对象.before(创建的元素) 	将创建的元素作为当前元素的兄弟元素，在当前元素的前面
jQ对象.remove()	 将当前的元素删除
jQ对象.empty()	将当前元素中的内容清空
jQ对象.html('');	将当前标签内容清空
$.extend(obj1, obj2);
浅拷贝对象
$.extend(true, obj1, obj2)	
深拷贝对象
添加，创建元素的方法
insertAdjacentHTML("追加的位置", 添加的元素)	
afterbegin 插入元素内部第一个节点之前
beforeend插入元素内部最后一个节点之后
beforebegin元素外部的前面
afterend元素外部的后面


```

# JQ的各种方法

```
jQ对象.show（）	元素显示
jQ对象.hide（）	元素隐藏
jQ对象.toggle（）	元素切换显示隐藏
jQ对象.slideDown（）	元素显示（滑动）
jQ对象slideUp（）	元素隐藏（滑动）

jQ对象.slide.Toggle（）	元素切换显示
jQ对象.fadeIn（）	元素淡入（显示）
jQ对象.fadeout（）	元素淡出（隐藏）
jQ对象.fadetoggle（）	
jQ对象.fadeTo（）	透明度
animate(params,[speed],[easing],[fn])	params：要设置动画的CSS属性 【要以对象的形式设置CSS样式】
jQ对象.stop()	停止动画
jQ对象.index()	获取元素的索引
jQ对象[索引]/jQ对象.get(索引)	jQ对象转化为dom对象
$(dom对象)	dom对象转为jQ对象

```

# JQ的遍历

```js
jQ对象.each(function(index, domElement){ });	如果要遍历页面中的元素使用 jQ对象.each
$.each(object, function(index, element){})	    2. 如果要遍历程序中的数据使用 $.each
$.each($('li'), function(i, element){   })	可以遍历程序中的jq对象

```

# JQ的事件注册

```
$('元素').事件名称(function(){});
$('元素').on(事件名称, function(){});   ---注册一个事件
事件委托
语法：
	$('元素').on('事件名称', '真正执行事件的子元素', function(){})
例如：
	//给ul注册点击事件，但是在执行的时候，是点击每一个li执行的点击事件，委托思想
	$('ul').on('click', 'li', function(){ console.log(123) });
```

# jq的解绑事件

```
语法：
	$('元素').off([事件名称],[执行事件委托元素])

注意：
   	1. 如果off()中没有设置任何参数，代表将该元素身上的所有事件都解除掉
    2. 如果要解除对应的事件，可以设置off('事件名称')
   	3. 如果要解除委托事件，可以通过off('事件名称', '执行事件的元素')
	   例如：
       $('ul').on('click', 'li', function(){}) ---> 通过委托给li注册的点击事件
  	   $('ul').off('click', 'li')  ---> 解除li委托的点击事件

   	4. 如果一个元素只执行一次事件可以通过 one('事件名称', function(){})实现
```



# BOM方法

```
location.href	获取或重新设置地址     location.href = 'https://www.jd.com';

window.onload	页面加载完毕的时候执行                     
var timer = setTimeout(函数,延迟的毫秒数);	一次性定时器（clearTimeout(timer);）
var timer = setInterval(函数,间隔毫秒数);	永久性定时器（clearInterval(timer);）
localStorage.setItem("键",值);  	数据进行本地存储
localStorage.getItem("键");	读取数据  本地读取
localStorage.removeItem("键") 	删除键的值  本地删除
localStorage.clear();	清除本地存储
JSON.stringify(对象); 	将对象（数组）转换为json格式的字符串
JSON.parse(json格式字符串);	将json格式的字符串 转换为 对象     
```



# 获取鼠标的坐标

```js
e.clientX e.clientY
鼠标位置，以浏览器可视区域左上角为原点	数值

e.pageX e.pageY	
鼠标位置，以body左上角为原点	数值

元素.offsetLeft	
得到的是某个元素距离他的offsetParent元素的水平距离 marginLeft + left	数值

元素.offsetTop	
得到的是某个元素距离他的offsetParent元素的垂直距离 marginTop + top	数值

元素的offsetParent	
找到一个有定位的父亲元素，如果亲生父亲没有定位，会一直往上找，直到找打有定位的父亲，或者body；

元素.offsetWidth	
border+padding+content（width）	数值

元素.offsetHeight
border+padding+content（height）	数值

元素.clientWidth
盒子内容区域的宽度（content）	数值

元素.clientHeight
盒子内容区域的高度（content）	数值

```

# 事件类型

```
onclick	点击事件
onfocus	获取光标
onblur	失去光标
oncontextmenu   页面右键
onmousedown	鼠标按键点下
onmousemove	鼠标移动
onmouseup	鼠标按键弹起
onmouseover	鼠标移入
onmouseout	鼠标移出
onkeydown，onkeyup	键盘按下，键盘弹起
onchange 改变事件
"var box = document.querySelector('.box');
box.addEventListener('animationend',function(){
  console.log(123);
})"	动画结束触发
transitionend	元素的过渡动画结束的时候触发；

```

# 事件对象

```
e.stopPropagation(); 	阻止冒泡
e.preventDefault(); 	阻止默认行为

dom_a.addEventListener('click', function(e) {
    dom_a.setAttribute(""href"", ""javascript = void(0)"")
      });"	阻止a标签跳转
 dom_a.addEventListener('click', function(e) {      return :flase  });	阻止a标签跳转
dom_a.addEventListener('click', function(e) {
    e.preventDefault();
});"	阻止a标签跳转


e.target	目标对象，点到谁就是谁
this	谁注册是就是谁
e.currentTarget	谁注册是就是谁
e.keyCode == 13 （键盘码==回车键）
e.ctrlKey  true  按下ctrl键
```

# 问题型的提示框

```
  confirm()
```

# ES6类和对象的继承

```js
	class Star {
				// 属性
				constructor (uname, age) {
					this.uname = uname;
					this.age = age;
					// console.log(123);
				}

				// 方法，普通函数
				// chang：方法名，函数名
				chang () {
					console.log(this.uname + '唱歌');
				}

				tiao () {
					console.log(this.uname + '跳舞');
				}
			}



类的继承-------------------------------------------------------
class Father {
				constructor (uname, age) {
					this.uname = uname;
					this.age = age;
				}
				qian () {
					console.log('赚他一个亿');
				}
			}
			// 子类
			class Son extends Father{
				
				constructor (uname, age, score) {
					
					super(uname, age);
					this.score = score;
				}
				say () {
					console.log('哇哈哈');
				}
				qian () {
					super.qian();
					console.log('zt两毛钱');
				}
			}
			var obj = new Son('李寻欢', 22, 99);
			obj.qian();
```

# ES5对象的创建

```js
 // 对象字面量   键值对的方式

    var obj = {
        name : "王晓雨",
        age :18,
        sayname : function () {
            console.log(123);
        },
    }
    console.log(obj);
    obj.sayname();



    // 构造函数  
    var obj1 = new Object();
    obj1.name = "张三丰";
    obj1.age = 25;
    obj1.say = function () {
        console.log(456)
    }
    console.log(obj1);
    obj1.say();


    // 自定义构造函数

    function Star(usname,age) {
        this.usname = usname;
        this.age = age;
    }
    Star.prototype = {
        constructor : Star,
        chang : function () {
            console.log(852)
        },
        tiao : function () {
            
        },
        rap : function () {
            
        }
    }

    var obj2 = new Star("刘德华",26);
    // console.log(obj2);
    console.log(Star.prototype);
    console.log(obj2.__proto__.__proto__.__proto__)

    // obj2.chang();



```

# ES5的继承

```js
属性的继承
 // ES5
    // 属性的继承 当前调用 被继承函数.call(当前函数this，参数)
    function Father(usname,age) {
        this.usname = usname;
        this.age = age;
    }
    function Son(usname,age,height) {
        Father.call(this,usname,age)
        this.height = height;
    }
方法的继承
// 方法的继承  组合继承
    // 子的原型对象 = 父的构造函数   子原型对象指向构造函数  
    Father.prototype = {
        chang : function () {
            console.log(123);
        }, 
        tiao : function () {
            console.log(456);
        }
    }
    Son.prototype = new Father();
    Son.prototype.constructor = Son;
    
    Son.prototype.rap = function () {
        console.log(789)
    }
    Son.prototype.daqiu = function () {
        console.log(563)
    }
    
    var obj = new Son();
    obj.chang();
    obj.rap();
    obj.daqiu();
```

# 函数的调用方式

```
1. 普通函数【fn()】
2. 对象的方法【对象.方法()】
3. 构造函数【new Fn()】
4. 绑定事件函数【obj.onclick = function () {}】
5. 定时器函数【window.setInterval(function () {},1000)】
6. 立即执行函数【(function () {})()】
```

# this指向

```
普通函数调用	window
构造函数调用	实例对象
对象方法调用	改方法的调用对象
事件绑定方法	事件源
定时器函数	window
立即执行函数	window

```

# 改变函数内部指向

```
fun.call(函数制定的this, arg1, arg2, …参数)	
用于对象属性的继承  改变函数this指向并执行函数

fun.apply(函数制定的this, [argsArray] 参数数组的形式)
和数组在一块使用Math.max() 求数组的最大值

fun.bind(thisArg, arg1, arg2, ...)	
改变this指向  但不执行函数


相同点:  都可以改变函数内部的this指向.

区别点:  
1.call 和apply  会调用函数, 并且改变函数内部this指向.
2.call 和apply 传递的参数不一样, call 传递参数aru1, aru2..形式apply 必须数组形式[arg]
3.bind  不会调用函数, 可以改变函数内部this指向

主要应用场景:  
1.call 经常做继承. 
2.apply 经常跟数组有关系.比如借助于数学对象实现数组最大值最小值
3.bind  不调用函数,但是还想改变this指向. 比如改变定时器内部的this指向
	


```

# js开启严格模式

- js开启严格模式	"use strict";

# 闭包

- 闭包作用：延伸变量的作用范围。	

```
闭包（closure）指有权访问另一个函数作用域中变量的函数。【很多种解释，都并不权威】

简单理解就是，一个作用域可以访问另外一个函数内部的局部变量。

<script>
	function fn1(){
		// fn1 就是闭包函数
		var num = 10;
		function fn2(){
			console.log(num); // 10
		}
		fn2()
	}
	fn1();
</script>
```

# 打印索引值的三种方法

```js
// 方法一  DOM自定义属性
        for (var i = 0; i < lis.length; i++) {
            
            lis[i].setAttribute("index",i)
            // lis[i].getAttribute("index")
            lis[i].onclick = function () {
                this.getAttribute("index");
                console.log(this.getAttribute("index"))
            }
        }
// 方法2 对象的方法

        for (var i = 0; i < lis.length; i++) {
            lis[i].index = i
            lis[i].onclick = function () {
                console.log(this.index);
                
            }
        }
方法三  闭包的方法

        for (var i = 0; i < lis.length; i++) {
            // 写一个匿名函数的自调用
           (function (index) {
            //    var index = i 
            // 一个作用域访问另一个函数内部的变量 为闭包
               lis[index].onclick = function () {
                   console.log(index);
               }
           })(i)
        }
```

# 对象的深拷贝和浅拷贝

- 拷贝不能直接赋值，对象赋值的是地址

- 浅拷贝：只拷贝最外面一层

```
var obj = {
			name : '张三丰',
			age : 22
		};

		var newObj = {};
		for (key in obj) {
			newObj[key] = obj[key];
		}

		console.log(newObj);
		
es6：新方法

Object.assign(target, sources);

console.log(newObj);
```

深拷贝

```js

			var obj = {
				name : '张三丰',
				age : 22,
				color : ['red','blue','yellow'],
				message : {
					sex : '男',
					score : 99
				}
			}

			var newObj = {};

			function kaobei (newObj, obj) {
				// newObj：空对象
				// obj：拷贝对象
				for (var key in obj) {
					// 如果obj[key]是复杂数据类，就不可以直接赋值
					// 如果obj[key]是数组，遍历数组继续拷贝
					// 再如果obj[key]是对象，遍历对象继续拷贝
					// 求他就直接拷贝
					if (obj[key] instanceof Array) { // 是数组
						// 数组拷贝obj[key] = [数组]
						// 保证obj[key]是一个数组
						newObj[key] = [];
						// 把obj[key]遍历拷贝newObj[key]
						kaobei(newObj[key], obj[key]);
						
					} else if (obj[key] instanceof Object) {// 是对象
						// 对象拷贝
						newObj[key] = {};
						kaobei(newObj[key],obj[key]);
					} else {
						newObj[key] = obj[key];
					}
				
				}

			}


			kaobei(newObj, obj);

			obj.message.sex = '女';

			console.log(newObj);
			console.log(obj);

```

# 递归

```
利用递归求1~n的阶乘

//利用递归函数求1~n的阶乘 1 * 2 * 3 * 4 * ..n
 function fn(n) {
     if (n == 1) { //结束条件
       return 1;
     }
     return n * fn(n - 1);
 }
 console.log(fn(3))
```

```
利用递归求斐波那契数列

// 利用递归函数求斐波那契数列(兔子序列)  1、1、2、3、5、8、13、21...
// 用户输入一个数字 n 就可以求出 这个数字对应的兔子序列值
// 我们只需要知道用户输入的n 的前面两项(n-1 n-2)就可以计算出n 对应的序列值
function fb(n) {
  if (n === 1 || n === 2) {
        return 1;
  }
  return fb(n - 1) + fb(n - 2);
}
console.log(fb(3));


思考题羊村：50人家，每户一只羊
	每户只能看别人家的羊有木有病
	每户只能杀自己家的羊
	第一天，第二天 ,第三天，砰砰砰几声枪响，问杀了几只羊
```

```
利用递归遍历数据

		var data = [
			{
				id : 1,
				name : '家电'
			},
			{
				id : 2,
				name : '服饰'
			}
		];


var data = [{
   id: 1,
   name: '家电',
   goods: [{
     id: 11,
     gname: '冰箱',
     goods: [{
       id: 111,
       gname: '海尔'
     }, {
       id: 112,
       gname: '美的'
     },

            ]

   }, {
     id: 12,
     gname: '洗衣机'
   }]
 }, {
   id: 2,
   name: '服饰'
}];
//1.利用 forEach 去遍历里面的每一个对象
 function getID(json, id) {
   var o = {};
   json.forEach(function(item) {
     // console.log(item); // 2个数组元素
     if (item.id == id) {
       // console.log(item);
       o = item;
  
       // 2. 我们想要得里层的数据 11 12 可以利用递归函数
       // 里面应该有goods这个数组并且数组的长度不为 0 
     } else if (item.goods && item.goods.length > 0) {
       o = getID(item.goods, id);
     }
   });
   return o;
}
```

# 正则表达式测试

```
表达式.test（str）
手机验证
var regtel = /^[1][3|4|5|7|8][0-9]{9}$/;
qq号验证
var regqq = /^[1-9][0-9]{4,}$/;
昵称验证
var nikName = /^[\u4e00-\u9fa5]{2,8}$/;
短信验证
var regmsg = /^[0-9]{6}$/;
```

# 敏感字过滤

```
replace替换
表达式/[修饰符]

g：全局匹配

i：忽略大小写

gi：全局+忽略

屏蔽敏感字符


val = val.replace(/搞基|gay/gi, '**')
```

# Ajax   jQuery的写法

```
$.ajax({
    type: 'POST', //请求方式  有 GET获取 和 POST设置，默认是GET
    url: '接口地址',
    data: { //请求参数
      '参数': '值',
      '参数': '值'
    }, //或 '参数=值&参数=值'
    dataType: 'json', //响应数据格式  常用json  默认是text
    success: function(result) {
      // resule为响应结果
    },
    beforeSend: function() {
      //请求开始之前，需要做什么  (选填)
    },
    complete: function() {
      //请求结束后，执行         (选填)
    }
  })
```

```
$.ajax({
    type: '请求方式',
    url: '接口地址',
    data: '请求参数',
    dataType: '响应数据格式',
    success: function (res) {
        // res就是服务器返回的结果
    },
    beforeSend: function () {},
    complete: function () {},
    contentType: '设置请求头中的content-type的值',
    processData: '是否处理请求参数'
});
```

```
$.get('url', [请求参数], [请求成功后的回调函数], [服务器返回数据的类型]);
```

```
$.post('url', [请求参数], [请求成功后的回调函数], [服务器返回数据的类型]);
```



# 原生Ajax写法

- GET

```
//原生的Ajax请求，使用的是XMLHttpRequest对象提供的API

  // 1、实例化 XMLHttpRequest对象， request 请求
  var xhr = new XMLHttpRequest();
  //2、调用open方法，调用请求方式和url 当有参数时,写在URL后面用?隔开
  xhr.open('GET', '/common/time?username=lisi');
  //3、调用send方法，发送请求，到这一步才开始发送ajax请求
  xhr.send();
  //4、响应过程结束，接收服务器响应的结果
  xhr.onload(function() {
    console.log(xhr.response);
  })
```

- POST

```
// 1、实例化 XMLHttpRequest对象， request 请求
  var xhr = new XMLHttpRequest();
  //2、调用open方法，调用请求方式和url

	// open内的第三个参数为false时，表示为同步ajax，运行到send时，会阻塞后面的代码运行，当收到响应时再运行后续代码   不写默认为true 表示异步(常用)

  xhr.open('POST', '/common/checkUser',false);
  //3、设置请求头，固定的代码  只要写POST就写  相对于GET，多了一行
  xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
  //4、设置响应数据格式   属性 默认为text  类似于ajax里的dataType
  xhr.responseType = 'json';
  //5、调用send方法，发送请求，到这一步才开始发送ajax请求
  xhr.send({
    '参数': '值',
    '参数': '值'
  }); //或'参数=值&参数=值'
  //6、响应过程结束，接收服务器响应的结果
  xhr.onload(function() {
    console.log(xhr.response);
  })
```

# FormData  预览选择文件

```js
//获取表单数据   
//注意：input里面的name要与接口文档里面的data里面的键一样
//new FormData() 括号内的数据必须为DOM对象
const formdata = new FormData($('form')[0]); 
 //调用接口
        $.ajax({
          url: '/hero/add',
          type: 'post',
          data: formdata, 
          //  不设置类型
          contentType: false, 
          // 不处理数据
          processData: false,
          success: function(backData) {};
```

## FormData 追加数据

```js
//获取表单数据   
//注意：input里面的name要与接口文档里面的data里面的键一样
//new FormData() 括号内的数据必须为DOM对象
const formdata = new FormData($('form')[0]); 

// 追加数据
		//语法  formdata.append(key,value)  当调用接口时，key为参数名称 value要提交的内容
        formdata.append('content',editor.txt.html());
        formdata.append('state','已发布');
```

## formData提交数据

### 如果用ajax(post)提交数据报错时，检查文档接口内需要提交的参数是否都提交

![1572432324281](E:\就业班\复习\新建文件夹\总结笔记\1572432324281.png)

# 懒加载思路

![](E:\就业班\复习\新建文件夹\总结笔记\1571126953761.png)

# 模板引擎

1. 准备一个存放数据的盒子（不是必须的，使用body也可以）
2. 引入template-web.js文件
3. 定义模板（具体语法可以去官网查看），一定要指定script的id和type属性
4. 调用template函数，为模板分配数据，template函数有两个参数一个返回值
   1. 参数1：模板的id
   2. 参数2：分配的数据，必须是一个JS对象的形式
   3. 一个返回值：是数据和模板标签组合好的结果
5. 将 “拼接” 好的结果放到准备好的盒子中（不是必须的，console出来也可以看结果）

![](E:\就业班\复习\新建文件夹\总结笔记\1566443384929.png)

```js
<script src="./assets/template-web.js"></script>

<script type="text/html" id="test">
        <h2>{{title}}</h2>
        <p>{{age}}</p>
        <ul>
            <li>{{heroes[0]}}</li>
            <li>{{heroes[1]}}</li>
            <li>{{heroes[2]}}</li>
    </ul>
</script>

<script>
    // 下面的数据是模拟的，相当于ajax请求之后，服务器返回的数据
    var data = {
        title: '模板引擎练习',
        age: 20,
        heroes: ['曹操', '刘备', '李逵', '张飞']
    };
    // 调用template函数
    /*
        var str = template(模板的id, 数据); // 数据必须是JS对象格式
        */
    var str = template('test', data);
    console.log(str);
</script>
```

模板语法

- 输出普通数据（字符串、数值等）

```
// 模板写法
{{var}}

// template函数写法
var html = template('id', {
    var: 'hello world'
});
```

- 条件

```
// 模板写法
{{if age > 18}}
	大于18
{{else}}
	小于18
{{/if}}

// template函数写法
var html = template('id', {
    age: 20
});
```

- 循环

```
// 模板写法
{{each arr}}
	{{$index}} -- 数组的下标
	{{$value}} -- 数组的值
{{/each}}

// template函数写法
var html = template('id', {
    arr: ['apple', 'banana', 'orange']
});
```

# 模板引擎处理响应数据

![](E:\就业班\复习\新建文件夹\assets\snipaste_20191018_221700.png)

# 图片预览功能  ![1572354829385](E:\就业班\复习\新建文件夹\assets\1572354829385.png)

```js
<input type="file" class="file-input" id="heroIcon" name="icon">
    //给input注册change事件

    $('#heroIcon').change(function() {
    //console.dir(this.files[0]) 图片
    //url 获取到的地址可以链接到图片
    const url = URL.createObjectURL(this.files[0]);
    $(this).prev().attr('src', url);
})
```

# 解析URL中数据的方法  ![1572358989703](E:\就业班\复习\新建文件夹\assets\1572358989703.png)

- ### 简单类型，得到单个值

```js
 console.log(window.location.search);  //打印出来是?id=8
//利用split  用'='把字符串分开为数组  获取第二个元素即可得到id
const id = window.location.search.split('=')[1];
```

![1572359423741](E:\就业班\复习\新建文件夹\总结笔记\1572359423741.png)

- ### 复杂类型，得到对象类型

```js
url:http://127.0.0.1:3000/index.html?name=jack&age=18&skill=swim
	//解析数据  slice 获取从索引1开始到最后的数据  得出name=jack&age=18&skill=swim
   var dataStr = window.location.search.slice(1);
        //以&为分隔符  切割为`key=value`的数组  得到 name=jack age=18 skill=swim  的数组
        var dataArr = dataStr.split('&');
        // 生成数据对象
        var searchData = {};
        for (var i = 0; i < dataArr.length; i++) {
            // 获取每一项  将每一项用=分隔  
            var eachData = dataArr[i].split('=');
            // console.log(eachData); 得到[name,jack] [age,18] 的数组
            // 添加到对象中 key=value  通过 对象[键]=值  将每一项赋给对象
            searchData[eachData[0]] = eachData[1];
        }
```

![1572427775170](E:\就业班\复习\新建文件夹\assets\1572427775170.png) ![1572427906539](E:\就业班\复习\新建文件夹\总结笔记\1572427906539.png)

# Node.js获取地址中的数据

```js
app.get('/hero/info', (req, res) => {
  // query是一个保存了get请求提交的数据的对象
  // console.log(req.query);
  // 接收参数
  const id = req.query.id;
```

# Node.js获取post提交的数据

```js
// 导包 express-fileuploadbody-parser 获取text文本的
const bodyParser = require('body-parser');

// 导包 express-fileupload  获取文件的  图片
const fileUpload = require('express-fileupload');

app.post('/hero/add', (req, res) => {
  // 获取文本
  //   console.log(req.body);
  const { name, skill } = req.body;  //post提交的数据都在这个对象里  文本
  // 获取文件
  //   console.log(req.files);   post提交的图片 文件都在这里 
  // 文件名
  const icon = req.files.icon.name;
  // 保存文件  将文件保存到upload的文件夹里
  req.files.icon.mv(path.join(__dirname, './uploads', icon), err => {
    // 这是保存文件的回调函数
    if (!err) {
      console.log('文件保存成功了哦!');
    }
  });
```

# Node.js托管静态资源

```js
// 静态资源托管 (让外部可以访问)  web  文件夹名
app.use(express.static('web'));
```

