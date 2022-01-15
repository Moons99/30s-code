# partitionBy

适用`fn`于中的每个值`arr`，每次提供的函数返回新值时将其拆分。

## 思路

- 与将`Array.prototype.reduce()`保存结果数组和从`fn`.
- 用于`Array.prototype.push()`将每个值添加`arr`到累加器数组中的相应分区。

## code

```javascript
const partitionBy = (arr, fn) =>
    arr.reduce(
        ({res, last}, v, i, a) => {
            const next = fn(v, i, a)
            if (next !== last) res.push([v])
            else res[res.length - 1].push(v)
            return {res, last: next}
        }, {res: []}
    ).res
```

## examples

```javascript
const numbers = [1, 1, 3, 3, 4, 5, 5, 5];
partitionBy(numbers, n => n % 2 === 0); // [[1, 1, 3, 3], [4], [5, 5, 5]]
partitionBy(numbers, n => n); // [[1, 1], [3, 3], [4], [5, 5, 5]]
```