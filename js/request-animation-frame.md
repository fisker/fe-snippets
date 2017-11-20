# requestAnimationFrame

** there is no ms/o verdor prefix **

```js
var requestAnimationFrame = window.requestAnimationFrame ||
  window.mozRequestAnimationFrame ||
  window.webkitRequestAnimationFrame ||
  function (callback) {
    return window.setTimeout(callback, 16)
  }
```
