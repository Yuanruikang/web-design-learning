# 函数
# 声明函数
```javascript
  function sayhi() {
    语句；
  }
```
1. function 关键字小写
2. 函数名一般用动词
3. 函数声明后不调用不执行
```javascript
  sayhi(); // 小括号必须
```
## 匿名函数
在声明函数时，function后面没有变量名
```javascript
  var fun = function() {
    console.log('xxx');
  }
  fun();
```
# 函数参数
形式参数+实际参数
* 在声明函数时，小括号里的参数为形式参数
* 在调用函数时，小括号里的参数为实际参数
**注意：**
1. 如果实参个数和行参个数一致，则正常输出结果
2. 如果实参个数 > 行参个数，会取到行参的个数
3. 如果实参个数 < 行参个数，多余行参会被定义为undefined，最终结果是NaN  
   行参可以看作是不用声明的变量，而这个变量没有值时却被直接使用就会undedined
```javascript
  function getArrMax(arr) { //形式参数为数组
    for (var i=1; i<=arr.length;i++){
    if (arr[i] > max) {
      max = arr[i];
    }
  }
  return max;
  }
  //实际参数可以为一个数组
  var re= getArrMax([1,2,3,45435,5365,643534,4354])
```
# return 
1. 如果函数需要返回参数，则需用通过return实现
2. 当函数遇到rerurn后，函数后面的内容就不会再执行了
3. 如果return有多个参数，那么return只会返回最后一个值num2
```javascript
  function fn(num1, num2) {
    return num1, num2; //返回的结果是最后一个值
  }
```
4. return只能返回一个值，如果要返回多个值，可以使用数组的形式
5. 当函数没有return时，返回undefined
# arguments
当我们不确定有多少个参数要传递进函数时，可以使用函数的内置对象arguments，其存储了传递的所有实参

arguments为一个**伪数组**，具有一下特点：
- 有length属性
- 可以按索引方式储存数据
- 但不具有数组的push和pop等方法
- 在声明函数时，其不需要写在形式参数框里function f-name()
```javascript
  function fn() {
    console.log(arguments);
    console.log([2]);
    //可以遍历
    for (var i=0;i<arguments.length ; i++) {
      console.log(arguments[i]);
    }
  }
```