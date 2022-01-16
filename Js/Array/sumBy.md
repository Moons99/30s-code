# sumBy

在使用提供的函数将每个元素映射到一个值之后，计算数组的总和。

## 思路

用于`Array.prototype.map()`将每个元素映射到`fn`.
用于`Array.prototype.reduce()`将每个值添加到累加器，初始化为`0`.

## code

```javascript
const sumBy = (arr, fn) =>
    arr
        .map(typeof fn === 'function' ? fn : val => val[fn])
        .reduce((acc, val) => acc + val, 0)
```

## examples

```javascript
sumBy([{n: 4}, {n: 2}, {n: 8}, {n: 6}], x => x.n); // 20
sumBy([{n: 4}, {n: 2}, {n: 8}, {n: 6}], 'n'); // 20
```