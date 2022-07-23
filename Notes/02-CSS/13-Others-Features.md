# 精灵图技术
### 精灵图 （ sprites）的使用  
1. 精灵技术主要针对于背景图片使用。就是把多个小背景图片整合到一张大图片中。
2. 这个大图片也称为 sprites 精灵图 或者 雪碧图。
3. 移动背景图片位置，此时可以使用 background-position。
4. 移动的距离就是这个目标图片的x和y坐标。注意网页中的坐标有所不同。
5. 因为一般情况下都是往上往左移动，所以数值是负值。
6. 使用精灵图的时候需要精确测量，每个小背景图片的大小和位置。
### 精灵图缺点：
1. 图片文件还是比较大的。
2. 图片本身放大和縮小会失真。
3. 一旦图片制作完成想要更换非常复杂。  
# 字体图标
**字体图标的产生**  
字体图标iconfont技术的出现很好的解决了**精灵图**的问题。
宇体图标可以为前端工程师提供一种方便高效的图标使用方式，展示的是图标，本质属于字体。  
字体图标使用场景：主要用于显示网页中通用、常用的一些小图标。    
### 字体图标的优点
1. 轻量级：一个图标字体要比一系列的图像要小。一旦宁体加载了，图标就会马上渲染出来，减少了服务器请求。
2. 灵活性：本质其实是文字，可以很随意的改变颜色、产生阴影、透明效果、旋转等。
3. 兼容性：几乎支持所有的浏览器，请放心使用。  

**注意：** 字体图标不能替代精灵技术，只是对工作中图标部分技术的提开和优化。  

**总结：**
1. 如果遇到一些结构和样式比较简单的小图标，就用字体留标。
2. 如果遇到一些结构和样式复杂一点的小图片，就用精灵图。
### 字体图标的引入
字体图标是一些网页常见的小图标 ，我们直接网上下载即可。因此使用可以分为：
1. 字体图标的下载
* https://icomoon.io
* https://www.iconfont.cn/
2. 字体图标的引入（引入到我们htm页面中）
* 下载好文件后，解压zip包，将**fonts文件夹**放到html的根目录，之后在style文件内引入@font-face类 
![字体类别](../Pics/font类别.png)
3. 字体图标的追加（以后添加新的小图标）
* 将demo.html中想要使用的图标复制到html页面中，可以调整其font-size、color等属性
```html
   <span></span>
``` 
* [demo详情](font_6sewa2bhng6/demo_index.html)  
4. 字体图标的追加
将zip文件夹里的json文件import到**字体下载网站**，网站会重新生成此组图标的数据，我们就可以在此基础上增加其他图标，以供我们使用。
![字体图标追加](../Pics/字体图标追加.png)
# CSS三角形的插入
网页中常见一些三角形，使用CSS直接画出来就可以，不必做成图片或者字体图标。
```html
div {
width: 0;
height: 0;
<!-- line-height和font-size是为了兼容性考虑 -->
line-height:0;
font-size: 0;
border: 50px solid transparent;
border-left-color: pink
}
```
# 鼠标样式 
li {curcsor: pointer;}  
设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形式
|   属性值    | 描述                                               |
| :---------: | :------------------------------------------------- |
|   default   | 小白箭头 默认                                      |
|   pointer   | 小手：👋                                            |
|    move     | 移动：淘宝网页端商品放大展示时，图片上的十字架形状 |
|    text     | 文本：大写I形状                                    |
| not-allowed | 禁止：🚫                                            |
# 去掉表单轮廓线 outline
表单默认是有轮廓线的，给表单添加outline:();或者outline:none;样式之后，就可以去掉默认的蓝色边框了
```html
<style>
  input {
    <!-- 取消表单轮廓 -->
    outline: none;
  }
</style>
```
# textarea防止任意拖拽文本域大小
```html
<style>
  textarea {
    <!-- 止任意拖拽文本域 -->
    resize: none;
    outline;none;  <!-- 同时去掉文本域的蓝色外边框-->
  }
</style>
```
文本域的元素标签最好写在一行上，防止光标定位在文本框内出现没有对齐到左上端的情况
```html
<texarea name="" id="" cols="30" row="10"></textarea>
```
# veticl-align 属性应用
## 应用场景：经常用于设置图片或者表单（行内块元素）和文字垂直对齐
**但**只针对行内块元素或者行内块有效
语法： vertical-align: baseline | top | middle | bottom
图片默认和文字的基线对齐  
![](../Pics/文字的底线-基线-中线-顶线.png)
使用：
```html
<head>
<style>
  img {
  display: inline-block;
  vertical-align: middle;
  }
</style>
```

