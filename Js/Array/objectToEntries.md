# objectToEntries

从一个对象创建一个键值对数组的数组。

## 思路

- 使用`Object.keys()`and`Array.prototype.map()`遍历对象的键并生成一个带有键值对的数组。
- `Object.entries()`提供类似的功能。

## code

```javascript
const objectToEntries = obj => Object.keys(obj).map(k => [k, obj[k]]);
```

## examples

```javascript
objectToEntries({a: 1, b: 2}); // [ ['a', 1], ['b', 2] ]
```