> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.cnblogs.com](https://www.cnblogs.com/Hfolsvh/p/15651879.html)

页面样式（页面参考了别的小程序的页面）
===================

标题字体的样式
-------

[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207104329879-1345646537.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207104329879-1345646537.png)image

```
复制`.title{
  margin-top: 45rpx;
  font-size: 50px;
  font-weight: 700;
  background: -webkit-linear-gradient(left, #6cc6cb, #ef33b1);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;

}` 
```

*   `font-size`是字体大小
*   `font-weight`是字体的粗细
*   字体颜色渐变  
    `background: -webkit-linear-gradient(left, #6cc6cb, #ef33b1);`这一行是设置字体颜色从左往右渐变，颜色是从#6cc6cb到 #ef33b1  
    [渐变色的搭配参考](https://baijiahao.baidu.com/s?id=1644345842477287270&wfr=spider&for=pc "渐变色的搭配参考")  
    `-webkit-background-clip: text;`  
    `background-clip: text;`  
    `-webkit-text-fill-color: transparent;`

输入框的样式
------

[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207105332271-1144065130.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207105332271-1144065130.png)image

```
复制`.get_info{
  height: 500rpx;
  width: 600rpx;
  background-color: white;
  text-align: center;
  margin-top: 50rpx;
  border-radius: 50rpx;
  box-shadow: 6rpx 6rpx 6rpx 6rpx violet;
}` 
```

*   `border-radius: 50rpx;`是设置圆角，取值为百分比或者数字  
    [相关border属性](https://blog.csdn.net/UFO00001/article/details/72832770 "相关border属性")
*   `box-shadow: 6rpx 6rpx 6rpx 6rpx violet;` [设置对象的阴影](https://www.runoob.com/cssref/css3-pr-box-shadow.html "设置对象的阴影")  
    `box-shadow:`有六个参数，分别为：水平阴影的位置、垂直阴影的位置、模糊距离、阴影的大小、阴影的颜色、从外层的阴影（开始时）改变阴影内侧阴影

按钮的样式
-----

[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207110321832-1468428763.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207110321832-1468428763.png)image

```
复制`.button-contain{
  height: 90rpx !important;
  width: 70% !important;
  margin-top: 350rpx;
  border-radius: 20rpx;
  background: linear-gradient(to right, #bbdbec, #e5b7e9);
  color: white;
}` 
```

*   按钮的高度和宽度后加了`!important`，否则按钮大小无法改变，只能是系统默认的大小，加`!important`提高了属性的优先级
    
*   `border-radius: 20rpx;`同样是设置圆角
    
*   `background: linear-gradient(to right, #bbdbec, #e5b7e9);` 设置按钮背景颜色从左往右线性渐变  
    第一个参数设置渐变的方向，可以是`to right`,`to bottom right`,`45deg`  
    [点击查看具体函数效果](https://www.runoob.com/cssref/func-linear-gradient.html "点击查看具体函数效果")
    
*   `color: white;`设置字体颜色，这些设置颜色的都可以写成渐变
    

页面布局
====

一些重要的属性
-------

*   **display**控制组件的显示方式  
    常见的值：  
    `display:none`隐藏该元素  
    `display:block`设置为块元素，总是从新行开始，对宽高的属性值生效  
    `display:inline`设置为内联元素，可以和其他元素在一行上，对宽高属性值不生效，完全靠内容撑开宽高  
    `display:inline-block`结合的行内和块级的优点，既可以设置长宽，可以让padding和margin生效，又可以和其他行内元素并排。  
    `display:flex`弹性布局，适应于不同屏幕尺寸
*   **align-items**在flex布局的容器中，将各个子项对齐  
    `align-items:center`元素位于**容器的**中心。  
    [具体效果](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=center "具体效果")
*   **justify-content**在flex布局的容器中，各个子项在横轴上（**水平**）的对齐方式

```
复制`justify-content: center;     /* 居中排列 */
justify-content: start;      /* 从行首开始排列 */
justify-content: end;        /* 从行尾开始排列 */
justify-content: flex-start; /* 从行首起始位置开始排列 */
justify-content: flex-end;   /* 从行尾位置开始排列 */
justify-content: left;       /* 一个挨一个在对齐容器得左边缘 */
justify-content: right;      /* 元素以容器右边缘为基准，一个挨着一个对齐, */` 
```

[具体效果](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=flex-start "具体效果")

*   **text-align**指定元素**文本**的**水平**对齐方式

```
复制`left	把文本排列到左边。默认值：由浏览器决定。
right	把文本排列到右边。
center	把文本排列到中间。
justify	实现两端对齐文本效果。
inherit	规定应该从父元素继承 text-align 属性的值。` 
```

*   **margin**设置元素外边距（上下左右）  
    相关的四个单独的属性

```
复制`margin-bottom 底部边距
margin-left 左边距
margin-right 右边距
margin-top 上边距` 
```

*   **padding**设置填充属性  
    和margin效果类似  
    **区别：** margin设置元素外边距的值，padding设置元素内边距的值
*   **flex-direction** 规定元素的排列方式

```
复制`row  将元素水平显示
column 将元素垂直显示` 
```

*   **rpx**  
    宽度和高度数值如果是rpx，就会自适应屏幕大小

根据页面解释布局
--------

[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203044713-2103072515.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203044713-2103072515.png)image  
就看页面上半部分

### 各个class样式之间的级别关系

[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203159516-487117786.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203159516-487117786.png)image  
（忽略box_contain）  
[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207210702604-1007805389.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207210702604-1007805389.png)image

### background_color

```
复制`.background_color{
  height: 500rpx;
  width: 100%;
  background-color: mistyrose;
  align-items: center;
  display: flex;
  flex-direction: column;
}` 
```

删除`align-items: center;`，该容器内元素就不会居中  
[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203751030-830549293.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207203751030-830549293.png)image  
将`flex-direction 改为row`，元素就不会垂直排列  
[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207204019554-1816832209.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207204019554-1816832209.png)image

### get_info

```
复制`.get_info{
  height: 500rpx;
  width: 600rpx;
  background-color: white;
  text-align: center;
  margin-top: 50rpx;   
  border-radius: 50rpx;
  box-shadow: 6rpx 6rpx 6rpx 6rpx violet;
}` 
```

去掉`text-align: center;`，内容就不会居中  
[![image](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207205156822-1089400629.png)](https://img2020.cnblogs.com/blog/2018690/202112/2018690-20211207205156822-1089400629.png)image

### 剩下的就不说了

```
复制`.input-contain{
  align-items: center;
  display: flex;
  flex-direction: column;
}

.input_info{
  width: 80%;
  height: 100rpx;
  background-color: whitesmoke;
  margin-top: 20rpx;
  border-radius: 30rpx;
  display: flex;
  align-items: center;
  justify-content: center;
}` 
```

### 一些居中

```
复制`align-items: center;
是让元素位于容器中心，就是水平、垂直居中

justify-content: center; 
让元素在水平上居中

text-align: center; 
让文本水平居中` 
```