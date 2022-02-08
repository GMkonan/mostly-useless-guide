# Pure functions

> A pure function is a function that, given the same input, will always return the same output and does not have any observable side effect.

Take a look at this examples for better understanding:

```js
//impure
let variableOutOfScope = 2;
const addNumbers = (a) => (variableOutOfScope += a);
//This function is not deterministic and it depends on a variable
//declared outside the function
addNumbers(2); //4
addNumbers(2); //6

//pure
const addNumbers = (a, b) => a + b;
//given the same input will always return the same output
addNumbers(2, 2); //4
```

In this example we have a **impure** function because:

- given the same input can have a different output

- depends on a mutable variable **variableOutOfScope** to determine the output

And the **pure** function is considered pure because:

- It's only depending on it's inputs

- if the same input is given it will always produce the same ouput

Let's take a look at another example:

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

In this case the impure function has the same problem. Is using an out of scope mutable variable to determine the result.
But the **pure** function is self-sufficient. It uses a variable that is self-contained inside the function itself (block scoped since is a **const**), which means is closed scope.

## Side Effects

>A side effect is a change of system state or observable interaction with the outside world that occurs during the calculation of a result.

An easier way to think about it is that **any interaction with the world outside of a function is a side effect**. Is difficult to think about a program that can follow this rules. That's because that is not the goal! We are not forbidden from using side-effects. We just want to use them as little as possible in a controlled way.

Now if you take a look at our **pure functions** examples you will see that the out of scope variables are side effects. Which shows why side effects disqualifies functions from being pure, you can't guarantee the *same output given the same input* if you have side effects in your function, making it **impure**.

## Math!...?

>A function is a special relationship between values: Each of its input values gives back exactly one output value.

What this phrase make us realize is that pure functions in the end are just mathematical functions!

## But why pure functions?

Pure functions can be really powerful depending on the context, some of the reasons are:

- **Testing**: Is a lot easier to test Pure functions.
- **Performance**: Since they are deterministic, we can [memoise](https://en.wikipedia.org/wiki/Memoization) (cache) the result.
- **Concise**: They don't alter variables outside there scope, so is a lot easier to read them.

### Referential transparency
One of the best things about working with pure functions is [Referential transparency](https://stackoverflow.com/questions/210835/what-is-referential-transparency). When talking about programming we can say that a piece of code is referentially transparent when it can be substituted for its evaluated value without changing what the program does. Which in the end translates to something we already heard of, which is:

> If the input is the same, the output will always be the same

I recommend checking [this section](https://mostly-adequate.gitbook.io/mostly-adequate-guide/ch03#reasonable) in *mostly adequate guide* book to see more about Referential transparency, Equational reasoning and reason about code.

### Useful Links
- [Professor Frisby's book chapter 3](https://mostly-adequate.gitbook.io/mostly-adequate-guide/ch03)
- [What is referential transparency?](https://stackoverflow.com/questions/210835/what-is-referential-transparency)
- [Meaning of Equational reasoning](https://stackoverflow.com/questions/29113863/where-does-the-name-of-equational-reasoning-come-from#:~:text=%22Equational%20reasoning%22%20is%20just%20reasoning,series%20of%20rewrites%3A%20fmap%20even%20.)