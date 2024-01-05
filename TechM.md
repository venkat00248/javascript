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

      setData(res);
    } catch (error) {
      console.log("error", error);
    }
  };
  useEffect(() => {
    fetchData();
  }, []);
  return (
    <>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </>
  );
};

# 4 latest es6 and html5 and css3 features


