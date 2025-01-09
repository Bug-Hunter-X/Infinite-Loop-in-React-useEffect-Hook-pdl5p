# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by omitting the dependency array.  The `useEffect` hook is designed to perform side effects, but without a dependency array, it runs after every render, leading to a loop where the component constantly updates itself.

## Problem
The `bug.js` file contains a React component that uses `useEffect` without a dependency array.  This results in the effect running on every render, leading to an infinite loop.  The console will continuously log "Component rendered", illustrating the problem. 

## Solution
The `bugSolution.js` file provides a corrected version. By adding the `count` variable to the dependency array (`[count]`), the effect now only runs when the `count` changes, resolving the infinite loop.

## How to reproduce
1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server. Observe the console output and see the infinite loop.
5. Try running `bugSolution.js` and you'll see that the problem is fixed. 

## Lesson Learned
Always include a dependency array in `useEffect` unless you explicitly intend for the effect to run after every render.  The dependency array controls when the effect function executes and is crucial for preventing performance problems and unexpected behavior.