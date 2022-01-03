# pullAtIndex

改变原始数组以过滤掉指定索引处的值。返回移除的元素。

## 思路
- 使用Array.prototype.filter()和Array.prototype.includes()提取不需要的值。
- 设置Array.prototype.length为通过将数组的长度重置为 来改变传入的数组0。
- 用于Array.prototype.push()仅使用提取的值重新填充它。
- 用于Array.prototype.push()跟踪拉取值。

## code
```js
const pullAtIndex = (arr, pullArr) => {
  let removed = [];
  let pulled = arr
    .map((v, i) => (pullArr.includes(i) ? removed.push(v) : v))
    .filter((v, i) => !pullArr.includes(i));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
  return removed;
};

```

## examples
```js
let myArray = ['a', 'b', 'c', 'd'];
let pulled = pullAtIndex(myArray, [1, 3]);
// myArray = [ 'a', 'c' ] , pulled = [ 'b', 'd' ]
```
