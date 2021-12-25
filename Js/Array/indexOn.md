# indexOn

从数组创建一个对象，使用指定的键并将其从每个值中排除。

## 思路
- 用于`Array.prototype.reduce()`从`arr`.
- 使用对象解构来获取给定`key`和关联`data`的值，并将键值对添加到对象中。

## code

```js
const indexOn = (arr, key) =>
  arr.reduce((acc, v) => {
    const {[key]: id, ...data} = v
    acc[id] = data
    return acc
  }, {})

```

## examples

```js
indexOn([
  {id: 10, name: 'apple'},
  {id: 20, name: 'orange'}
], 'id');
// { '10': { name: 'apple' }, '20': { name: 'orange' } }
```
