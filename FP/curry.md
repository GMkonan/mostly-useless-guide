# Currying
Currying is a technique used to make a function with multiple parameters transform into a series of functions that receive one parameter each. For example:

```js
const add = x => y => x + y;
const increment = add(1);
const addTen = add(10);

increment(2); // 3
addTen(2); // 12
```
The subsequent functions remember the first argument via [closure](https://simple.wikipedia.org/wiki/Closure_(computer_science)#:~:text=In%20computer%20science%2C%20a%20closure,between%20uses%20of%20the%20closure.&text=A%20named%20closure%20is%20not%20anonymous.).

This is a pretty simple concept yet is pretty powerful in the functional programming world.
### Useful Links
- [Professor Frisby's book chapter 4](https://mostly-adequate.gitbook.io/mostly-adequate-guide/ch04)
- [Currying wikipedia](https://pt.wikipedia.org/wiki/Currying)
- [Closure wikipedia](https://simple.wikipedia.org/wiki/Closure_(computer_science)#:~:text=In%20computer%20science%2C%20a%20closure,between%20uses%20of%20the%20closure.&text=A%20named%20closure%20is%20not%20anonymous.)
- [functional JS closures](https://medium.com/dailyjs/functional-js-4-closures-30b4ee8853c9)