文本域也可以实现框框与文字对齐，因为其也为行内块元素
```html
<style>
  textarea {
  vertical-align: middle; 
  }
</style>
```
## 解决图片底部默认空白缝隙问题
默认情况下图片底部会有一个空白缝隙，因为行内块元素会和文字的基线对齐。  
主要解决办法：  
1. 给图片添加vertical-align: middle | top | bottom 等（只要不是基线对齐），提倡使用这种方式。
2. 把图片转换为块级元素display: block;
# 溢出文字省略号显示
## 单行文字溢出用省略号
```html
  <style>
    div {
      width: 150px;
      height: 80px;
      background-color: pink;
      margin: 100px auto;
      /* 1. white-space: normal; 这个单词的意思是如果文字显示不开自动换行 */
      white-space: nowrap; 
      /* nowrap: 如果文字显示不开，也必须在一行内显示 */

      overflow: hidden;
      /* 2. 溢出的部分文字隐藏起来 */

      text-overflow: ellipsis;
      /* 3. 文字溢出的似乎用省略号 */

    }
  </style>
```
## 多行文字溢出用省略号
多行文本溢出显示省略号，有较大的兼容性问题，适用于webkit浏览器或移动端（移动端大部分是webkit内核）
```html
  <style>
    div {
      overflow: hidden;
      text-overflow: ellipsis;
      /* 弹性伸缩盒子模型显示 */
      display: -webkit-box;
      /* 限制在一个块元素显示的文本的行数  */
      -webkit-line-clamp: 2;
      /* 设置或检索伸缩盒对象的子元素的排列方式 */
      -webkit-box-orient: vertical;
    }
  </style>
```
# margin 负值运用
## float时，给每一个小框加上border，消除边界上border变粗的情况
```html
  <style>
    * {
      margin: 0;
      padding: 0;
      /* 清除P的内边距 */
    }
    .box {
      width: 300px;
      height: 70px;
      background-color: pink;
      margin: 0 auto;
    }
    .pic {
      float: left;
      width: 100px;
      height: 70px;
    }
  </style>
  <body>
    <div class="box">
      <div class="pic">
        <img src="img...." alt="">
      </div>
      <p> 「集锦」热身赛</p>
      <!-- 在div「class="box"」的img添加浮动后，由于浮动不遮蔽文字，所有仅仅添加左浮动，就可以让右边的文字排列好 -->
  </body>
```
# 行内块元素布局
## 页码布局 
直接用行内块元素布局，不用浮动，因为各个页码块之间是有空隙的，正好符合行内块元素的设定
```html
<style>
    .box {
      text-align: center;
    }

    .box a {
      display: inline-block;
      width: 36px;
      height: 36px;
      background-color: #f7f7f7;
      border: 1px solid #ccc;
      /* text-align: center; */
      line-height: 36px;
      text-decoration: none;
      color: #333;
    }

    .box .prev,
    /* 注意类的优先级 */
    .box .next {
      width: 85px;
    }

    .box input,
    .box button {
      background-color: #f7f7f7;
      border: 1px solid #ccc;
    }
  </style>
</head>

<body>
  <div class="box">
    <a href="" class="prev">&lt;&lt;上一页</a>
    <a href="">2</a>
    <a href="">3</a>
    <a href="">4</a>
    <a href="" class="next">&gt;&gt;下一页</a>
    到第
    <input type="text">
    页
    <button>确定✅</button>
  </div>
</body>
```
# 京东秒杀楔形制作
```html
<style>
  .box {
    width: 0;
    height: 0;
    /* 上边框宽度调大 让它变成非等腰直角三角形,都写一样会成等腰三角形*/
    border-top: 100px solid transparent;
    border-right: 50px solid skyblue;
    /* 左边和下边的边框宽度设置为0 */
    border-left: 0 solid green;
    border-bottom: 0 solid blue;
  }
  .box-simple {
    /* 精简代码 */
    /* 1. 只保留右边的边框有颜色 */
    border-color: transparent red transparent transparent;
    /* 2. 样式都是solid */
    border-style: solid;
    /* 3. 上边框宽度要大,右边框宽度稍小,其余的边框为0 */
    border-width: 100px 50px 0 0;

  } 
</style> 
```
