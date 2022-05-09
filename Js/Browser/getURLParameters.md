# getURLParameters

创建一个包含当前 URL 参数的对象。

## 思路

- 与适当的正则表达式一起使用`String.prototype.match()`以获取所有键值对。
- 用于`Array.prototype.reduce()`将它们映射并组合成一个对象。
- 作为参数传递`location.search`以应用于当前`url`。

## code
```js
const getURLParameters = url =>
    (url.match(/([^?=&]+)(=([^&])*)/g) || []).reduce(
        (a,v)=>{
            a[v.slice(0, v.indexOf('='))] = v.slice(v.indexOf('=')+1)
            return a
        },{})
```

## examples
```js
getURLParameters('google.com'); // {}
getURLParameters('http://url.com/page?name=Adam&surname=Smith');
// {name: 'Adam', surname: 'Smith'}
```