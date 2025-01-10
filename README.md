# Infinite useEffect Loop in React

This repository demonstrates a common React bug involving an infinite loop in the `useEffect` hook.  The `useEffect` hook, intended for performing side effects after rendering, runs infinitely when the dependency array is incorrectly specified.

## Problem

The provided `MyComponent` uses `useEffect` to log the current value of `count` to the console. Without the dependency array, `useEffect` is executed after *every* render. This causes a continuous loop because `setCount` triggers a re-render, leading to infinite calls of `useEffect`. This creates significant performance issues and floods the console.

## Solution

The fix is simple: add `[count]` to the dependency array of `useEffect`. This ensures that the effect only runs when the `count` value changes, preventing the infinite loop.

## How to Reproduce

1. Clone this repository
2. Navigate to the project directory
3. Run `npm install`
4. Run `npm start`
5. Observe the infinite logging in the console

## How to Fix

1. Open `bug.js` and review the error
2. Look at the solution in `bugSolution.js` to see how to correctly implement the useEffect hook with the correct dependency array