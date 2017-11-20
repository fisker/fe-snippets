# get ratio for high definition canvas

```js
var ratio = (function(window, document) {
  var devicePixelRatio = window.devicePixelRatio || 1
  var context = document.createElement('canvas').getContext('2d')
  var backingStoreRatio =
    context.webkitBackingStorePixelRatio ||
    context.mozBackingStorePixelRatio ||
    context.msBackingStorePixelRatio ||
    context.oBackingStorePixelRatio ||
    context.backingStorePixelRatio ||
    1
  return devicePixelRatio / backingStoreRatio
})(window, window.document)
```

### ustage

```js
canvas.width = width * ratio
canvas.height = height * ratio
context.scale(ratio, ratio)
```