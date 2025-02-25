# Signal
Very small, basically Fundamental Signal Implementation compliant with [tc39 Signals proposal](https://github.com/tc39/proposal-signals).

Adaptation from [Ryan Carniato's Signal Article](https://dev.to/ryansolid/building-a-reactive-library-from-scratch-1i0p).


## Example

```ts
console.log("1. Create")
const firstName = new ClosureSignal.State("John")
const lastName = new ClosureSignal.State("Smith")
const showFullName = new ClosureSignal.State(true)

const displayName = new ClosureSignal.Computed(() =>
  showFullName.get() ? `${firstName.get()} ${lastName.get()}` : firstName.get()
)

new ClosureSignal.Computed(() => console.log("My name is", displayName.get()))

console.log("2. Set showFullName: false ")
showFullName.set(false)

console.log("3. Change lastName")
lastName.set("Legend")

console.log("4. Set showFullName: true")
showFullName.set(true)

console.log("5. Change lastName while showFullName: true")
lastName.set("Who")
```
