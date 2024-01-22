css box modal

react life cycles
# Automatic Batching

In React, updating the DOM can be an expensive operation, so React tries to optimize this process by batching multiple updates into a single update. This process is known as "batching updates." React uses a mechanism called the "virtual DOM" to efficiently update the actual DOM.

When multiple state updates or other changes occur within a single execution context (like a React event handler or a lifecycle method), React will batch those updates and apply them in a single pass. This helps to avoid unnecessary re-renders and improve performance.
