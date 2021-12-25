# findLastIndex

查找提供的函数为其返回真值的最后一个元素的索引。

## 思路

- 用于`Array.prototype.map()`将每个元素映射到具有其索引和值的数组。
- 使用`Array.prototype.filter()`删除元素为其`fn`返回`falsy`值
- 使用`Array.prototype.pop()`获得的最后一个元素的过滤阵列英寸
- `-1`如果没有匹配的元素，则返回。

## code

```js
const findLastIndex = (arr, fn) =>
  (arr
    .map((val, i) => [i, val])
    .filter(([i, val]) => fn(val, i, arr))
    .pop() || [-1])[0];
```

## examples

```js
findLastIndex([1, 2, 3, 4], n => n % 2 === 1); // 2 (index of the value 3)
findLastIndex([1, 2, 3, 4], n => n === 5); // -1 (default value when not found)
```
