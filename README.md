# Compute Program

这是一个计算程序，灵感来自《南方新中考·数学》中的一道题。我使用前端技术实现了它


## 实现该程序的算法

```js
function computeProgram(x, count) {
  for (let i = 1; i <= count; i++) {
    if (x != 1) {
      x /= 5
    } else if (x == 1) {
      x += 4
    }
  }
}
```