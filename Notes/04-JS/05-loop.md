# For 
```javascript
  for (var i=1; i<=num; i++){
    var score= prompt('xxxxxxx')
    sum = sum + parseFloat(score);
  }
```
* i<=num比较时，字符串型会自动转换为数值型
* prompt 输入的值需要进行转换，因为prompt输入值默认为字符串
* console.log 默认会换行，如果想在一行输入可以转换为字符串，并在末尾加上'\n'
# while
```javascript
  while (条件表达式){
    语句
  }
```
1. 执行条件表达式，如果结果为true ，则执行循环体代码；如果为 false，则退出循环，执行后面代码
2.  执行循环体代码
3.  循环体代码执行完毕后，程序会继续判断执行条件表达式，如条件仍为true，则会继续执行循环体，直到循环条件为false 时，整个循环过程才会结束
