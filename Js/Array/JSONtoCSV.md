# JSONtoCSV

将对象数组转换为仅包含columns指定对象的逗号分隔值 (CSV) 字符串。

## 思路

- 使用`Array.prototype.join(delimiter)`到所有的名字结合起来，`columns`创造了第一排。
- 使用`Array.prototype.map()`和`Array.prototype.reduce()`为每个对象创建一行。用空字符串替换不存在的值，并且只映射`columns`.
- 使用`Array.prototype.join('\n')`到的所有行合并为一个字符串。
- 省略第三个参数 ,`delimiter`以使用默认分隔符`','`。

## code
```js
const JSONtoCSV = (arr, columns, delimiter = ',') =>
  [
    columns.join(delimiter),
    ...arr.map(obj =>
      columns.reduce(
        (acc, key) =>
          `${acc}${!acc.length ? '' : delimiter}"${!obj[key] ? '' : obj[key]}"`,
        ''
      )
    ),
  ].join('\n');
```

## 测试用例

```js
JSONtoCSV(
  [{ a: 1, b: 2 }, { a: 3, b: 4, c: 5 }, { a: 6 }, { b: 7 }],
  ['a', 'b']
); // 'a,b\n"1","2"\n"3","4"\n"6",""\n"","7"'
JSONtoCSV(
  [{ a: 1, b: 2 }, { a: 3, b: 4, c: 5 }, { a: 6 }, { b: 7 }],
  ['a', 'b'],
  ';'
); // 'a;b\n"1";"2"\n"3";"4"\n"6";""\n"";"7"'
```
