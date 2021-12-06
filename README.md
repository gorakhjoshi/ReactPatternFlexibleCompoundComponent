# Flexible Compound Components

## 📝 Your Notes

## Background

**One liner:** The Flexible Compound Components Pattern is only differs from the
previous exercise in that it uses React context. You should use this version of
the pattern more often.

Right now our component can only clone and pass props to immediate children. So
we need some way for our compound components to implicitly accept the on state
and toggle method regardless of where they're rendered within the Toggle
component's "posterity" :)

The way we do this is through context. `React.createContext` is the API we want.

**Real World Projects that use this pattern:**

- [`@reach/accordion`](https://reacttraining.com/reach-ui/accordion)

## Exercise

The fundamental difference between this exercise and the last one is that now
we're going to allow people to render the compound components wherever they like
in the render tree. Searching through `props.children` for the components to
clone would be futile. So we'll use context instead.

Your job will be to make the `ToggleContext` which will be used to implicitly
share the state between these components, and then a custom hook to consume that
context for the compound components to do their job.

## Extra Credit

### 1. 💯 custom hook validation

Change the `App` function to this:

```javascript
const App = () => <ToggleButton />;
```

Why doesn't that work? Can you figure out a way to give the developer a better
error message?