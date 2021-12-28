# symmetricDifferenceBy

将提供的函数应用于两个数组的每个元素后，返回两个数组之间的对称差值

## 思路

- `new Set()`从每个数组创建一个以在应用fn到每个数组后获取每个数组的唯一值。
- `Array.prototype.filter()`对它们中的每一个使用以仅保留不包含在另一个中的值。

## code

```js
const symmetricDifferenceBy = (a, b, fn) => {
  const sA = new Set(a.map(v => fn(v))),
    sB = new Set(b.map(v => fn(v)));
  return [...a.filter(x => !sB.has(fn(x))), ...b.filter(x => !sA.has(fn(x)))];
};
```

## examples

```js
symmetricDifferenceBy([2.1, 1.2], [2.3, 3.4], Math.floor); // [ 1.2, 3.4 ]
symmetricDifferenceBy(
  [{id: 1}, {id: 2}, {id: 3}],
  [{id: 1}, {id: 2}, {id: 4}],
  i => i.id
);
// [{ id: 3 }, { id: 4 }]
```
