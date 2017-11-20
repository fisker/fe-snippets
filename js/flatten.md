# flatten

```js
var reduce = Array.prototype.reduce ||
  function(callback, initialValue) {
    var len = arr.length
    var i = 0
    var value
    if (arguments.length >= 2) {
      value = initialValue
    } else {
      if (len === 0) {
        throw new TypeError('Reduce of empty array with no initial value')
      } else {
        value = this[0]
      }
    }

    while (i < len) {
      value = callback(value, this[i], i, this)
      i++
    }

    return value
  }

var flatten = function flatten(arr) {
  return reduce.call(arr, function(acc, current) {
    return acc.concat(current)
  }, [])
}

var isArray = Array.isArray ||
  function(x) {
    return Object.prototype.toString.call(x) === '[object Array]'
  }

var flattenDeep = function flattenDeep(arr) {
  return reduce.call(arr, function(acc, current) {
    return acc.concat(isArray(current) ? flatten(current) : current)
  }, [])
}
```