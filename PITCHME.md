# React Hooks in Practice

---
## Agenda

1. Introduction to Hooks
2. State and lifecycle in Function Components
3. Reusing Component logic
4. Final thoughts

---
## Introduction to hooks

---
## Hooks

> Hooks are a new feature proposal that lets you use state and other React features without writing a class. They’re currently in React v16.7.0-alpha and being discussed in an open RFC.

---
## Available hooks

* State Hook
* Effect Hook
* Custom Hooks
* Other build-in hooks

---
## State and lifecycle

---
### State

#### Without hooks 🍂 
```jsx
this.setState({ value: initialValue })
const { value } = this.state
```

#### With hooks 🌱 
```jsx
const [value, setValue] = useState(initialValue)
```

---
### Lifecycle

#### Without hooks 🍂
```jsx
componentDidMount() {
    console.log('component did mount')
}
componentDidUpdate() {
    console.log('component did update')
}
componentWillUnmount() {
    console.log('component will unmount')
}
```
---
### Lifecycle

#### With hooks 🌱
```jsx
useEffect(() => {
    console.log('component did mount or update')

    return () => {
        console.log('component will update or unmount')
    }
})
```

---
### Live coding demo 👨🏻‍💻

---
## Reusing component logic

---
#### Reusing component logic with Higher-Order Components 🍂 

```jsx
class MyComponent extends Component {
    render() { ... }
}

export default addFunctionality(MyComponent)
```


#### Reusing component logic With hooks 🌱
```jsx
export const MyComponent = () => {
    useFunctionality()
    return ...
}
```

---
#### Reusing component logic with Higher-Order Components 🍂 

```jsx
class MyComponent extends Component {
    render() { ... }
}

export default addThirdFunctionality(
    addSecondFunctionality(
        addFirstFunctionality(
            MyComponent,
            firstFunctionalityArg1,
            firstFunctionalityArg2,
        ),
        secondFunctionalityArg,
        ),
    thirdFunctionalityArg,
)
```

---
#### Reusing component logic With hooks 🌱
```jsx
export const MyComponent = () => {
    useFirstFunctionality(
        firstFunctionalityArg1,
        firstFunctionalityArg2,
        )
    useSecondFunctionality(
        secondFunctionalityArg,
        )
    useThirdFunctionality(
        thirdFunctionalityArg,
        )

    return ...
}
```

---
### Redux example

---
#### Redux example with Higher-Order Components 🍂 

```jsx
class MyComponent extends Component {
    ...
}

const mapStateToProps = state => ({
    ...
});
const mapDispatchToProps = dispatch => ({
  ...
});

export default connect(
  mapStateToProps,
  mapDispatchToProps
)(MyComponent);
```

---
#### Redux example With hooks 🌱

```jsx
export const MyComponent = () => {
    const [state, dispatch] = useRedux()
    
    return (
        <Button onClick={() => dispatch({type: 'CLICKED'})}>
            {state.clicked}
        </Button>
    )
}
```

---
### Live coding demo 👨🏻‍💻

---
## Final thoughts

1. Other Hooks
2. Further reading

---
### Other Hooks

* useContext
* useReducer
* useCallback
* useMemo
* useRef
* useImperativeMethods
* useMutationEffect
* useLayoutEffect

---
### Futher reading

Official documentation:
* [Introducing Hooks](https://reactjs.org/docs/hooks-intro.html)
* [Hooks at a Glance](https://reactjs.org/docs/hooks-overview.html)
* [Hooks API Reference](https://reactjs.org/docs/hooks-reference.html)


Medium.com:
* [Dan Abramov - Making Sense of React Hooks](https://medium.com/@dan_abramov/making-sense-of-react-hooks-fdbde8803889)
* [Rudi Yardley - React hooks: not magic, just arrays](https://medium.com/@ryardley/react-hooks-not-magic-just-arrays-cd4f1857236e)

---
## Thank you!