# 内置对象

# Math
Math是一个内置对象，但不是一个**构造器**，Math中所有的属性和方法都是静态的（不需要new）。此外，JS中的常数是以全精度实数定义的
## 常见属性
- Math.E 欧拉常数
- Math.LN2 2的自然对数，约等于0.693
- Math.LN10 10的自然对数，约等于2.303
## 常见方法
1. 取绝对值
```javascript
  Math.abs(-1) // 1
  Math.abs('-1') // 1 字符串默认会隐式转换
  Math.abs('blue') // NaN
```

2. 三个不同的取整方法
```javascript
  //1. 向下取整
  Math.floor(1.9); // 1
  Math.floor(1.1); // 1
  Math.floor(-1.2); // -2 向下取整数，如果是负数取更小，因为-2小于-1
  
  // 2. 向上取整
  Math.ceil(1.4); // 2
  Math.ceil(1.7); // 2 
  Math.ceil(-2.1); // 2 
  console.log(Math.ceil(-1.6)); // -1
  // 3. 四舍五入
  // 正数
  Math.round(1.2); // 1 
  Math.round(1.5); // 2 
  //  负数
  Math.round(-1.3); // -1
  Math.round(-1.5); // -1
  console.log(Math.round(-1.6)); // -2
```

3. 取随机数

```javascript
  Math.random(); // 返回一个随机小数 0 <= x < 1,不包含1
  
  //得到一个两数之间的随机数 getRandomArbitrary(min, max)
  function getRandomArbitrary(min, max) {
  return Math.random() * (max - min) + min;
  }
  // 这个值不小于 min（有可能等于），并且小于（不等于）max。

  // 两数间随机整数
  function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min)) + min; 
  // 不含最大值，含最小值
  }
   // 两数间随机整数，包含两端
  function getRandomIntInclusive(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) +  min; //含最大值，含最小值 
  }
```

4. 最大值和最小值
```javascript
  Math.max[];
  Math.min[];
```
# Date
- 创建一个新`Date`对象的唯一方法是通过[`new`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/new) 操作符，例如：`let now = new Date();`  
- 若将它作为常规函数调用（即不加 [`new`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/new) 操作符），将返回一个字符串，而非 `Date` 对象。
```javascript
  var arr = new Array();
  var obj = new Object();
  
  // 使用Date 不带参数
  var date = new Date();
  console.log(date);
  // 带参数
  var date1 = new Date(2022, 10, 2);
  console.log(date1); // 返回的是 11月 不是 10月
  var date2 = new Date('2022-10-2 8:8:8');
```
1. 如果**没有提供参数**，那么新创建的 Date 对象表示实例化时刻的日期和时间，即当前时间
2. 参数常用的写法
- 数字型 2022 10, 01 // 用逗号
- 字符串型 '2022-10-1 8:8:8'  // 短横杠 空格 冒号
## 日期格式化
```javascript
  var date = new Date();
  console.log(date.getFullYear()); // 返回当前日期的年
  console.log(date.getMonth() + 1); // 返回月份 月份要➕:one:，因为默认month范围为（0，11）
  console.log(date.getDate()); // 返回几号
  console.log(date.getDay(); // 0⃣️是周日 6⃣️是周六 3是周三
  // 解决日期问题，用数组
  var week = ['星期日','星期一','星期二','星期三','星期四','星期五','星期六'];
 console.log(date.getHours()); //获取当前小时
 console.log(date.getMinutes()); //获取当前分钟
 console.log(date.getSeconds()); //获取当前秒数
 // 小时前面加0
 h = date.getHours();
 h = h < 10 ? '0'+ h : h;
 
 m = date.getMinutes();
 m = m < 10 ? '0'+ m : m;
```

## 总时间毫秒数--时间戳
因为用32位来表示时间的最大间隔是68年，而最早出现的UNIX操作系统考虑到计算机产生的年代和应用的时限综 合取了1970年1月1日作为UNIX TIME的纪元时间(开始时间)
```javascript
  // 通过valueOf() getTime()
  var date = new Date();
  date.valueOf();// 现在的时间距离1970.01.01总毫秒数
  console.log();
  
```

2. 简单写法
```javascript
  var date1 = +new Date();
```
**注意：**    
- `+new Date()`只是拿来获取总的毫秒数的，而`new Date()`才是用于创建日期对象
- 这种写法做了隐式转换 Date() + '0'

3. H5 新增获得总毫秒数的写法
```javascript
console.log(Date.now());
```

## 倒计时案例
用两个时间戳相减，就是剩余时间（倒计时），直接拿时分秒相减算不出来
```javascript
  // 用户输入的时间总毫秒数-当前时间毫秒数=剩下时间毫秒数
  //  余数比除数小
  d = parseInt(totalTime/60/60/24); // totalTime为秒🐱数
  h = parseInt(totalTime/60/60%24);
  m = parseInt(totalTime/60%60);
  s = parseInt(totalTime%60);
```

