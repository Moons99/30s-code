# unzipWith

创建一个元素数组，将`zip`生成的数组中的元素解组并应用提供的函数。

## 思路
- 使用`Math.max()`,`Function.prototype.apply()`获取数组中最长的子数组，`Array.prototype.map()`使每个元素成为一个数组。
- 使用`Array.prototype.reduce()`和`Array.prototype.forEach()`将分组值映射到单个数组。
- 使用`Array.prototype.map()`和 展开运算符 ( `...` ) 应用于`fn`每个单独的元素组。

## code
```js
const unzipWith = (arr, fn ) =>
  arr
    .reduce(
      (acc,val) => (val.forEach((v, i) =>acc[i].push(v)), acc),
      Array.from({
      length: Math.max(...arr.map(x => x.length))
      }).map(x => [])
    )
    .map(val => fn(...val))
```

## example
```js
unzipWith(
  [
    [1, 10, 100],
    [2, 20, 200],
  ],
  (...args) => args.reduce((acc, v) => acc + v, 0)
);
// [3, 30, 300]
```
