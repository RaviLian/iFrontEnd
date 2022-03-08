# 0. 学习记录
## 学习时长
9:00 - 12:22
## 学习目标
入门css，试着完成一个例子
## 学的比较透彻的
- 基本选择器的使用
## 学的比较粗略的
- 关于em的认识。
## 学了之后依然有疑问的
- border、padding、margin
- 块内的元素(block element和inline element)如何居中？
# 1. 初始css选择器
```css
// li.special,
span.special {
  color: orange;
  font-weight: bold;
}
只对类名为special的span有效
p, li {
  color: red;
}
对全部p和li有效

li span{
  color: red;
}
对li的后代span有效

/* selects any <p> that comes directly after a <ul>, which comes directly after an <h1>  */
h1 + ul + p { ... }

body h1 + p .special {
  color: yellow;
  background-color: black;
  padding: 5px;
}
上面的代码为以下元素建立样式：在<body>之内，紧接在<h1>后面的<p>元素的内部，类名为 special。
```
# 2. 初始css属性
## font-size
适用于所有元素
### em
em可以自动适应用户的字体，em是一个非常有用的CSS单位。  
用`em`值设定字体大小。`em` 值的大小是动态的。当定义或继承font-size属性时，1em等于该元素的字体大小。如果你在网页中任何地方都没有设置文字大小的话，那它将等于浏览器默认文字大小，通常是16px。所以通常1em = 16px。2em = 32px。 如果你设置了body元素的字体大小为20px，那1em = 20px、2em = 40px。那个2就是当前em大小的倍数。  
`em = 希望得到的像素大小 / 父元素字体像素大小`  
一个流行的技巧是设置body元素的字体大小为62.5% (即默认大小16px的62.5%)，等于10px。现在你可以通过计算基准大小10px的倍数，在任何元素上方便的使用em单位。这样有6px = 0.6em, 8px = 0.8em, 12px = 1.2em, 14px = 1.4em, 16px = 1.6em。例如：
```css
body {
  font-size: 62.5%; /* font-size 1em = 10px */
}
p {
  font-size: 1.6em; /* 1.6em = 16px */
}
```
## width
width 属性用于设置元素的宽度。width 默认设置内容区域的宽度，但如果 box-sizing 属性被设置为 border-box，就转而设置边框区域的宽度。
```css
语法
/* <length> values */
width: 300px;
width: 25em;

/* <percentage> value */
使用外层元素的容纳区块宽度（the containing block's width）的百分比定义宽度。
width: 75%;

/* Keyword values */
width: max-content; 元素内容固有的（intrinsic）合适宽度。
width: min-content; 元素内容固有的最小宽度。
width: fit-content(20em);
width: auto; 浏览器将会为指定的元素计算并选择一个宽度。

/* Global values */
width: inherit;
width: initial;
width: unset;
```
将只覆盖文字区域
```css
p.maxgreen {
      background: lightgreen;
      width: intrinsic;
      /* Safari/WebKit 使用了非标准的名称 */
      width: -moz-max-content;
      /* Firefox/Gecko */
      width: -webkit-max-content;
      /* Chrome */
    }
```
## border
设置边框
```css
/* style */
border: solid;

/* width | style */
border: 2px dotted;

/* style | color */
border: outset #f33;

/* width | style | color */
border: medium dashed green;

/* Global values */
border: inherit;
border: initial;
border: unset;
```

## padding 与 margin
内边距和外边距
```css
/* 应用于所有边 */
padding: 1em;

/* 上边下边 | 左边右边 */
padding: 5% 10%;

/* 上边 | 左边右边 | 下边 */
padding: 1em 2em 2em;

/* 上边 | 右边 | 下边 | 左边 */
padding: 5px 1em 0 2em;
```
