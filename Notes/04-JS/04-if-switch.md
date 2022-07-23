# 流程控制
顺序结构+分支结构+循环结构
# if
```javascript
  if (true) {
    语句;
  }
  
  if (true) {
    语句;
  } else {
    语句;
  }
  
  if (true) {
    语句;
  } else if (true) {
    语句;
  } else if (true) {
    语句;
  } else {
    
  }
```
# 三元运算符
```javascript
条件表达式?表达式1:表达式2
```
如果条件表达式成立，则返回表达式:one:的值，否则返回表达式:two:的值
使用三元表达式可以精简代码结构，避免使用if-else结构
# switch
```javascript
  switch (表达式) {
    case 选项值:
        语句;
        break;
    case 选项值:
        语句;
        break;
    case 选项值:
        语句;
        break;
    default:
        语句;
  }
```
**注意：**
1. 表达式与case里的选项值必须全等（===）才能被匹配上，即值和数据类型必须完全一致
2. 如果当前case里没有break，则会执行下一个case
# switch 语句和 ifelse if 语句的区别
1. 一 般情况下，它们两个语句可以相互替换
2. switch...case 语句通常处理case为比较确定值的情况，而 if..else..语句更加灵活，常用于范围判断(大于、等于某个范围）
3. switch 语句进行条件判断后直接执行到程序的条件语句 ，效率更高。而if..else 语句有几种条件，就得判断多少次。
4. 当分支比较少时，it.else语句的执行效率比switch语句高。
5. 当分支比较多时，switch语句的执行效率比较高，而且结构更清晰。