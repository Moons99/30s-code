# bifurcate

根据给定`filter`数组的结果将值分成两组。

## 思路
- 使用`Array.prototype.reduce()`和`Array.prototype.push()`将元素添加到组中，基于filter.
- 如果`filter`任何元素具有真值，则将其添加到第一组，否则将其添加到第二组。
## code

```javascript
const bifurcate = (arr, filter) =>
  arr.reduce((acc, val, i) => (acc[filter[i] ? 0 : 1].push(val), acc), [
    [],
    [],
  ]);
```

## examples

```javascript
bifurcate(['beep', 'boop', 'foo', 'bar'], [true, true, false, true]);
// [ ['beep', 'boop', 'bar'], ['foo'] ]
```