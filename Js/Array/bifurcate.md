# bifurcate

## 思路

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