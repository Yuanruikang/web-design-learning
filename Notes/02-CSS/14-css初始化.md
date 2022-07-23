# CSS初始化
不同浏览器对有些标签的默认值是不同的，为了消除不同浏览器对HTML文本呈现的差异，照顾刘览器的兼容，我们需要对CSS初始化

简单理解：CSS初始化是指重设浏览器的样式。（也称为CSS reset )每个网页都必须首先进行 CSS初始化。  
这里我们以京东CSS初始化代码为例。  
**Unicode编码字体：**
把中文字体的名称用相应的Unicode编码来代替，这样就可以有效的避免浏览器解释CSS代码时候出现乱码的问题.  
比如:  
- 黑体 \9ED1\4F53
- 宋体 \5B8B\4F53
- 微软雅黑 \5FAE\8F6F\96CS\9ED1
```html
<style>
/* 把我们所有标签的内外边距清零 */
* {
    margin: 0;
    padding: 0
}
/* em 和 i 斜体的文字不倾斜 */
em,
i {
    font-style: normal
}
/* 去掉li 的小圆点 */
li {
    list-style: none
}

img {
    /* border 0 照顾低版本浏览器 如果 图片外面包含了链接会有边框的问题 */
    border: 0;
    /* 取消图片底侧有空白缝隙的问题 */
    vertical-align: middle
}

button {
    /* 当我们鼠标经过button 按钮的时候，鼠标变成小手 */
    cursor: pointer
}

a {
    color: #666;
    text-decoration: none
}

a:hover {
    color: #c81623
} 

button,
input {
    /* "\5B8B\4F53" 就是宋体的意思 这样浏览器兼容性比较好 */
    font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif
}

body {
    /* CSS3 抗锯齿形 让文字显示的更加清晰 */
    -webkit-font-smoothing: antialiased;
    background-color: #fff;
    font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif;
    color: #666
}

.hide,
.none {
    display: none
}
/* 清除浮动 */
.clearfix:after {
    visibility: hidden;
    clear: both;
    display: block;
    content: ".";
    height: 0
}

.clearfix {
    *zoom: 1
}
</style>
```
# 页面布局整体思路
为了提高网页制作的效率，布局时通常有以下的整体思路：
1. 必须确定页面的版心（可视区），我们测量可得知。
2. 分析页面中的行模块，以及每个行模块中的列模块。其为页面布局第一准则.
3. 一行中的列模块经常浮动布局,先确定每个列的大小,之后确定列的位置，页面布局第二准则
4. 制作HTML结构。我们还是遵循，先有结构，后有样式的原则。结构永远最重要
5. 所以，先理清楚布局结构,再写代码尤为重要. 这需要我们多写多积累 