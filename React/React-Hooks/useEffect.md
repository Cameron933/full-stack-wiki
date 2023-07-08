- `React.useEffect` is a built-in hook that allows you to run some custom code after React renders (and re-renders) your component to the DOM. It accepts a callback function which React will call after the DOM has been updated:
```javascript
// useEffect(setup, dependencies?)
React.useEffect(() => {
  // your side-effect code here.
  // this is where you can make HTTP requests or interact with browser APIs.
}, [])
```
Parameters 
setup: The function with your Effect’s logic. Your setup function may also optionally return a cleanup function. When your component is added to the DOM, React will run your setup function. After every re-render with changed dependencies, React will first run the cleanup function (if you provided it) with the old values, and then run your setup function with the new values. After your component is removed from the DOM, React will run your cleanup function.

optional dependencies: The list of all reactive values referenced inside of the setup code. Reactive values include props, state, and all the variables and functions declared directly inside your component body. If your linter is configured for React, it will verify that every reactive value is correctly specified as a dependency. The list of dependencies must have a constant number of items and be written inline like [dep1, dep2, dep3]. React will compare each dependency with its previous value using the Object.is comparison. If you omit this argument, your Effect will re-run after every re-render of the component.
