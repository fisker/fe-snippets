# nice

```js
function nice(val, round) {
  var exponent = Math.floor(Math.log(val) / Math.LN10)
  var exp10 = Math.pow(10, exponent)
  var f = val / exp10 // 1 <= f < 10
  var nf
  if (round) {
    if (f < 1.5) {
      nf = 1
    } else if (f < 2.5) {
      nf = 2
    } else if (f < 4) {
      nf = 3
    } else if (f < 7) {
      nf = 5
    } else {
      nf = 10
    }
  } else {
    if (f < 1) {
      nf = 1
    } else if (f < 2) {
      nf = 2
    } else if (f < 3) {
      nf = 3
    } else if (f < 5) {
      nf = 5
    } else {
      nf = 10
    }
  }
  val = nf * exp10

  // Fix 3 * 0.1 === 0.30000000000000004 issue (see IEEE 754).
  // 20 is the uppper bound of toFixed.
  return exponent >= -20 ? +val.toFixed(exponent < 0 ? -exponent : 0) : val
}

```
see:

https://stackoverflow.com/questions/8506881/nice-label-algorithm-for-charts-with-minimum-ticks
https://github.com/ecomfe/echarts/blob/d59b0c4aa39f43ef95700e253b3d6d27a9a4fb80/src/util/number.js#L356
https://github.com/chartjs/Chart.js/blob/e080e782ab44f34d2bcd63ad6255f48bac2292ea/src/core/core.helpers.js#L331