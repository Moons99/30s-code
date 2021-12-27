# frequencies

以数组的唯一值作为键，以其频率作为值创建一个对象。

## 思路
- 使用`Array.prototype.reduce()`将唯一的值映射到对象的键，每次遇到相同的值时都添加到现有的键。

## code

```js
const frequencies = arr =>
  arr.reduce((acc, val) => {
    acc[val] = acc[val] ? acc[val] + 1 : 1
    return acc
  }, {})
```

## examples

```js
frequencies(['a', 'b', 'a', 'c', 'a', 'a', 'b']); // { a: 4, b: 2, c: 1 }
frequencies([...'ball']); // { b: 1, a: 1, l: 2 }
```
