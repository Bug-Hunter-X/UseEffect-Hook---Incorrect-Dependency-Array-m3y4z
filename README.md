# React useEffect Hook - Incorrect Dependency Array

This repository demonstrates a common bug in React applications involving the `useEffect` hook. The bug arises from an incorrect dependency array, leading to unexpected behavior.

## Bug Description

The `MyComponent` component uses the `useEffect` hook to update the `count` state every second.  However, the dependency array is empty (`[]`), meaning the effect runs only once after the component mounts.  The issue is that inside the effect, `setCount(count + 1)` uses the `count` variable from the closure, which is not reflected in the dependency array.  This causes an infinite loop because the effect keeps re-running without ever considering the new count value.