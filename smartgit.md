1.call bind and apply
In summary:

Use call when you want to immediately invoke a function with a specific context and individual arguments.
Use apply when you want to immediately invoke a function with a specific context and arguments provided as an array.
Use bind when you want to create a new function with a specific context and possibly pre-set arguments, without immediately invoking the original function.

2.real dom vs virtual dom
React, a JavaScript library for building user interfaces, utilizes the concept of a virtual DOM to optimize rendering. When a state or props change in a React component, React first updates the virtual DOM. It then calculates the differences (diffing) between the old and new virtual DOM and applies only the necessary changes to the real DOM. This approach minimizes the number of actual manipulations on the real DOM, leading to improved performance.

In summary, the virtual DOM is an abstraction that provides a more efficient way to update the actual DOM in web applications, and it is commonly used in libraries and frameworks like React for smoother and faster UI rendering.

3.promise vs async preference

4.scale  transfom  translate  properties in css

5.find vs filter

5.debounce

Debouncing is a programming practice used to ensure that time-consuming tasks do not fire so often, making them more efficient. It's often applied to events like resizing a window or typing in an input field to limit the frequency of function execution.

6.code spliting

Code splitting in React is a technique that allows you to split your JavaScript bundle into smaller chunks, which can be loaded on-demand. This helps in reducing the initial loading time of your application by only loading the necessary code when it's required. React provides a built-in feature called dynamic import, which you can use for code splitting


7.lazy loading

Lazy loading in React is a technique used to defer the loading of certain components or assets until they are actually needed. This can significantly improve the initial loading time of your application, especially for larger projects. React provides a built-in way to achieve lazy loading using the React.lazy function.

Here's a basic example of lazy loading a component in React:

import React, { lazy, Suspense } from 'react';

// Lazy-loaded component
const LazyComponent = lazy(() => import('./LazyComponent'));

function App() {
  return (
    <div>
      <h1>Hello, Lazy Loading in React!</h1>

      {/* Suspense is used to specify a fallback while the lazy component is loading */}
      <Suspense fallback={<div>Loading...</div>}>
        <LazyComponent />
      </Suspense>
    </div>
  );
}

export default App;

8.optimization techniques

1.Code Splitting:
2.Memoization
3.Use PureComponent or shouldComponentUpdate

For class components, use PureComponent or implement shouldComponentUpdate to avoid unnecessary re-renders when the props or state haven't changed.
Lazy Loading and Suspense:




