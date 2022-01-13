# merge

用两个或多个对象的组合创建一个新对象。

## 思路
- 使用`Array.prototype.reduce()`组合`withObject.keys()`来迭代所有对象和键。
- 使用`Object.prototype.hasOwnProperty()`and`Array.prototype.concat()`为多个对象中存在的键附加值。

## code
```javascript
const merge = (...objs) =>
    [...objs].reduce(
        (acc, obj) =>
            Object.keys(obj).reduce((a, k) => {
                acc[k] = acc.hasOwnProperty(k)
                    ? [].concat(acc[k]).concat(obj[k])
                    : obj[k];
                return acc;
            }, {}),
        {}
    );
```

## examples
```javascript
const object = {
  a: [{ x: 2 }, { y: 4 }],
  b: 1
};
const other = {
  a: { z: 3 },
  b: [2, 3],
  c: 'foo'
};
merge(object, other);
// { a: [ { x: 2 }, { y: 4 }, { z: 3 } ], b: [ 1, 2, 3 ], c: 'foo' }
```