# 表格
1. Table用来更好地展示数据
2. Table的基本结构：
   table tr=table row td=table data
    ```html
    <table>
    <tr><td></td> <td></td> <td></td> </tr>
    </table>
3. 表头单元格：默认会加粗➕居中
4. 表格属性有：  
   |   属性名    |      属性值       |                                    描述                                    |
   | :---------: | :---------------: | :------------------------------------------------------------------------: |
   |    align    | left,center,right |      规定表格相对周围元素的对齐方式。表格在**页面**上是居中还是左对齐      |
   |   border    |      11或"“       |     规定表格是否拥有边框，默认为™，表示没有边框。表格外面是否有个圈圈      |
   | cellpadding |      像素值       | 规规定单元边沿与其内容之间的空白，默认1像素。但是table data 默认是左对齐的 |
   | cellspacing |      像素值       |                     规定单元格之间的空白，默认2像素。                      |
   |    width    |  像素值或百分比   |                              规定表格的宽度。                              |
   
   **但**：不常用，一般通过css来控制表格属性 
   **这些属性要写在table标签里**
5. 表格结构标签
   1. \<thead>\</thead>：用于定义表格的头部。＜thead>内部必须拥有＜tr＞标签。一般是位于第一行。
   2. \<tbody>\</tbody＞：用于定义表格的主体 ，主要用于放数据本体。
   3. 以上标签都是放在\<table>\</table>标签中。
6. 合并单元格 
   colspan 跨列合并 
   rowspan 跨行合并