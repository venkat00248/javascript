#1 code for camel case 
const str = " one two three "

function camelCase(strn){
    const str1 = str.trim().split(" ")
    
    const str2 = str1.map(item =>{ 
        const str4 = item.charAt(0).toUpperCase()
        const str3 = item.substring(1)
       
        return str4+str3})
    
    
    return str2
}
console.log(camelCase(str))

#2 code for promises

function fetchDataFromAPI() {
  return new Promise((resolve, reject) => {
    // Simulating an API endpoint
    const apiUrl = 'https://jsonplaceholder.typicode.com/posts/1';

    // Making an API request using fetch
    fetch(apiUrl)
      .then(response => {
        // Check if the response is successful (status code 200-299)
        if (!response.ok) {
          throw new Error(`Failed to fetch data. Status: ${response.status}`);
        }
        // Parse the JSON data from the response
        return response.json();
      })
      .then(data => {
        // Resolve the promise with the fetched data
        resolve(data);
      })
      .catch(error => {
        // Reject the promise with an error message
        reject(error);
      });
  });
}

// Using the promise to make an API call
fetchDataFromAPI()
  .then(result => {
    console.log('Data fetched successfully:', result);
  })
  .catch(error => {
    console.error('Error fetching data:', error.message);
  });

#3 code for  simple promise 

const promise = new Promise((resolve, reject)=>{
let isPromise = false
if(isPromise){
  resolve("data")  
}
else{
    reject("data")
}
})
promise.then((response)=>{
    console.log("response", response)
}).catch((error)=>{
    console.log("error", error)
})
# 4  code for fetch data and display in UI
import React from "react";
import { useEffect, useState } from "react";
import axios from "axios";
export const Together = () => {
  const [data, setData] = useState([]);
  const fetchData = async () => {
    try {
      const res = await axios.get("https://jsonplaceholder.typicode.com/posts");
      console.log("resp", res.data);
      // const resp = res.json();

      setData(res.data);
    } catch (error) {
      console.log("error", error);
    }
  };
  useEffect(() => {
    fetchData();
  }, []);
  return (
    <>
      {/* <pre>{JSON.stringify(data, null, 2)}</pre> */}
      {data.length >= 0 ? (
        data.map((item) => {
          return (
            <div>
              <p>{item.userId}</p>
              <p>{item.id}</p>
              <p>{item.title}</p>
            </div>
          );
        })
      ) : (
        <div>no data </div>
      )}
    </>
  );
};



# 5 pseudo elements 
<div class="container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
  <div class="box">4</div>
</div>
.container {
  display: flex;
}

.box {
  width: 100px;
  height: 100px;
  border: 1px solid #000;
  margin: 5px;
}

.box:nth-child(2) {
  /* Styles for the second div go here */
  background-color: #3498db;
  color: #fff;
}
.box:last-child {
  /* Styles for the last div go here */
  background-color: #e74c3c;
  color: #fff;
}

.box:nth-last-child(2) {
  /* Styles for the last but one div go here */
  background-color: #2ecc71;
  color: #fff;
}

# 6 arrow function

Key points about arrow functions:

Concise Syntax: Arrow functions have a more concise syntax, especially when the function body is a single statement.

No this Binding: Arrow functions do not have their own this. They inherit this from the enclosing scope. This can be useful in certain situations, especially in callbacks or when dealing with nested functions.

No arguments Object: Arrow functions also do not have their own arguments object. Instead, you can use the rest parameters (...args) to get all arguments.

# 7 map vs filter

Map:
Purpose: The map method is used for transforming each element in an array and creating a new array with the results.
Syntax:
const newArray = array.map((currentValue, index, array) => {
  // return new element based on current element
});
Example:
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
// doubled is now [2, 4, 6, 8]

Filter:
Purpose: The filter method is used for creating a new array with elements that satisfy a specific condition.
Syntax:

const newArray = array.filter((currentValue, index, array) => {
  // return true to keep the element, false to filter it out
});

Copy code
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(num => num % 2 === 0);
// evenNumbers is now [2, 4]

# 8 latest es6 and html5 and css3 features

es6 
1.Arrow Functions:

const add = (a, b) => a + b;
2. Template Literals:

const name = "World";
console.log(`Hello, ${name}!`);

3.Destructuring Assignment:


const person = { name: "John", age: 30 };
const { name, age } = person;
4. Let and Const:


let variable = 10;
const constantValue = 20;

html5

Certainly! Let's break down your question into two parts:

Map vs. Filter:
Map:
Purpose: The map method is used for transforming each element in an array and creating a new array with the results.
Syntax:
javascript
Copy code
const newArray = array.map((currentValue, index, array) => {
  // return new element based on current element
});
Example:
javascript
Copy code
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
// doubled is now [2, 4, 6, 8]
Filter:
Purpose: The filter method is used for creating a new array with elements that satisfy a specific condition.
Syntax:
javascript
Copy code
const newArray = array.filter((currentValue, index, array) => {
  // return true to keep the element, false to filter it out
});
Example:
javascript
Copy code
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(num => num % 2 === 0);
// evenNumbers is now [2, 4]
Latest ES6, HTML5, and CSS3 Features:
ES6 (ECMAScript 2015+):
Arrow Functions:

javascript
Copy code
const add = (a, b) => a + b;
Template Literals:

javascript
Copy code
const name = "World";
console.log(`Hello, ${name}!`);
Destructuring Assignment:

javascript
Copy code
const person = { name: "John", age: 30 };
const { name, age } = person;
Let and Const:

javascript
Copy code
let variable = 10;
const constantValue = 20;

HTML5:
Semantic Elements:

<article>, <section>, <header>, <footer>, <nav>, <main>, etc.
New Form Elements:


<input type="date">, <input type="email">, <input type="url">, etc.
Canvas API:

<canvas id="myCanvas" width="200" height="100"></canvas>

CSS3

Certainly! Let's break down your question into two parts:

Latest ES6, HTML5, and CSS3 Features:
ES6 (ECMAScript 2015+):
Arrow Functions:

const add = (a, b) => a + b;
Template Literals:

const name = "World";
console.log(`Hello, ${name}!`);
Destructuring Assignment:

const person = { name: "John", age: 30 };
const { name, age } = person;
Let and Const:

let variable = 10;
const constantValue = 20;
HTML5:
Semantic Elements:

<article>, <section>, <header>, <footer>, <nav>, <main>, etc.
New Form Elements:


<input type="date">, <input type="email">, <input type="url">, etc.
Canvas API:


<canvas id="myCanvas" width="200" height="100"></canvas>

CSS3:
Flexbox:
.container {
  display: flex;
  justify-content: space-between;
}
Grid Layout:

.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}
Media Queries:

@media screen and (max-width: 600px) {
  /* styles for small screens */
}
Transitions and Animations:

.element {
  transition: transform 0.3s ease-in-out;
}

@keyframes slideIn {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}



