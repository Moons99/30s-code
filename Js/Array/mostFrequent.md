# mostFrequent

返回数组中出现频率最高的元素。

## 思路

- 用于Array.prototype.reduce()将唯一值映射到对象的键，每次遇到相同的值时添加到现有键。
- 使用Object.entries()这一结果与组合Array.prototype.reduce()获得阵列中的最频繁的值。

## code
```js

const mostFrequent = arr =>
  Object.entries(
    arr.reduce((a, v) => {
      a[v] = a[v] ? a[v] + 1 : 1;
      return a;
    }, {})
  ).reduce((a, v) => (v[1] >= a[1] ? v : a), [null, 0])[0];

// 第二个版本 两个出现次数一样的元素
const mostFrequent = arr =>
  Object.entries(
    arr.reduce((a, v) => {
      a[v] = a[v] ? a[v] + 1 : 1;
      return a;
    }, {})
  )
    .reduce((a, v) => {
      const last = a[a.length -1 ][1]
      if (last === v[1]) {
        return  a.concat([v])
      }else {
        return v[1] > last ? [v] : a
      }
    }, [[null, 0]])
    .map(v => v[0])
```

## examples
```js
mostFrequent(['a', 'b', 'a', 'c', 'a', 'a', 'b']); // 'a'
```
