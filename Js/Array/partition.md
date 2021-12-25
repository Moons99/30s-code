# partition

根据所提供的函数对每个元素的真实性，将元素分组为两个数组。

## 思路

- 使用`Array.prototype.reduce()`以创建两个数组的数组。
- 使用`Array.prototype.push()`针对其元素添加`fn`返回`true`到所述第一阵列和用于该元件`fn`返回`false`到第二个。

## code

```js
const partition = (arr, fn) =>
  arr.reduce((acc, val, i) => {
    acc[fn(val, i) ? 0 : 1].push(val) 
    return acc
  }, [[], []])

```

## examples

```js
const users = [
  {user: 'barney', age: 36, active: false},
  {user: 'fred', age: 40, active: true},
];
partition(users, o => o.active);
// [
//   [{ user: 'fred', age: 40, active: true }],
//   [{ user: 'barney', age: 36, active: false }]
// ]
```
