# 30s-code 学习笔记

天赋异禀的人不可怕，一直在持续进步的人才可怕

## Array

1. [unzipWith](Js/Array/unzipWith.md) 创建一个元素数组，将zip生成的数组中的元素解组并应用提供的函数。 
2. [unzip](Js/Array/unzip.md) 创建数组的数组，将zip生成的数组中的元素取消分组。
3. [JSONtoCSV](Js/Array/JSONtoCSV.md) 将对象数组转换为仅包含columns指定对象的逗号分隔值 (CSV) 字符串。
4. [countBy](Js/Array/countBy.md) 根据给定的函数对数组的元素进行分组，并返回每个组中元素的计数。
5. [groupBy](Js/Array/groupBy.md) 根据给定的函数对数组的元素进行分组。
6. [indexBy](Js/Array/indexBy.md) 从数组创建一个对象，使用函数将每个值映射到一个键。
7. [reduceFilter](Js/Array/reduceFilter.md) 根据条件过滤对象数组，同时过滤未指定的键。
8. [mapObject](Js/Array/mapObject.md) 使用函数将数组的值映射到对象。
9. [bifurcateBy](Js/Array/bifurcateBy.md) 根据给定过滤函数的结果将值分成两组。
10. [mostFrequent](Js/Array/mostFrequent.md) 返回数组中出现频率最高的元素。
11. [indexOn](Js/Array/indexOn.md) 从数组创建一个对象，使用指定的键并将其从每个值中排除。
12. [partition](Js/Array/partition.md) 根据所提供的函数对每个元素的真实性，将元素分组为两个数组。
13. [findLastIndex](Js/Array/findLastIndex.md) 查找提供的函数为其返回真值的最后一个元素的索引。
14. [frequencies](Js/Array/frequencies.md) 以数组的唯一值作为键，以其频率作为值创建一个对象。
15. [remove](Js/Array/remove.md) 通过删除给定函数返回`false`的元素来改变数组。
16. [symmetricDifferenceBy](Js/Array/symmetricDifferenceBy.md) 将提供的函数应用于两个数组的每个元素后，返回两个数组之间的对称差值。
17. [orderBy](Js/Array/orderBy.md) 对对象数组进行排序，按属性和顺序排序。
18. [pull](Js/Array/pull.md) 改变原始数组以过滤指定的值。
19. [pullAtIndex](Js/Array/pullAtIndex.md) 改变原始数组以过滤掉指定索引处的值。返回移除的元素。
20. [takeRightUntil](Js/Array/takeRightUntil.md) 从数组末尾移除元素，直到传递的函数返回`true`。返回移除的元素。
21. [takeRightWhile](Js/Array/takeRightWhile.md) 从数组末尾移除元素，直到传递的函数返回`false`。返回移除的元素。
22. [averageBy](Js/Array/averageBy.md) 在使用提供的函数将每个元素映射到一个值之后，计算数组的平均值。
23. [bifurcate](Js/Array/bifurcate.md) 根据给定`filter`数组的结果将值分成两组。
24. [merge](Js/Array/merge.md) 用两个或多个对象的组合创建一个新对象。
25. [orderWith](Js/Array/merge.md) 根据所提供的顺序数组对由属性排序的对象数组排序。
26. [partitionBy](Js/Array/merge.md) 适用`fn`于中的每个值`arr`，每次提供的函数返回新值时将其拆分。
27. [sumBy](Js/Array/sumBy.md) 在使用提供的函数将每个元素映射到一个值之后，计算数组的总和。

## Object 

1. [get](Js/Object/get.md) 从对象中检索由给定选择器指示的一组属性。
2. [compactObject](Js/Object/compactObject.md) 从对象或数组中移除所有错误值。

## Browser

1. [getURLParameters](Js/Browser/getURLParameters.md) 创建一个包含当前 URL 参数的对象。
