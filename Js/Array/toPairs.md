# toPairs

从对象或其他可迭代对象创建键值对数组的数组。

## 思路

- 检查是否`Symbol.iterator`已定义，如果是，则`Array.prototype.entries()`用于获取给定迭代的迭代器。
- 用于`Array.from()`将结果转换为键值对数组的数组。
- 如果`Symbol.iterator`没有为定义`obj`，请`Object.entries()`改用。

## code
```javascript
const toPairs = obj =>
    obj[Symbol.iterator] instanceof Function && obj.entries instanceof Function
        ? Array.from(obj.entries())
        : Object.entries(obj);
```

## examples

```javascript
toPairs({a: 1, b: 2}); // [['a', 1], ['b', 2]]
toPairs([2, 4, 8]); // [[0, 2], [1, 4], [2, 8]]
toPairs('shy'); // [['0', 's'], ['1', 'h'], ['2', 'y']]
toPairs(new Set(['a', 'b', 'c', 'a'])); // [['a', 'a'], ['b', 'b'], ['c', 'c']]
```