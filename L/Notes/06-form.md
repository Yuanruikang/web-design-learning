## 表单
目的：收集用户信息
表单结构：表单域、表单控件（表单元素）、提示信息

## 1.表单域
用\<form>\</form>定义表单域
```html
<from action="url地址" method=“提交方式” name=“表单域名称”>
    表单控件
</form>
```
常用属性：
|  属性  |  属性值  |           作用           |
| :----: | :------: | :----------------------: |
| action | url地址  |   服务器程序的url地址    |
| method | get/post |  设定表单数据的提交方式  |
|  name  |   名称   | 区分同一页面中的其他表单 |

## 2. 表单控件
### 2.1 input输入表单元素

<style>
    .new {
        vertical-align:text-bottom;
        color:red
    }
</style>
<table>
<tr>
<th width="22%">值</th>
		<th>描述</th>
	</tr>
<tr>
<td>button</td>
		<td>定义可点击的按钮（通常与 JavaScript 一起使用来启动脚本）。</td>
	</tr>
<tr>
<td>checkbox</td>
		<td>定义复选框。</td>
	</tr>
<tr>
<td>color<span class="new">New</span>
</td>
		<td>定义拾色器。</td>
	</tr>
<tr>
<td>date<span class="new">New</span>
</td>
		<td>定义 date 控件（包括年、月、日，不包括时间）。</td>
	</tr>
<tr>
<td>datetime<span class="new">New</span>
</td>
		<td>定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，基于 UTC 时区）。</td>
	</tr>
<tr>
<td>datetime-local<span class="new">New</span>
</td>
		<td>定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，不带时区）。</td>
	</tr>
<tr>
<td>email<span class="new">New</span>
</td>
		<td>定义用于 e-mail 地址的字段。</td>
	</tr>
<tr>
<td>file</td>
		<td>定义文件选择字段和 "浏览..." 按钮，供文件上传。</td>
	</tr>
<tr>
<td>hidden</td>
		<td>定义隐藏输入字段。</td>
	</tr>
<tr>
<td>image</td>
		<td>定义图像作为提交按钮。</td>
	</tr>
<tr>
<td>month<span class="new">New</span>
</td>
		<td>定义 month 和 year 控件（不带时区）。</td>
	</tr>
<tr>
<td>number<span class="new">New</span>
</td>
		<td>定义用于输入数字的字段。</td>
	</tr>
<tr>
<td>password</td>
		<td>定义密码字段（字段中的字符会被遮蔽）。</td>
	</tr>
<tr>
<td>radio</td>
		<td>定义单选按钮。</td>
	</tr>
<tr>
<td>range<span class="new">New</span>
</td>
		<td>定义用于精确值不重要的输入数字的控件（比如 slider 控件）。</td>
	</tr>
<tr>
<td>reset</td>
		<td>定义重置按钮（重置所有的表单值为默认值）。</td>
	</tr>
<tr>
<td>search<span class="new">New</span>
</td>
		<td>定义用于输入搜索字符串的文本字段。</td>
	</tr>
<tr>
<td>submit</td>
		<td>定义提交按钮。</td>
	</tr>
<tr>
<td>tel<span class="new">New</span>
</td>
		<td>定义用于输入电话号码的字段。</td>
	</tr>
<tr>
<td>text</td>
		<td>默认。定义一个单行的文本字段（默认宽度为 20 个字符）。</td>
	</tr>
<tr>
<td>time<span class="new">New</span>
</td>
		<td>定义用于输入时间的控件（不带时区）。</td>
	</tr>
<tr>
<td>url<span class="new">New</span>
</td>
		<td>定义用于输入 URL 的字段。</td>
	</tr>
<tr>
<td>week<span class="new">New</span>
</td>
		<td>定义 week 和 year 控件（不带时区）。</td>
	</tr>
</table>

### 2.2 select下拉表单元素

### 2.3 textarea文本域元素
