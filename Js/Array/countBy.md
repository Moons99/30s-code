# countBy

根据给定的函数对数组的元素进行分组，并返回每个组中元素的计数。

## 思路

- 用于Array.prototype.map()将数组的值映射到函数或属性名称。
- 使用Array.prototype.reduce()创建一个对象，其中，所述密钥是从映射结果产生的。

## code
```js
const countBy = (arr, fn) => 
  arr.map(typeof fn === 'function' ? fn : val => val[fn]).reduce((acc,val) =>{
    acc[val] = ( acc[val] || 0) + 1
    return acc
  },{})
```

## 测试用例
```js
countBy([6.1, 4.2, 6.3], Math.floor); // {4: 1, 6: 2}
countBy(['one', 'two', 'three'], 'length'); // {3: 2, 5: 1}
countBy([{ count: 5 }, { count: 10 }, { count: 5 }], x => x.count)
// {5: 2, 10: 1}
```
