# unzip

创建数组的数组，将zip生成的数组中的元素取消分组。

## 思路

- 使用`Math.max()`,`Function.prototype.apply()`获取数组中最长的子数组，`Array.prototype.map()`使每个元素成为一个数组。
- 使用`Array.prototype.reduce()`和`Array.prototype.forEach()`将分组值映射到单个数组。

## code
```js
const unzip = (arr) => 
  arr.reduce((acc,val) =>{
      val.forEach((v,i) => acc[i].push(v))
      return acc
    },
    Array.from({
      length: Math.max(...arr.map(v => v.length))
    }).map(v => [])
  )
```

## 测试用例
```js
unzip([['a', 1, true], ['b', 2, false]]); // [['a', 'b'], [1, 2], [true, false]]
unzip([['a', 1, true], ['b', 2]]); // [['a', 'b'], [1, 2], [true]]
```