```javascript
  function countdown(time) {
    var nowTime = +new Date(); // 返回当前时间毫秒数
    var inputTime = +new Date(time); // 输入的时间数
    var times = inputTime - nowTime; // 剩余时间总毫秒数
    var d = parseInt(times/1000/60/60/24); // times为毫秒🐱数，需要先变成秒
    d = d < 10 ? '0' + d : d;
    var h = parseInt(times/1000/60/60%24);
    var m = parseInt(times/1000/60%60);
    var s = parseInt(times/1000%60);
    return d + '天' + h + '小时' + m + '分' + s + ' 秒'
  }
```

# Array

## 1. 创建数组

```javascript
  // 利用字面量
  var arr = [1,2,3];
  // 利用new Array()
  // Array()括号里什么都不写表明为空数组
  var arr1 = new Array(2); //  这个2表示数组长度为2
  var arr2 = new Array(2, 3); // 表示里面有两个数组元素为2和3
```
## 2. 检测是否为数组

```javascript
  //1. instanceof 运算符用来检测是否为数组
  var arr = [];
  console.log(arr instanceof Array);
  
  //2.Array.isArray(参数)  方法，是数组返回true
  console.log(Array.isArray(arr));
  
  //翻转数组增强，检测输入是否为数组
  function reserve(arr1) {
    if (Array.isArray(arr1) {
      var newArr = [];
      for (i = arr1.length -1 ; i>=0; i--) {
        newArr[newArr.length] = arr1[i];
      }
      return newArr;
    }else {
      return 'error';
    }
  }
```
## 3. 添加或者删除数组元素

```javascript
  // 1. 在数组末尾添加
  // push()  在数组末尾添加一个或者多个数组元素 
  var arr4 = [1,2,3];
  arr4.push(4,'blue'); //  可以追加多个，此方法有返回值，其值为数组新的总长度
  
  // 2. unshift 在数组开头添加一个或者多个
  arr4.unshift('red','green'); // 此方法有返回值，其值为数组新的总长度
  
  // 3. 删除数组最后一个元素
  arr4.pop(); // 一次删一个，()里面不加参数，返回值为删除的值，数组长度会减一
  
  // 4. shift删除第一个元素
  arr4.shift();// 一次删一个，()里面不加参数，返回值为删除的值，数组长度会减一
```

## 4. 筛选案例

```javascript
  var arr5 = [1500,1200,2000,2100,1800];
  var newArr = [];
  for (var i = 0; i < arr5.length;i++) {
    if (arr5[i] < 2000) {
      // newArr[newArr.length] = arr5[i];
      newArr.push(arr5[i]);
      //unshift 就是反转筛选
    }
  }
```
## 5.数组排序

```javascript
  // 翻转
  var  arr6 = ['pink','red','blue'];
  arr6.reverse();
  
  // 排序
  var arr7 = [2,4,56,7,8];
  arr7.sort();
  // 但是sort()默认实现方式是字典排序
  var arr8 = [13, 4, 477,7 ,1];
  arr8.sort(function(a,b) {
    return a - b; //升序排列
    //return b - a; // 降序排列
    // 如果a-b>0(即正数)就把a和b的位置交换，也就是较小的一个数会排到前面； 如果b-a>0就把a和b的位置交换，也就是较大的一个数会排到前面。
  })
```

## 6. 数组索引方法

```javascript
  // indexOf() 输入数组元素返回数组索引号
  var arr9 = ['blue' , 'green', 'purple', 'blue'];
  console.log(arr9.indexOf('blue'));
  // 只返回第一个匹配到的索引号<双blue>
  // 如果找不到该元素，返回-1
  
  // lastIndexOf(数组元素)，从后面往前查找
```

## 7. 数组去重

利用新数组arrNew.indexOf() 返回-1说明新数组没有这个元素那么就push进去

```javascript
  function unique(arr10) {
    var newArray = [];
    for (i = 0; i< arr10.length; i++) {
      if (newArray.indexOf(arr10[i]) === -1) {
        newArray.push(arr10[i]);
      }
    }
  }
  // 其他，原理：两层循环，外层遍历每一个元素，并判断lastIndexOf与外。层i，若不一样，则内层循环使lastIndexOf后面的元素往前移，最后pop删除最后一个元素即可
```
## 8. 数组转为字符串

* toString() 
* join(分隔符)

```javascript
  // 1. toString()
  var arr11 = [1,2,3];
  console.log(arr11.toString());
  
  // 2. join(分隔符) 
  var arr12 = ['green','blue','pink'];
  console.log(arr12.join()); // green,blue,pink 默认情况逗号
  console.log(arr12.join(-));// green-blue-pink
  console.log(arr12.join(&));// green&blue&pink
```

## 9. 连接数组，返回新数组 concat()

concat() 连接两个或者多个数组，不影响原数组
return 👉 返回一个新的数组

```javascript
<script>
var parents = ["Jani", "Tove"];
var brothers = ["Stale", "Kai Jim", "Borge"];
var children = ["Cecilie", "Lone"];
var family = parents.concat(brothers, children); // family is an object
document.write(family); // Jani,Tove,Stale,Kai Jim,Borge,Cecilie,Lone
</script>
```
## 10. 数组截取 slice()

slice(begin,end)
return 👉 返回被截取的新数组

