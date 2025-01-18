# Stale Closure Bug in React's useEffect Hook

This repository demonstrates a common error in React's `useEffect` hook involving stale closures within `setInterval`.  The incorrect dependency array in the `useEffect` hook leads to the counter failing to update properly.

## Bug Description

The `MyComponent` functional component uses `useState` to manage a counter.  A `setInterval` is set up within the `useEffect` hook to increment the counter every second. However, the dependency array is empty (`[]`), causing the `count` variable used inside `setInterval` to retain its initial value (0) throughout the component's lifecycle. This results in the counter never changing beyond 0.

## Solution

The solution involves correctly specifying the `count` variable in the dependency array of the `useEffect` hook.  This ensures that the effect is re-run whenever the `count` changes, correctly updating the `setInterval`'s closure.

## How to run

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install necessary packages.
4. Run `npm start` to start the development server.