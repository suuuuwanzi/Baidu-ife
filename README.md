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