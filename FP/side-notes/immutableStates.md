```js
// impure
let minimum = 21;
const checkAge = (age) => age >= minimum;

// pure
const checkAge = (age) => {
  const minimum = 21;
  return age >= minimum;
};
```

We can even make it better making the `minimum` variable immutable, using a method in Javascript called [freeze](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze). Just create an object to freeze like this:

```js
const immutableState = Object.freeze({ minimum: 21 });
```

Remember that you can destructure the object:

```js
const { minimum } = Object.freeze({ minimum: 21 });
```

### Useful Links

- [const X Object.freeze](https://stackoverflow.com/questions/33124058/object-freeze-vs-const)
