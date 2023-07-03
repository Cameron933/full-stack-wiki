### State can be defined as: data that changes over time.
```jsx
function Counter() {
  const [count, setCount] = React.useState(0)
  const increment = () => setCount(count + 1)
  return <button onClick={increment}>{count}</button>
}

// destructure
const [name, setName] = React.useState("")

// Nobody will like to write like this:
const array = React.useState("")
const name = array[0]
const setName = array[1]
```
- `React.useState` is a function that accepts a single argument. 
	That argument is the initial state for the instance of the component.

- `React.useState` returns a pair of values.
	It does this by returning an array with two elements (and we use destructuring syntax to assign each of those values to distinct variables).
	> The first of the pair is the state value and the second is a function we can call to update the state. We can name these variables whatever we want. Common convention is to choose a name for the state variable, then prefix `set` in front of that for the updater function.

### lazy state initialization
- 
