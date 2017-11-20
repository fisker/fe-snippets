# cancelAnimationFrame
** there is no ms/o verdor prefix **

```js
var cancelAnimationFrame = window.cancelAnimationFrame ||
  window.mozCancelAnimationFrame ||
  window.webkitCancelAnimationFrame ||
  window.webkitCancelRequestAnimationFrame ||
  window.clearTimeout
```
