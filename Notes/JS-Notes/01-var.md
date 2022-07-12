# Var

# 汇编语言和高级语言
- 汇编语言和机器语言实质是相同的，都是直接对硬件操作，只不过指令采用了英文缩写的标识符，容易识别和记忆。
- 高级语言主要是相对于低级语言而言，它并不是特指某一种具体的语言，而是包括了很多编程语言，常用的有C语言、C++、 Java、C#、Python、PHP、JavaScript、Go语言、Objective-C、Swift等。
# 编程语言和标记语言
- 编程语言有很强的逻辑和行为能力。在编程语言里, 你会看到很多 if else 、for 、while等具有逻辑性和行为能力的指令，这是主动的。
- 标记语言(html)不用于向计算机发出指令，常用于格式化和链接。标记语言的存在是用来被读取的, 他是被动的
# 储存单位
bit < byte < kb < GB < TB<.....
* 位(bit): 1bit 可以保存一个 0 或者 1 (最小的存储单位)
* 字节(Byte):1B = 8b
* 千字节(KB):1KB = 1024B
* 兆字节(MB):1MB = 1024KB
* 吉字节(GB): 1GB = 1024MB
* 太字节(TB): 1TB = 1024GB
# 浏览器组成
以后再补：  
https://segmentfault.com/a/1190000018277184  
https://www.jianshu.com/p/e4a75cb6f268  
https://zhuanlan.zhihu.com/p/47407398  
https://zhuanlan.zhihu.com/p/261111011  
# JS
## ECMAScript
[JavaScript_technologies_overview](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/JavaScript_technologies_overview)

ECMAScript 规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。
## DOM文档对象模型(Document Object Model)
DOM是W3C组织推荐的处理可扩展标记语言的标准编程接口。 通过DOM提供的接口可以对页面上的各种元素进行操作(大小、位置、颜色等)。
## BOM浏览器对象模型(Browser Object Model) 
BOM是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。
## JS 关键字
关键字:是指 JS本身已经使用了的字，不能再用它们充当变量名、方法名。  

包括:break、case、catch、continue、default、delete、do、else、finally、for、function、if、in、 instanceof、new、return、switch、this、throw、try、typeof、var、void、while、with 等。
## JS 保留字
保留字:实际上就是预留的“关键字”，意思是现在虽然还不是关键字，但是未来可能会成为关键字，同样不能 使用它们当变量名或方法名。

包括:boolean、byte、char、class、const、debugger、double、enum、export、extends、 fimal、float、goto、implements、import、int、interface、long、mative、package、 private、protected、public、short、static、super、synchronized、throws、transient、 volatile 等。

**注意:** 如果将保留字用作变量名或函数名，那么除非将来的浏览器实现了该保留字，否则很可能收不到任何错误消息。当浏览器将其实现后，该单词将被看做关键字，如此将出现关键字错误。
# 变量声明
## 声明多个变量格式
```javascript
var age=18,
    address='xxx',
    gz=2000;
```
## 只声明不赋值
```javascript
var sex;
    console.log(sex);
```
最后结果会输出undefined

## 不声明也不赋值会直接报错“variable is not defined”
```javascript
console.log(sex);
```
## 不声明直接赋值使用
可以使用的😌
# 命令规范
- 由字母(A-Za-2)、数字（0-9)、下划线（_）、美元符号(＄）组成，如：usrAge,num01, name
  **不用&、#等其他符号**
- 严格区分大小写。varapp;和 var App;是两个变量
- 不能以数字开头。 18age 是错误的
- 不能是关键字、保留字。例如：var、for、while  
  **一般也不使用name为变量名**
- 遭寸驼峰命名法。首字母小写，后面单治的首字母需要大马。myFirstNare
