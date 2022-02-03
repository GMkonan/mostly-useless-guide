## First class functions
When a programming language has "first class functions" it just means that this functions can be like everyone else. What does that even mean? It just means that they can be treated like **any other** data type.
They can be assigned to other variables, passed as an argument etc. The easiest way to a think about than is:

```
First class functions are just ordinary variables with a **function** type
```

### Okay, sooo...?
You may be asking yourself, how this concept can benefit your code? Let's check some examples to figure it out.

I think an amazing example of this concept's usage alone is this one:

```js
const hi = name => `Hi ${name}`;
const greeting = name => hi(name);
```

At first glance this is fine. Just a function `hi` that is called by other function `greeting` where both pass an argument `name`.

The problem is, `greeting` doesn't need to call `hi` with the same argument. In Javascript, when a function has `()` at the end it will run and return us a value. But if a function doesn't have `()` at the end it will simple return the function in itself:

```js
//Test this on a brownser console :)
hi; // name => `Hi ${name}`
hi("jonas"); // "Hi jonas"
```

With that information in hand we can grab or first example again and **just assign** `hi` to `greeting`.

```js
const greeting = hi;
greeting("times"); // "Hi times"
```

The proper usage of **First class functions** can make your code less verbose, but this is not the only reason we talked about it. They are necessary to other concepts of FP like `Higher-order functions` which we will see later on.


#### Useful Links
- [Professor Frisby's book chapter 2](https://mostly-adequate.gitbook.io/mostly-adequate-guide/ch02)