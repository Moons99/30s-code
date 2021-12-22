# reduceFilter

根据条件过滤一组对象，同时过滤掉未指定的键。

## 思路
- 用于`Array.prototype.filter()`根据谓词过滤数组，fn以便它返回条件返回真值的对象。
- 在过滤后的数组上，使用`Array.prototype.map()`返回新对象。
- 使用`Array.prototype.reduce()`过滤掉哪些不为所提供的关键`keys`参数。
## code
```js
const reducedFilter = (data, keys, fn) =>
  data.filter(fn).map(el =>
    keys.reduce((acc, key) => {
      acc[key] = el[key];
      return acc;
    }, {})
  );
```

## examples
```js
const data = [
  {
    id: 1,
    name: 'john',
    age: 24
  },
  {
    id: 2,
    name: 'mike',
    age: 50
  }
];
reducedFilter(data, ['id', 'name'], item => item.age > 24);
// [{ id: 2, name: 'mike'}]
```
