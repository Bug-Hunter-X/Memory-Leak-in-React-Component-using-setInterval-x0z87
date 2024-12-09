# React setInterval Memory Leak
This repository demonstrates a common error in React components: using `setInterval` within `useEffect` without proper cleanup.  This results in a memory leak because the interval continues to run even after the component unmounts.

The `bug.js` file shows the problematic code. The `bugSolution.js` demonstrates the corrected version, including a cleanup function to stop the interval when the component unmounts.

## How to reproduce
1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` to compare the code.
3. Run the example (instructions might vary depending on your environment). Observe the behavior of both versions.

## Solution
The key to fixing this issue is to return a cleanup function from the `useEffect` hook. This function is responsible for stopping the interval using `clearInterval` before the component unmounts, preventing the memory leak.