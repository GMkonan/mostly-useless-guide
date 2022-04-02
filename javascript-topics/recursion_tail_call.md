## Recursion tail call

```js
const recur = n => acc =>  n == 0 ? acc : recur(n-1)(n * acc)
```