# groupBy 

根据给定的函数对数组的元素进行分组。

## 思路
- 用于`Array.prototype.map()`将数组的值映射到函数或属性名称。
- 使用`Array.prototype.reduce()`创建一个对象，其中，所述密钥是从映射结果产生的。

## code
```js
const groupBy = (arr, fn) => 
  arr.map(typeof fn ==='function' ? fn : val => val[fn]).reduce((acc, val, i) =>{
    acc[val] = (arr[val] || []).concat(arr[i])
    return acc
  },{})
```

## 测试用例

```js
groupBy([6.1, 4.2, 6.3], Math.floor); // {4: [4.2], 6: [6.1, 6.3]}
groupBy(['one', 'two', 'three'], 'length'); // {3: ['one', 'two'], 5: ['three']}
```
