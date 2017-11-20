# now

```js
var now = Data.now ||
  function () {
    return (new Data()).getTime()
  }
```