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
# 8 latest es6 and html5 and css3 features


