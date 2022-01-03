# takeRightUntil

从数组末尾移除元素，直到传递的函数返回true。返回移除的元素。

## 思路

- 使用展开运算符 `( ...)` 和来创建数组的反向副本Array.prototype.reverse()。
- 循环遍历反向副本，使用`for...of`循环`Array.prototype.entries()`直到函数的返回值为真。
- 使用 返回已删除的元素`Array.prototype.slice()`。
- 回调函数`fn`接受单个参数，即元素的值。

## code
```js
const takeRightUntil = (arr, fn) => {
  for (const [i, val] of [...arr].reverse().entries())
    if (fn(val)) return i === 0 ? [] : arr.slice(-i);
  return arr;
};
```

## examples
```js
takeRightUntil([1, 2, 3, 4], n => n < 3); // [3, 4]
```
