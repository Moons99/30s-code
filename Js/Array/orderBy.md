# orderBy

按属性和顺序对对象数组进行排序。

## 思路
- 用途`Array.prototype.sort()`，`Array.prototype.reduce()`在上`props`有一个默认值阵列`0`。
- 使用数组解构根据提供的顺序交换属性位置。
- 如果未`orders`提供数组，则`'asc'`默认排序。

## code
```js
const orderBy = (arr, props, orders) =>
  [...arr].sort((a, b) =>
    props.reduce((acc, prop, i) => {
      if (acc === 0) {
        const [p1, p2] =
          orders && orders[i] === 'desc'
            ? [b[prop], a[prop]]
            : [a[prop], b[prop]];
        acc = p1 > p2 ? 1 : p1 < p2 ? -1 : 0;
      }
      return acc;
    }, 0)
  );
```

## examples
```js
const users = [
  { name: 'fred', age: 48 },
  { name: 'barney', age: 36 },
  { name: 'fred', age: 40 },
];
orderBy(users, ['name', 'age'], ['asc', 'desc']);
// [{name: 'barney', age: 36}, {name: 'fred', age: 48}, {name: 'fred', age: 40}]
orderBy(users, ['name', 'age']);
// [{name: 'barney', age: 36}, {name: 'fred', age: 40}, {name: 'fred', age: 48}]
```
