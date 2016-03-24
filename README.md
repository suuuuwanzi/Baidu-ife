# Baidu-ife
Web trainning

1、自动居中一列布局（标准文档流）

用<div id="wrap">包裹住header、mainbody、footer层
设置#wrap{width:一个固定的数值，不可以是100%; margin:0 auto;}
即可实现自动居中


2、横向两列布局（浮动布局）

float:left right both
可以实现横向多列布局
但是会对相邻的元素产生影响，需要清除浮动
清除浮动的方法：1）适合于父层元素 容纳了浮动块  消除对其的影响  {width:;overflow:hidden;}
                2) {clear:both}  <也可以clear：right/left>

注意：不要对块元素设置高度  让其根据浏览器和内容自适应高度
3、绝对定位布局

3.1相对定位（更稳定 用于设置父包含块，作为绝对定位的参照基准）
position:relative
特点：1相对于自身原有位置进行偏移 2 仍处于标准文档流中，会占据标准文档流的空间 3拥有了偏移属性和z-index属性（因为产生了堆叠 有了互相遮盖 即产生了Z轴上的特性）

3.2绝对定位
特点：1 、建立了以包含块为基准的定位   2、完全脱离了标准文档流 不会影响兄弟块
3拥有了偏移属性和z-index属性（因为产生了堆叠 有了互相遮盖 即产生了Z轴上的特性）
 "<em>当一个元素设置绝对定位，没有设置宽度时，元素的宽度根据内容进行调节</em>"
case1：posation:absolute 不设置具体偏移值
       特点：1、尺寸随着内容变化（不设置width时）
             2、无论是否存在已定位的祖先元素，都保持在元素初始位置
             3、完全脱离了标准文档流

case2:设置偏移量
偏移参照基准：
      1、无已定位祖先元素，以<html>为偏移参照基准（不是以<body>作为参照！）
      2、有已定位祖先元素，以距其最近的已定位祖先元素为偏移参照基准


absolute实现横向两列布局（不常使用）
应用场景：常用于一列固定宽度、另一列宽度自适应的情况
主要应用技能：对其父元素设置相对定位，对自适应宽度的元素设置绝对定位  使用margin调节同列间距
<important>注意：固定宽度列的高度必须大于自适应宽度的列，用于撑开父元素<important>



<style color="blue">2016.3.14完成index.html时遇到的问题</style>
1、header部分：在将logo部分和导航部分进行位置的设计时遇到了问题，至今解决的也不好 待改进 如何更高效的让其处于该处的位置，并且
调整logo字体时不会影响到nav部分距header bottom的位置
2、注意画布的包括范围，即div覆盖的部分

<style color="green">2016.3.15完成index.html时遇到的问题</style>

1、如何实现三个同行div自适应内容高度且保持高度一致?
Answer:父级元素overflow:hidden
里边的三个子元素 每一个都是设置一个大的padding-bottom 然后用margin-bottom抵消掉就可以了


2、3个同行div的位置布局不够熟练 目前的方法认为不够合适 
为何用float left无法达到3个模型同行？？？？？  

3、<div>...</div>封闭的错误导致出了很多问题  主要出现在message部分  3个大的div块的封闭错误的写成了</div>   令后面的盒子整个凌乱了 

4、如何让头像部分在灰色背景区域显示出来





2016.03.23
开始写blog.html，是一个两列格局，吸取写index时候遇到的定位、浮动问题，争取这次写的更适应改变。

1、header 部分的定位问题
logo和link在写index时候采用浮动方法，及时设置了bottom的值他们也不会在自身该在的位置上，让我十分头疼

此次写将 headwrap 设置为relative，将logo和link设置为absolute，设置好下方距离后，发现两个都飞出了header部分，此时将headwrap设置 height值后，二者又出现在了原本该处在的位置上。


2、让右侧第二栏的内容在div中垂直居中的方法
1、行高（line-height）法
如果要垂直居中的只有一行或几个文字，那它的制作最为简单，只要让文字的行高和容器的高度相同即可，比如：

p { height:30px; line-height:30px; width:100px; overflow:hidden; }
这段代码可以达到让文字在段落中垂直居中的效果。


3、div不设置高度时 如何给主体部分设置背景颜色

将父类设置{overflow: hidden;
	height:auto;}