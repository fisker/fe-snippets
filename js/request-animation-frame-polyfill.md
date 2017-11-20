# requestAnimationFrame polyfill

```js
var requestAnimationFrame = window.requestAnimationFrame ||
  window.mozRequestAnimationFrame ||
  window.webkitRequestAnimationFrame ||
  function (callback) {
    return window.setTimeout(callback, 16)
  }
```

```js
var cancelAnimationFrame = window.cancelAnimationFrame ||
  window.mozCancelAnimationFrame ||
  window.webkitCancelAnimationFrame ||
  window.webkitCancelRequestAnimationFrame ||
  window.clearTimeout
```
