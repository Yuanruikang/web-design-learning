# 数组
# 创建数组
## 利用 new 创建数组
```javascript
  var array-name = new Array();
  // creat a array named array-name
  // A in Array() must be capitalized 
```
## 数组字面量创建数组
```javascript
  array-name = [] // creat a empty array
  array-name = ['tom','sam','David'];
  // using comma between array element
```
1. 数组中可以存放任意类型的数据，例如字符串、数字、布尔值等
2. 如果访问了超出下标的数组元素，输出结果为undefined
3. array-name.length 为数组自带属性，可以输出数组的长度（数组元素个数）
# 对数组的操作
## 新增元素
1. 修改length的长度
```javascript
  var arr=['red','green','blue'];
  console.log(arr.length);
  arr.length=5;// 数组元素长度从3增加到5
```
2. 修改索引号，追加数组元素
```javascript
  var arr1 = ['red','green','blue'];
  arr1[3] = 'pink';
  arr1[4] = 'skyblue';
  //修改原来的数组
  arr1[0] = 'yellow';
```
**注意：**
不能直接给数组名赋值
## 筛选数组值
```javascript
  var arr = [2,0,6,1,77,0,53,234,34,67];
  var newArr = [];
  for (var i=0;i<arr.length;i++) {
    if (arr[i] >= 10) {
      newArr[newArr.length] = arr[i];
    }
  }
```
## 冒泡排序
* 外层循环需要arr.length-1次
* 内层需要 arr.length -1 -i (i 从0开始)