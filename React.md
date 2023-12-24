1.Error Boundaries 

In React, error boundaries are a feature that allows components to catch JavaScript errors anywhere in their component tree, log those errors, and display a fallback UI instead of crashing the component tree. Error boundaries are implemented using the componentDidCatch lifecycle method.

2.Ex of custom Hook

// useUpperCase.js

import { useState, useEffect } from 'react';

const useUpperCase = (initialText) => {
  const [text, setText] = useState(initialText);

  useEffect(() => {
    setText(initialText.toUpperCase());
  }, [initialText]);

  return text;
};

export default useUpperCase;

// MyComponent.js
import React from 'react';
import useUpperCase from './useUpperCase';

const MyComponent = ({ text }) => {
  const upperCaseText = useUpperCase(text);

  return <div>{upperCaseText}</div>;
};

export default MyComponent;

// App.js
import React from 'react';
import MyComponent from './MyComponent';

const App = () => {
  return <MyComponent text="Hello, World!" />;
};

export default App;


