# React setInterval Memory Leak
This example demonstrates a common mistake when using setInterval within a React component's useEffect hook: forgetting to include a cleanup function to stop the interval when the component unmounts.  This leads to a memory leak because the interval continues running even after the component is no longer needed.

## Bug
The `bug.js` file contains the buggy component.  The `setInterval` function is used to update a counter every second. However, there's no way to stop this interval once the component unmounts, resulting in a memory leak.

## Solution
The `bugSolution.js` file shows the corrected version.  The useEffect hook now returns a cleanup function that uses `clearInterval` to stop the interval when the component is unmounted or when the component updates.