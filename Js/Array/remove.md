# remove

通过删除给定函数返回`false`的元素来改变数组。

## 思路

- 使用`Array.prototype.filter()`发现数组元素返回`truthy`值。
- 用于使用`Array.prototype.reduce()`删除元素`Array.prototype.splice()`。
- 使用三个参数（值、索引、数组）调用回调函数。

## code

```js
const remove = (arr, fn) =>
  Array.isArray(arr)
    ? arr.filter(fn).reduce((acc, val) => {
      arr.splice(arr.indexOf(val), 1)
      return acc.concat(val)
    }, [])
    : []
```

## example

```js
remove([1, 2, 3, 4], n => n % 2 === 0); // [2, 4]
```