```javascript
// 包含begin 不包含end 类似于python里面的切片，(1,3)表明从1开始取，取到3之前
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
	var citrus = fruits.slice(1,3);
  console.log(typeof citrus);// object
  console.log(citrus);
}
myFunction() // Orange,Lemon
</script>
```
## 11. 数组删除 splice()

splice(从第几个开始,要删除几个,要添加的item1,要添加的item2,要添加的item3) 《splice 铰接 粘接》
return 👉 返回被删除后的新数组，✨原数组改变✨

```javascript
// 1. 删除一些items
var fruits1 = ["Banana", "Orange", "Apple", "Mango"];
fruits1.splice(2,1,"Lemon","Kiwi");// fruits 输出结果：Banana,Orange,Lemon,Kiwi,Mango

var fruits2 = ["Banana", "Orange", "Apple", "Mango"];
fruits2.splice(2,2); // fruits 输出结果：Banana,Orange

// 2. 添加一些items
var fruits3 = ["Banana", "Orange", "Apple", "Mango"];
fruits3.splice(2,0,"Lemon","Kiwi"); // fruits 输出结果：Banana,Orange,Lemon,Kiwi,Apple,Mango

// 3. 删除0个
如果删除一个元素，则返回一个元素的数组。 如果未删除任何元素，则返回空数组。
var fruits4 = ["Banana", "Orange", "Apple", "Mango"];
zero = fruits4.splice(2, 0);// 不做任何操作
console.log(zero);// 返回空数组
console.log(fruits4);// fruit4 本身不变
console.log(typeof fruits4); // object
```
# String

对象才有属性和方法，为啥字符串这种简单数据类型有length属性呢

```javascript
var str = 'andy';
console.log(str.length);
```

基本包装类型：把简单数据类型包装成了复杂数据类型

```javascript
// 1. 把简单数据类型包装成了复杂数据类型
var temp = new String('andy');
// 2. 把临时变量给str
str = temp;
// 3. 删除临时变量
temp = null;
```

String, Numer, Boolean都可进行包装

## 使用字符串的不可变

当字符串的内容改变时，字符串指针指向新的内容（新地址），原地址上的内容没有被销毁

故不要大量使用拼接字符串

## 查找字符位置

str.indexOf('要查找的字符', [起始位置])

lastIndexOf(数组元素)，从后面往前查找

```javascript
var str = '一条大河波浪宽，两条大河波浪窄';
console.log(str.indexOf('大'));
console.log(str.indexOf('大', 4)); //从索引号位置4开始往后查找，前面的大被略过了

```

某个字符出现的位置以及次数

算法：先找出第一个字符出现的位置，然后indexOf()得到其位置，如果不是-1就往下继续查找，但是开始查找的索引号需在其位置上➕:one:

```javascript
var str11 = 'oabceofoxyozzopp';
var index = str11.indexOg('o');
var num = 0;
while (index == -1) {
  console.log(index);
  index = str11.indexOf('o', index + 1);
  num++;
}
console.log('出现次数' + num);
```

## 根据位置返回字符（重点）

| 方法名            | 说明                                       | 使用 |
| ----------------- | ------------------------------------------ | ---- |
| charAt(index)     | 返回指定位置的字符（index字符串的索引号）  |      |
| charCodeAt(index) | 获取指定位置处字符的ASCII码（index索引号） |      |
| str[index]        | 获取指定位置处字符                         |      |

1. charAt(index) 根据位置返回字符  

   ```javascript
   // 根据位置返回字符
   var str = 'andy';
   console.log(str.charAt(3)); //y
   // 遍历所有的字符
   far (var i=0; i< str.length; i++) {
     console.log(str.charAt(i));
   }
   ```

2. charCodeAt(index) 返回相应的索引号的字符的ASCII值，目的：判断用户按下了**哪个键**

   ```javascript
   console.log(str.charCodeAt(0)) // 97
   ```

3. Str[i] H5新增  

   ```javascript
   str[0] // a
   ```

## 返回字符串位置

判断一个字符串'abcoefoxyozzopp'中出现次数最多的字符，并统计其次数

算法：

1. 利用charAt() 遍历这个字符串
2. 把每个字符都存储给对象，如果对象没有该属性，就赋值为:one:，如果存在了就➕ :one:
3. 遍历对象，得到最大值和该字符
```javascript
  var str = 'abcoefoxyozzopp';
  var o = {}; // 字面量创建空对象
  for (i=0;i<str.length;i++) {
    var chars = str.charAt(i);
    if (o.[chars]) {
      o.[chars]++; //创建并赋值
    }else {
      o.[chars] = 1;
    }
  }

  // 遍历对象
  var max = 0;
  var ch = '';
  for (var k in o) {
    // k 为属性名
    // o[k]为属性值
    if (o[k] > max) {
      max = o[k];
      ch = k;
    }

  }
```
## 字符串操作方法

### 字符串连接 concat()

`concat('串1','串2','串3');` 返回一个新数组

### substr()

### 字符串截取substring()

### 字符串截取 slice()

### 字符串替换replace()

### 字符串转为数组split()

### toUpperCase()

### toLowercase()



