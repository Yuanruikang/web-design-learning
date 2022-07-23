# 数据类型
Target:
- 5种数据类型
- typeof
- 转换为数值型的方法
- 转换为字符型的方法
- 隐式转换「isNaN() 数字字符串-或者* 」
# 变量的数据类型
1. JS赋值不声明变量类型，故变量在使用中数据类型是可以变换类型的
2. 在实际执行时，JS引擎根据变量👉值的数据类型来判断该变量的具体类型
# 简单数据类型
## Number数值型
类型，包括：整型和浮点  
各种其他进制的写法
- 八进制:数字前面加0表示八进制
```javascript
var num1=010;
console.log(num1);//010为八进制里的8，console结果输出的值为十进制的
``` 
- 十六进制: 用0-9和a-f表示，数字前面需要加上0x来表示十六进制
```javascript
var num1=0xa;
console.log(num1);//结果为10，console结果输出的值为十进制的
```   
- JS中确定数组最大值和最小值  
MAX_VALUE MIN_VALUE  
- 表示∞  
Infinity 无穷大   
-Infinity 无穷小  
- NaN 非数字，比如字符串-数字就会出现NaN 
  用isNaN()判断是否是数字
```javascript
var userAge = 21;
var isNum = isNaN(userAge) ;
console.log(isNum);// false
var usrName = "andy";
console.log(isNaN (userName) ); // true
//如果isNaN输入单引号'2'或者双引号 "2",结果都是false，即函数判断为数字
//isNaN()的原理：该函数会先调用Number方法，尝试将该参数转换为数值型，如果成功返回false
```
## String字符串类型  
字符串嵌套：遵循就近原则，如果字符串里面有字符串则外面和里面用不同的引号，如'xxxx"xxx"xxxxx'

字符串长度：string.length

字符串拼接：string+string，**字符串➕数字结果还是字符串**  
```javascript
var age = 19;
console.log('blue'+age+'red');
```
```javascript
var input=prompt("请输入年龄");
alert("\"您今年"+input+"岁了\"");
```
## Boolean布尔型➕Undefined➕Null
在四则运算中中，true=1、false=0

一个声明后没有被赋值的变量会有一个默认值undefined（如果进行字符串相连或者相加时，注意结果）
```javascript
var variable;
console.log(variable);
console.log('你好' + variable)；//你好undefined
console.log(11 + variable);//NaN
console.log(true + variable);//NaN
```
如果一个变量声明=null值，里面存的值为空
```javascript
var var1 = null;
console.log('您好'+var1)；//你好null
console.log(11+var1);//11
console.log(true+var1);//1
```
# typeof()
typeof是关键字不是像python里的函数名，使用方法直接[typeof 变量名]
```javascript
var num = 10;
console.log(typeof num); // number
var str='color'
console.log(typeof str); // string
var flag = true;
console.log(typeof flag); // boolean 
var vari = undefined;
console.log(typeof vari); // undefined
var timer = null;
console.log(typeof timer); // object
var input=prompt("请输入年龄");
console.log(typeof input);//通过prompt输入的字符默认为字符串格式
alert("\"您今年"+input+"岁了\"");
```
# 数据类型的转换
**注意：通过prompt输入的字符默认为字符串格式**
## 转换为字符串类型
| 方式              | 说明                         | 案例                                 |
| :---------------- | :--------------------------- | :----------------------------------- |
| num.toString()    | 转成字符串                   | var num= 1; alert(num.toString));    |
| String() 强制转换 | 转成字特串                   | var num = 1; alert(String(num));     |
| 加号拼接字符串    | 和字符串拼接的结果都是字符串 | var num = 1:alert(num+"我是字符串"); |

**注意：**
```javascript
var var1=true; 
console.log(typeof var1); //boolean
var2=var1.toString();
console.log(var2); //true
console.log(typeof var2);//string
```
## 转换为数字型
| 方式                     | 说明                         | 案例                |
| :----------------------- | :--------------------------- | :------------------ |
| parseInt(string) 函数    | 将string类型转成整数数值型   | parseInt('78")      |
| parseFloat(string)函数   | 将string类型转成浮点数数值型 | parseFloat('78.21") |
| Number() 强制转换函数    | 将string类型转换为数值型     | Number('12')        |
| js 隐式转换(- * /) 没有➕ | 利用算术运算隐式转換为数值型 | "12"- 0             |

```javascript
// var age = prompt(•请输入您的年龄’）；
// 1. parseInt(变量）
//可以把 字符型的转换为数字型 得到是整数
// console.10g (parseInt (age)) ;
console.log(parseInt('3.14')); // 3 
console.log(parseInt('3.94'));  // 3取整
console.log(parseInt('120px'));  // 120
console.log(parseInt('rem120px')); // NaN
// 2. parseFloat(string)函数
console.log(parseFloat('3.94'));  // 3.94
console.log(parseFloat('120px'));  // 120px的单位会去掉
console.log(parseFloat('rem120px')); // NaN
// 3.利用Number(变量）
var str="123";
console.log (Number(str));
console.log (Number ('12'));
// 4.利用了算数运算 隐式转换
console.log('12'- 0); //12
console.log('123'-'120'); //3
console.log('123'*1); //123
console.log('123'*'2'); //246
```
简单加法：
```javascript
var v1=prompt("请输入值1:"); 
var v2=prompt("请输入值2:"); 
alert(parseFloat(v1)+parseFloat(v2));
```
## 转换为布尔型
Boolean()
* 代表空、否定的值都会被转换为false，如'', 0, NaN, null, undifined
* 其余都会被转为true 

 