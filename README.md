# React 19 useEffect: Memory Leak with setInterval

This repository demonstrates a common mistake when using `setInterval` within a React `useEffect` hook, leading to memory leaks.  The bug is in `bug.js`, while the fix is in `bugSolution.js`.

## Bug Description

The `setInterval` function is used without a cleanup function, resulting in the interval never being cleared, even after the component unmounts. This leads to unnecessary resource consumption, and potentially memory leaks.

## Solution

The solution involves returning a cleanup function from the `useEffect` hook that uses `clearInterval` to stop the interval before the component unmounts.