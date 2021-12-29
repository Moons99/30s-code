# pull

改变原始数组以过滤指定的值。

## 思路

- 使用`Array.prototype.filter()`和`Array.prototype.includes()`提取不需要的值。
- 设置`Array.prototype.length`为通过将数组的长度重置为 来改变传入的数组`0`。
- 用于`Array.prototype.push()`仅使用提取的值重新填充它。

## code

```js
const pull = (arr, ...args) => {
  let argState = Array.isArray(args[0]) ? args[0] : args;
  let pulled = arr.filter(v => !argState.includes(v));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
};
```

## examples

```js
let myArray = ['a', 'b', 'c', 'a', 'b', 'c'];
pull(myArray, 'a', 'c'); // myArray = [ 'b', 'b' ]
```
