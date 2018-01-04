---
title: css3
---


## 盒模型

### 盒子模型

``` bash
$ 盒子中的内容（content）
$ 边框（border）
$ 内边距（padding）
$ 外边距（margin）
```

### 盒子3D模型

``` bash
$ border
$ content+padding
$ background-image
$ background-color
$ margin
```

### 盒子模型尺寸

``` bash
$ 盒子模型尺寸=边框+外边距+内边距+盒子中的内容尺寸
$ (浏览器的宽度-外包含层的宽度)/2=外边距
```



## 清除浮动的方法

``` bash
$ overfl:hidden（隐藏溢出部分）
$ visibility:hidden（隐藏部分）
$ display:none（隐藏全部）
$ clear:both（给浮动元素留下足够的垂直外边距）
```

## position四种属性
``` bash
$ static（静态定位、默认）
$ relative（相对定位）
$ absolute（绝对定位）
$ fixed（固定定位）
```
## 布局
### 静态布局（Static Layout）

``` bash
$ 即传统Web设计，对于PC设计一个Layout，在屏幕宽高有调整时，使用横向和竖向的滚动条来查阅被遮掩部分；
$ 对于移动设备，单独设计一个布局，使用不同的域名如wap.或m.。
```
### 自适应布局（Adaptive Layout）

``` bash
$ 自适应布局（Adaptive）的特点是分别为不同的屏幕分辨率定义布局。布局切换时页面元素发生改变，但在每个布局中，页面元素不随窗口大小的调整发生变化。
$ 可以把自适应布局看作是静态布局的一个系列。
```
### 流式布局（Liquid Layout）

``` bash
$ 流式布局（Liquid）的特点（也叫"Fluid") 是页面元素的宽度按照屏幕进行适配调整，主要的问题是如果屏幕尺度跨度太大，那么在相对其原始设计而言过小或过大的屏幕上不能正常显示。
```
### 响应式布局（Responsive Layout）

``` bash
$ 分别为不同的屏幕分辨率定义布局，同时，在每个布局中，应用流式布局的理念，即页面元素宽度随着窗口调整而自动适配。
$ 可以把响应式布局看作是流式布局和自适应布局设计理念的融合。
```
## 媒体查询
媒体查询的目的是应用不同的css规则为了获取不同的布局，有助于考虑多个显示尺寸的可能
@media screen and(max-width:980px){
	#pagewrap{
	width:95%;
    }
    #content{
    width+60%;
    padding:3% 4%;
    }
    #sidebar{
     width:30%;
    }
}
