背景颜色、背景图片、背景铺平、背景图片位置、背景图片固定
### background-color
- 什么都不写的时候默认为transparent
```html
<div>
    width: 30px;
    height: 50px;
    background-color: transparent;
</div>
```
- 也可以用颜色描述：十六进制、rgb、rgba、
### background-image
logo或者一些装饰性的小图片、超大的背景图片都可以用background-image，**便于控制位置**  
默认为none；  
```html
<div>
    width: 30px;
    height: 50px;
    background-image: url(xxx/xx.jpg);
</div>
```
### background-repeat
|   参数    |                      含义                       |
| :-------: | :---------------------------------------------: |
|  repeat   |         背景图像将向垂直和水平方向重复          |
| repeat-x  |           只有水平位置会重复背景图像            |
| repeat-y  |           只有垂直位置会重复背景图像            |
| no-repeat |            background-image 不会重复            |
|  inherit  | 指定 background-repeat 属性设置应该从父元素继承 |

注意：1. 在不写repeat的时候，背景图片默认平铺（repeat）
2. 图片会在颜色顶层
### background-position（重要）
background-position 可以用左右中来描述 或者%的位置来描述 或者像素位置来描述  
left top  
left center  
left bottom  
right top  
right center  
right bottom  
center top  
center center  
center bottom    
- 默认值是左上角 即为 0% 0% 右下角是100％100％ 只取一个值另一个默认50%  像素单位是0px 0px
- 如果指定的两个值都是方位名词，则两个值前后顺序无关，比如 left top和top left 效果一致
- 如果只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐
- 如果只指定一个数值，那该数值一定是x坐标，另一个默认垂直居中，且2px 3px表示前者为x坐标后者为y坐标
### 背景固定
<!--scroll: 背景图片相对于容器位置固定
            fixed: 背景图片相对于浏览器窗口固定
            local: 背景图片相对于容器内容位置固定-->
<!--background-size 100% 100%为纵横上全覆盖背景 会拉伸图片 
            cover和contain 会保留背景图片的纵横比：
            cover	此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。
            contain	此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。-->
### 背景复合写法
当使用简写属性时，没有特定的书写顺序,一般习惯约定顺序为：  
background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

            