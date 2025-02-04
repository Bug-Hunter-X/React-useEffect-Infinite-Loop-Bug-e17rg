# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by incorrectly including the state variable in the dependency array.

## Bug

The `bug.js` file contains a React component that attempts to increment a state variable (`count`) within the `useEffect` hook.  Because `count` is included in the dependency array, the effect runs every time `count` changes, leading to an infinite loop and a crash.

## Solution

The `bugSolution.js` file provides the corrected code. The solution is to remove `count` from the dependency array if the effect doesn't need to run on every `count` change.  If it should only run once after the initial render, use an empty dependency array `[]`.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the error in your browser's console.
