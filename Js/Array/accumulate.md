# accumulate

创建一个部分和数组。

## 思路

- 使用`Array.prototype.reduce()`, 用空数组累加器初始化来迭代`nums`.
- 用于`Array.prototype.slice()`获取先前的部分总和或`0`将当前元素添加到其中。
- 使用扩展运算符 (`...`) 将新的部分总和添加到包含先前总和的累加器数组中。

## code

```javascript
const accumulate = (...nums) =>
    nums.reduce((acc, n) => [...acc, n + (acc.slice(-1)[0] || 0)], [])
```

## examples

```javascript
accumulate(1, 2, 3, 4); // [1, 3, 6, 10]
accumulate(...[1, 2, 3, 4]); // [1, 3, 6, 10]
```