# zipObject

将属性与值关联，给定有效的属性标识符数组和值数组。

## 思路

- 用于`Array.prototype.reduce()`从两个数组构建对象。
- 如果`props`的长度大于`values`，剩余的键将是`undefined`。
- 如果`values`的长度大于`props`，剩余的值将被忽略。

## code

```javascript
const zipObject = (props, values) =>
    props.reduce((obj, prop, index) => ((obj[prop] = values[index]), obj), {});
```

## examples

```javascript
zipObject(['a', 'b', 'c'], [1, 2]); // {a: 1, b: 2, c: undefined}
zipObject(['a', 'b'], [1, 2, 3]); // {a: 1, b: 2}
```