# toRGBObject

## code

```js
const toRGBObject = rgbStr => {
    const [rgb, r, g, b, a] = rgbStr.match(/([^(,)]+)/g).map(i => Number(i.split(' ').filter(Boolean).join()))
    const RGB = rgbToHex(r, g, b)
    return [`${RGB}`, a]
}

const rgbToHex = (red, green, blue) => `#${[red, green, blue].map((v) => v.toString(16).padStart(2, '0')).join('')}`;
```

## examples

```js
console.log(toRGBObject('rgba(0, 6, 254, 0.1)')); //[ '#0006fe', 0.1 ]
```