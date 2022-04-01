## Deep merge objects(深度合并对象)

深度合并两个对象，使用一个函数来处理两者中存在的键。

### 思路

- 用于`Object.keys()`获取两个对象的键，`Set`从它们创建一个并使用扩展运算符 ( `...` ) 创建一个包含所有唯一键的数组。
- 用于`Array.prototype.reduce()`将每个唯一键添加到对象，`fn`用于组合两个给定对象的值。

### code
```js
const deepMerge = (a, b, fn) =>
    [...new Set([...Object.keys(a), ...Object.keys(b)])].reduce(
        (acc, key) => ({ ...acc, [key]: fn(key, a[key], b[key]) }),
        {}
    );
```

### examples
```js
deepMerge(
  { a: true, b: { c: [1, 2, 3] } },
  { a: false, b: { d: [1, 2, 3] } },
  (key, a, b) => (key === 'a' ? a && b : Object.assign({}, a, b))
);
// { a: false, b: { c: [ 1, 2, 3 ], d: [ 1, 2, 3 ] } }
```