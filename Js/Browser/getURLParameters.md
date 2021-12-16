# getURLParameters

创建一个包含当前 URL 参数的对象。

## 思路

## code
```js
const getURLParameters = url =>
  (url.match(/([^?=&]+)(=([^&]*))/g) || [] ).reduce((acc,v) =>
      (acc[val.slice(0, v.indexOf('='))] = v.slice(v.indexOf('=') + 1),acc)
    ,{})
```

## examples
```js
getURLParameters('google.com'); // {}
getURLParameters('http://url.com/page?name=Adam&surname=Smith');
// {name: 'Adam', surname: 'Smith'}
```
