# descartes

```js
var descartes = (function() {
  function append(current) {
    return this.concat(current)
  }

  function compile(compiled, list) {
    return compiled.reduce(function reducer(acc, values) {
      var current = list.map(append, values)
      return acc.concat(current)
    }, [])
  }

  function filter(values) {
    return Array.isArray(values) && values.length
  }

  function toArray(value) {
    return [value]
  }

  function transform(values) {
    return values.map(toArray)
  }

  function descartes(collection) {
    collection = collection || []
    collection = collection.filter(filter).map(transform)

    return collection.length
      ? collection.reduce(compile)
      : []
  }

  return descartes
})()
```