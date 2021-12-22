# compactObject

从对象或数组中移除所有错误值。

## 思路
- 使用递归。
- 初始化可迭代数据，使用`Array.isArray()`,`Array.prototype.filter()`和`Booleanfor` 数组以避免稀疏数组。
- 使用`Object.keys()`和`Array.prototype.reduce()`以适当的初始值迭代每个键。
- 使用`Boolean`以确定每个键的值的感实性，如果它的`truthy`它添加到累加器。
- 使用`typeof`来确定给定值是`object`和再次调用该函数深入压缩它。

## code
```js
const compactObject = val => {
  const data = Array.isArray(val) ? val.filter(Boolean) : val;
  return Object.keys(data).reduce(
    (acc, key) => {
      const value = data[key];
      if (Boolean(value))
        acc[key] = typeof value === 'object' ? compactObject(value) : value;
      return acc;
    },
    Array.isArray(val) ? [] : {}
  );
};
```

## examples
```js
const obj = {
  a: null,
  b: false,
  c: true,
  d: 0,
  e: 1,
  f: '',
  g: 'a',
  h: [null, false, '', true, 1, 'a'],
  i: { j: 0, k: false, l: 'a' }
};
compactObject(obj);
// { c: true, e: 1, g: 'a', h: [ true, 1, 'a' ], i: { l: 'a' } }
```
