The call method is used to invoke a method from an object as a parameter

Example:
```typescript
const geometry = {
    getX: function() {
        return this.x
    }
}

const square = {
    x: 9
}

geometry.getX.call(square)
```
### Useful Links:
- https://www.w3schools.com/js/js_function_call.asp