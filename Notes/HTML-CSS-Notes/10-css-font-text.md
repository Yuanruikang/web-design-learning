# 文本格式
## 文字颜色
可以用英文单词、十六进制、rgb值来表示；用rgba 来表示透明度
### 颜色
```html
body {color: rgba(255, 0, 0, 0.5);}<!--r=red;g=green;b=blue;a=alpha;最后一位表示透明度:1表示完全不透明-->
h1 {color:#00ff00;} <!--这种情况可以省略为0f0-->
p.ex {color:rgb(0,0,255);}
```
## 对齐方式
左、右、中间、两端对齐(justify) 
```html
h1 {text-align:center;}
p.date {text-align:right;}
p.main {text-align:justify;}
```
## 文字修饰，加入划线 
```html
h1.over {text-decoration:overline;}
h2.line {text-decoration:line-through;}
h3.under {text-decoration:underline;}
a.none {text-decoration:none}<!--最常用，这样可以去掉a中默认的下划线-->
```
## 文本缩进
```html
p {text-indent: 2em;} /*用em单位表示字符宽度 */
```   
## 字间距和词间距    
 ```html
p.letter-spacing {letter-spacing: 30px;}
p.word-spacing{word-spacing: 30px;} 
``` 
- letter-spacing 调节字符间距:
1. 对于英文，调节每个字母与每个字母的间距
2. 对于汉字，调节每个汉字与每个汉字的间距  
- word-spacing 调节词间距:
1. 对于英文，调节每个单词与每个单词的间距
2. 对于汉字，无法自动解析，需要在文本中将其已空格隔开
## 行间距（非段落的段前和段后）
```html
p.small {line-height:90%}
p.big {line-height:200%}
```
正常为normal
![line-height](../Pics/line-height.PNG)
    
文本上下标（sub和sup） 
  
```html
    <!-- 一个网页的背景颜色是指在主体内的选择：
    对于W3C标准的CSS：如果你定义了颜色属性，你还必须定义背景色属性。 -->
    <p>这是一个普通的段落。请注意,本文是红色的。页面中定义默认的文本颜色选择器。</p>
    <p class="ex">这是一个类为"ex"的段落。这个文本是蓝色的。</p>
```