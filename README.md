# css
清除浮动：
方法一：在底部插入：clear:both --》可以使用伪元素代替 （IE6/7:zoom:1）
方法二：让父元素BFC

标准的写法：
.clearfix:after{content:"",display:block;height:0;overflow:hidden;clear:both}
.clearfix{*zoom:1}

可以用以下这种方式替换：
.clearfix:after{content:"",display:table;clear:both}
.clearfix{*zoom:1}


.clearfix应用在包含浮动元素的父级元素上 （不要滥用）

浮动可以让元素block化和去空格化 clear.html

缺点：
1)容错性差
2）重用性差，需要固定width
3）IE7


借助浮动实现流体布局
1)内容自适应：
左侧固定宽度，右侧margin-left，这样右侧的内容自适应，详见：float1.html

2)左侧和右侧都自适应宽度,具体请参照：float2-flow.html
float
display:table-cell           IE8+
display:inline-block         IE7


tab.html 结合jquery和understore做的一个tab切换Demo
autoswitch.html  单张图片自动切换

标准文档流:
     从上到下,从左到右
     由块级元素和行内元素组成.

块级元素:div,ul.li dl,dt,p等
行级元素：span,strong,img,input等

块级元素和行内元素都是盒子模型；

margin,border,padding,content
盒子模型的尺寸=margin+border+padding+content


浮动布局：
特点：元素会向左，或右移动，直到碰到容器为止；
设置的浮动元素，仍然处在标准文档流中

设置为浮动后，
1）自身元素的宽度随着内容的变化而变化
2）会对相邻的元素产生影响，相邻元素特指紧邻后面的元素。


清除浮动的常用方法：
1）clear:both (对受到影响的元素进行设置)
2) 同时设置width:100%(或者固定宽度)+overflow:hidden;(对受到影响的元素进行设置)