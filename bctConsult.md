how react works 
overview and flow of redux and redux principle
shadow dom 
example of class based component
life cycle methods 
hoc example

# coding 1 


 function lengthOfLastWord(s) {
    let length = 0;
    let end = s.length - 1;

    // Skip trailing spaces
    while (end >= 0 && s[end] === ' ') {
        end--;
    }

    // Count the length of the last word
    while (end >= 0 && s[end] !== ' ') {
        length++;
        end--;
    }

    return length;
}

// Test cases
console.log(lengthOfLastWord("Hello World"));  // Output: 5
console.log(lengthOfLastWord("   fly me   to   the moon  "));  // Output: 4
console.log(lengthOfLastWord("luffy is still joyboy"));  // Output: 6












const lengthOfLastWord = (s) => {
  let length = 0;
  let lastWordFound = false;
 
  for (let i = s.length - 1; i >= 0; i--) {
    if (s[i] !== ' ') {
      length++;
      lastWordFound = true;
    } else if (lastWordFound) {
      break;
    }
  }
 
  return length;
};




import React from 'react';

// Higher Order Component
const withExtraProps = (WrappedComponent) => {
  return (props) => (
    <WrappedComponent {...props} extraProp="This is an extra prop from HOC" />
  );
};

// Functional Component
const MyComponent = (props) => (
  <div>
    <p>My Component</p>
    <p>Extra Prop: {props.extraProp}</p>
  </div>
);

// Using the HOC with the functional component
const EnhancedComponent = withExtraProps(MyComponent);

// App component
const App = () => (
  <div>
    <h1>Higher Order Component Example</h1>
    <EnhancedComponent />
  </div>
);

export default App;

