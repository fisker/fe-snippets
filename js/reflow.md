# reflow

```js
function reflow(element) {
  void (element || document.documentElement).offsetWidth
}
```

speed https://jsperf.com/reflow-speed