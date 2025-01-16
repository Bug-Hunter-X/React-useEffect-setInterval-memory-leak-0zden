# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within the `useEffect` hook in React: forgetting to clear the interval in the cleanup function, leading to memory leaks.

## Problem

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, resulting in the interval continuing to run even after the component is no longer needed, which causes a memory leak.

## Solution

The `bugSolution.js` file provides the corrected version.  The cleanup function now correctly calls `clearInterval` to stop the interval before the component unmounts, preventing memory leaks.  Always remember to return a cleanup function from your `useEffect` hook when using timers or other resources that need to be released.