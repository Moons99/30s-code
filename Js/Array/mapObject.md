# mapObject

使用函数将数组的值映射到对象。

## 思路

- 使用`Array.prototype.reduce()`适用`fn`于每个元素`arr`和合并结果为对象。
- 使用`val`为重点，每个属性和的结果`fn`作为值。
## code
```js
const mapObject = (arr, fn) =>
   arr.reduce((acc, val) =>{
     acc[val] = fn(val)
     return acc
  },{})

```

## examples
```js
mapObject([1, 2, 3], a => a * a); // { 1: 1, 2: 4, 3: 9 }
```
