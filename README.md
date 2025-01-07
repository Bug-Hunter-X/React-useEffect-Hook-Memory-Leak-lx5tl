# React useEffect Hook Memory Leak

This repository demonstrates a common error in React's `useEffect` hook:  forgetting to include a return statement for cleanup functions.  This can lead to memory leaks if not handled correctly. 

## The Problem

The `bug.js` file shows an implementation of a simple counter component.  The `useEffect` hook logs a message when the component mounts, but it is missing a return statement to perform cleanup actions when the component unmounts.

Without a return statement, any side effects (like event listeners or intervals) initiated within the `useEffect` will not be cleaned up when the component is unmounted from the DOM. This can result in memory leaks, especially if the component is frequently rendered and unrendered.

## The Solution

The `bugSolution.js` file shows the corrected version of the component with the return statement added to the `useEffect` hook. This ensures that cleanup actions are performed, preventing memory leaks. 

## How to Reproduce

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the behavior of the component in both the `bug.js` and `bugSolution.js` files.