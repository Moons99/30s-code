# bifurcateBy

根据给定过滤函数的结果将值分成两组。

## 思路

- 使用`Array.prototype.reduce()`和`Array.prototype.push()`根据`fn`每个元素返回的值将元素添加到组中。
- 如果`fn`返回任何元素的真值，则将其添加到第一组，否则将其添加到第二组。

## code
```js
const bifurcateBy = (arr, fn) =>
  arr.reduce((acc, val, i) => 
      (acc[fn(val, i) ? 0 : 1].push(val), acc)
    , [[], []]
  );
```

## examples
```js
bifurcateBy(['beep', 'boop', 'foo', 'bar'], x => x[0] === 'b');
// [ ['beep', 'boop', 'bar'], ['foo'] ]
```
