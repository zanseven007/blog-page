---
title: 前端开发中垂直居中的技巧
date: 2017-03-20 10:46:44
tags:
    - 前端
    - 个人
    - 复制粘贴专用
---

在前端开发中，经常会遇见需要元素垂直居中的场景，今天来总结一下常用的垂直居中方法

<!--more-->

## 一、利用 `line-height` 实现

```css

.demo1 { 
    height: 100px;
    line-height 100px;
}

```

适用于：1、高度固定 2、文字单行（多行文字会出现溢出）

## 二、利用 `display:table` 实现

```css

.demo-outer { 
    display: table;
}
.demo-outer .demo-inner{
    display: table-cell;
    vertical-align: middle;
}

```

适用于：比较通用，但是会改变元素 display

## 三、利用 `margin` 或者 `padding` 实现

```css

.demo-outer { 
    height: 100px;
}
.demo-outer .demo-inner{
    height: 50px;
    margin-top: calc((100px - 50px)/2); /* 或者 padding-top: calc((100px - 50px)/2); */
}

```

适用于：内外元素高度都固定

## 四、利用 `absolute` 加 `margin` 实现

```css

.demo-outer { 
    position: relative;
}
.demo-outer .demo-inner{
    height: 50px;
    position: absolute;
    top: 50%;
    margin-top: -25px;
}

```

适用于：内部元素高度固定，外部容器的高度可以不定

## 五、利用 `absolute` 加 `transform` 实现

```css

.demo-outer { 
    position: relative;
}
.demo-outer .demo-inner{
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}

```

适用于：内外元素高度都可以不定，但是像 IE8等老浏览器不支持 transform 属性

## 六、利用 `flex` 实现

```css

.demo6 { 
    display: flex;
    align-items: center;
}

```

适用于：移动端 flex 还是支持的比较好，PC 端 IE 就不是很给面子了
