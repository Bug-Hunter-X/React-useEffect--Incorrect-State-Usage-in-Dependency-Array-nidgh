# React useEffect: Incorrect State Usage in Dependency Array

This repository demonstrates a common error in React's `useEffect` hook where the previous state value is used within the dependency array's conditional statement, potentially leading to unexpected behavior or infinite loops.

## Problem

The `MyComponent` function uses `useState` to manage a count value. The `useEffect` hook is intended to perform an action whenever the `count` changes.  However, the conditional statement inside the effect checks against the previous value of `count`, which might not reflect the current value when the effect runs.  This can cause the effect to execute unexpectedly, leading to unintended consequences.

## Solution

To fix this issue, always use the current state value within the `useEffect` hook itself. Don't rely on the dependency array to hold a 'cached' value of state for use inside the conditional statement.  This approach helps prevent the effect from running based on stale values.

## How to reproduce the error

1. Clone this repository.
2. Run `npm install`
3. Run `npm start`
4. Observe the console logs as you click the increment button.  You'll notice the conditional statement may behave unexpectedly.