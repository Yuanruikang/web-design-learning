# CSS书写习惯
## 1. CSS代码风格
a. 属性分多行写   
b. 小写代码，容易识别  
**名字太长一般用-来连接，不建议用_下划线来命名，因为js变量命名用_**
c. 空格格式：  

【强制】选择器与{ 之间必须包含空格，示例： 

    .selector {
    }
【强制】属性名与之后的：之间不允许包含空格，：与属性值之间必须包含空格。
示例：

    font-size: 12px;
【强制】 当一个rule包含多个selector时，每个选择器声明必须独占一行。
示例：

    .post,
    .page,
    .comment {
        line-height: 0.5
    }
## 2. style 遵循以下顺序：
1. 布局定位属性：diaplay/position/flaot/clear/visibility/overflow（建议display第一个写，关系到模式）
2. 自身属性：width/height/margin/padding/border/background
3. 文本属性：color/font/text-drcoration/text-align/vertical-align/white-space/break-word
4. 其他属性（CSS3）：content/cursor/border-radius/box-shadow/text-shadow/background:linear-gradient...      
