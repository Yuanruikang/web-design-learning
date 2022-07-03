# 表格
1. 表格用来显示数据，列表用来布局
2. 列表最大的特点就是整齐、整洁、有序，它作为布局会更加自由和方便：比如小米网站
3. 根据不同的使用场景，列表一般分为三大类：无序列表、有序列表、自定义列表
## 无序列表
<ul style="list-style-type:square">
        <!--unordered lists-->
        <!--无序排列的图标可以用css来控制 ：style="list-style-type:disc" 
            style="list-style-type:circle" style="list-style-type:square"-->
        <li>Coffee</li>
        <!--list item-->
        <li>Milk</li>
        <li>Tee</li>
</ul>

无序列表里只能放\<li>不放其他任何东西，同时它没有先后顺序    
**但**\<li>里面可以放任何标签
## 有序列表
<!--ordered lists-->
<ol start="50">
    <li>hoffee</li>
    <li>Milk</li>
    <li>Tee</li>
</ol>
<ol reversed="reversed" type="I" start="50">
    <!--ol 加上 type=A 表示大写 a 表示小写 I罗马大写 i罗马小写-->
    <!--reversed 加上意为倒排序-->
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
</ol>

\<ol>里只能嵌套\<li>
\<li>之间相当于一个容器，都可以放的  
有序列表有自己的样式，实际开发用css来控制

## 自定义列表
常用在网页底部的导航栏里，如小米官网的底部
<dl><!--definition lists-->
    <!--definition term-->
    <dt>名词1</dt>
    <!--definition description-->
    <dd>名词1解释1</dd>
    <dd>名词1解释2</dd>
    <dd>名词1解释3</dd>
    <dt>名词2</dt>
    <dd>名词2解释1</dd>
    <dd>名词2解释2</dd>
    <dd>名词2解释3</dd>

</dl>