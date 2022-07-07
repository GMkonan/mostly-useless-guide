Basically make the function called return `this` from the value's scope. So the function bind is working at a `this` from the specified scope and not globaly.

```js
function.bind(value)
//function when called is gonna work using this from value
```

Example:
```typescript

const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () { //Needs to be a normal function
    return this.firstName + " " + this.lastName;
  }
}

const member = {
  firstName:"Hege",
  lastName: "Nilsen",
}

let fullName = person.fullName.bind(member);

```
### Useful Links:
- https://www.w3schools.com/js/js_function_bind.asp
- https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Function/bind
- https://stackoverflow.com/questions/33308121/can-you-bind-this-in-an-arrow-function