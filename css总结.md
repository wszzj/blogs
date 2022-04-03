# CSS内容
CSS中文名：层叠样式表，是由挪威莱博士提出和发明的。它是一种添加页面文件样式的语言，最广泛的版本是CSS2.1，2022年目前最新更新到CSS3.0，由W3C定义和维护。

## CSS最常见的语法样式：
    
    选择器{
        属性名:属性值;
    } 

## CSS的重要概念：
1. 文档流
2. 盒模型
3. 布局
4. 定位
5. 动画   

### 文档流

文档流指文件流动的方向，分为一下三种（可通过display相互转换）：
* inline元素：元素从左到右排列时，到最右边换行（元素会断开），宽度是内容的宽度，高度有line-height间接绝对，不能设置宽高。
* block元素：元素独占一行，宽度尽量大，高度是内部文档流决定，宽高可以设置。
* inline-block元素：元素从左到右排列时，到最右边换行（元素不会断开），宽度是内容的宽度，高度由内部文档流决定，可以设置宽高。

### 盒模型
当对一个文档布局时，浏览器会按照标准，将每一个元素表示为一个矩形盒子。矩形盒子从内到外包含内容层区域（content）、内边距区域（padding）、边框区域（border）和外边距区域（margin）。可以通过css改变它们的样式。盒模型有两种：
* box-sizing：content-box，宽度=内容区的宽度。
* box-sizing：border-box，宽度=内容区 + padding + border 的总和。优先使用border-box。

### CSS布局
CSS布局指的是将网页分成各个单独的区域，有三种常用布局：
1. float布局（常用于<= ie9浏览器）使用时子元素的语法样式：
    
        float:left;
        width:100px;

   父元素类的属性语法样式：

        .clearfix::after{
            content:'';
            display:block;
            clear:both;
        }

2. flex布局（手机电脑常用）主要处理单行和单列的布局排序。包含容器（display：flex）和子项。

container容器有属性：
*  主轴：flex-direction（顺序）、flex-warp（换行）、justify-content（对齐）
*  次轴：align-items（对齐）

items项属性：
* order（显示顺序）。
* flex-grow和flex-shrink控制空间的大小和变化速率。
* align-self单独控制单个子项单独样式。

3. gaid布局（最新最强）可以处理多行和多列的布局排序。主要属性可以通过[浇水小游戏](https://cssgridgarden.com/#zh-cn)了解。

### CSS定位

在一个div里面分层从上到下：定位元素：正值>内联子元素>浮动子元素>块级子元素>边框>背景>定位元素：负值。
定位可以将元素脱离出正常文档流，使他们处于不同的状态。属性名：position；属性值有五种：
* static：默认值。
* relative：相对定位，可通过Z-index改变元素显示优先级。
* absolute：绝对定位，定位是相对于最近的不是static属性的祖先元素位置。
* flex：固定定位，定位相对于页面固定，滑动页面时元素不动。
* sticky：类似excel中的冻结窗口效果，滑动页面时，始终位于页面最顶部。

### CSS动画

浏览器的渲染原理包括：
1. 根据HTML文件构建HTML树（DOM）。
2. 根据CSS文件构建CSS树（CSSOM）。
3. 将以上两棵树合成为一棵render渲染树。
4. 输出layout布局。
5. 绘制paint样式。
6. 根据层叠样式关系composite合成页面。

reflow回流和repaint重绘机制会影响CSS的性能，需要代码进行优化，例如：尽量选择DOM 树底层的元素去修改Class；避免设置多个内联样式；如果要使用动画尽量选择Position为Fixed或Absolute的元素；不要选用Table布局等。
   
CSS动画是描述由多个关键帧画面组成的有开始结束时间的CSS元素，有两种实现方式：

* transform+transition属性控制元素的位移、大小、倾斜和旋转，通常只用于表现最简单的动画。
* animation+@keyframe属性，可以设置几个关键帧，经浏览器处理，完成较复杂的多位置位移、往复等动画。
  
可参照演示[跳动的心](https://wszzj.github.io/heart/heart.html)




