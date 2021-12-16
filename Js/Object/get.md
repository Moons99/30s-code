# get

从对象中检索由给定选择器指示的一组属性。

## 思路
- 使用`Array.prototype.map()`的每个选择，`String.prototype.replace()`用点来代替方括号。
- 使用`String.prototype.split('.')`到各选择拆分。
- 使用`Array.prototype.filter()`删除空值，并`Array.prototype.reduce()`获得价值由每个选择指示。

## code
```js
const get = (from, ...selectors) =>
  [...selectors].map(s =>
    s
      .replace(/\[([^\[\]]*)\]/g, '.$1.')
      .split('.')
      .filter(t => t !== '')
      .reduce((prev, cur) => prev && prev[cur], from)
  );
```

## examples
```js
const obj = {
  selector: { to: { val: 'val to select' } },
  target: [1, 2, { a: 'test' }],
};
get(obj, 'selector.to.val', 'target[0]', 'target[2].a');
// ['val to select', 1, 'test']
```
