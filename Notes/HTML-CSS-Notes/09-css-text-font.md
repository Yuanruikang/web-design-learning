# CSS字体属性
字体样式、大小、粗细、文字样式
## 字体样式
font-family 来定义文本的字体系列  
```html
P {font-family:"微软雅黑";}
div {font-family: Arial,"Mircrosoft-Yahei","微软雅黑"}
```
- 尽量使用系统默认字体
- 如果浏览器找到不字体，会依照font-family里的字体排列顺序去寻找字体，若最后还是没有会加载系统字体。
- 但也可以调用远程字体@font-face

## 字体大小
font-size定义字体大小
```html
P {font-size: 20px;}
```
- px（像素）大小是我们网页的最常用的单位
- 谷歌浏览器默认的文字大小为16px
- 不同浏览器可能默认是示的字号大小不一致，我们尽量给一个明确值大小。
- **标题**比较特殊，需要单独指定字体大小和粗细（style{body{...}}里设定font-size和font-weight对标题不起作用）
## 字体粗细
font-weight设定文本粗细
```html
P {font-weight: bold;}
```
| 属性值  |                            描述                             |
| :-----: | :---------------------------------------------------------: |
| normal  |                     默认值（不加粗的）                      |
|  bold   |                     定义粗体（加粗的）                      |
| 100-900 | 400 等同于normal，而700 等同于bold 注意这个数字后面不跟单位 |

如果想去掉标题的加粗效果就可以用：
```html
h2 {font-weight: normal;}
```
## 文字样式
normal or italic；平时很少用斜体，反而要给斜体改为不斜体：
```html
em {
    font-style:normal;
}
```
## 字体复合属性
将几个属性按照规定顺序写在一起，节约代码量
- font字体的设定可以在一行里完成：顺序是： "font-style font-variant font-weight font-size/line-height font-family"
- font-size和font-family的值是必需的。如果缺少了其他值，默认值将被插入，如果有默认值的话，用空格隔开。  
  **注意**：line-height属性设置行与行之间的空间。
