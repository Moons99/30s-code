# indexBy

从数组创建一个对象，使用函数将每个值映射到一个键。

## 思路
- 用于`Array.prototype.reduce()`从`arr`.
- 应用于`fn`每个值`arr`以生成一个键并将键值对添加到对象中。

## code
```js
const indexBy = (arr, fn) => 
  arr.reduce((obj, v, i) =>{
    obj[fn(v, i)] = v
    return obj
  },{})
```

## 测试用例
```js
indexBy([
  { id: 10, name: 'apple' },
  { id: 20, name: 'orange' }
], x => x.id);
// { '10': { id: 10, name: 'apple' }, '20': { id: 20, name: 'orange' } }  
```
