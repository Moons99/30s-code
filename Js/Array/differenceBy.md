# differenceBy

在将提供的函数应用于两个数组的每个数组元素后，返回两个数组之间的差异。

## 思路

- `Set`通过应用`fn`到中的每个元素来创建一个`b`。
- 用于`Array.prototype.map()`应用于`fn`中的每个元素`a`。
- 与`onArray.prototype.filter()`结合使用，仅保留,中未包含的值。`fn a b Set.prototype.has()`

## code

```js
const differenceBy = (a, b, fn) => {
    const s = new Set(b.map(fn));
    return a.map(fn).filter(el => !s.has(el));
};
```

## examples

```js
differenceBy([2.1, 1.2], [2.3, 3.4], Math.floor); // [1]
differenceBy([{x: 2}, {x: 1}], [{x: 1}], v => v.x); // [2]
```