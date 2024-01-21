# promise.race and promise.All

Handling Multiple Promises:

Promise.all: Expects an array of promises and returns a new promise that fulfills with an array of the results when all of the input promises are fulfilled. If any promise in the array is rejected, the entire Promise.all is rejected, and the rejection reason is the reason of the first rejected promise.


Promise.race:

Also takes an array of promises but settles as soon as any one of the promises is settled (either resolved or rejected). The result or error of the first settled promise is used to settle the returned promise.


Settlement Behavior:

Promise.all: Resolves only if all promises in the array resolve successfully. If any promise is rejected, the entire Promise.all is rejected.

Promise.race: Settles with the result or error of the first settled promise in the array.


Use Cases:

Promise.all: Useful when you want to wait for all promises to complete before performing some action. For example, when fetching data from multiple sources and needing all the data before rendering a page.
Promise.race: Useful when you want to respond as soon as any of the promises is settled. For example, if you are making multiple requests and only need the result of the first successful one.
Example:

const promise1 = new Promise(resolve => setTimeout(resolve, 100, 'Promise 1 resolved'));
const promise2 = new Promise((resolve, reject) => setTimeout(reject, 50, 'Promise 2 rejected'));

// Promise.all
Promise.all([promise1, promise2])
  .then(results => console.log(results))
  .catch(error => console.error(error)); // This will log "Promise 2 rejected"

// Promise.race
Promise.race([promise1, promise2])
  .then(result => console.log(result)) // This will log "Promise 2 rejected"
  .catch(error => console.error(error)); // Will not be called as the first promise settles with rejection
Performance Consideration:

Promise.all: Waits for all promises to complete, so it might take longer to settle if there's a slow promise in the array.


Promise.race: Settles as soon as any one of the promises settles, which can be faster if one of the promises resolves or rejects quickly.
Understanding these differences helps in choosing the appropriate method based on the specific requirements of the task at hand.


# coding 
import React, { useEffect, useState } from "react";
import axios from "axios";
const Dropdown = () => {
  const [response, setResponse] = useState({});
  const [filter, setFilter] = useState("");
  const fetchData = async () => {
    try {
      const res = await axios.get("https://fakestoreapi.com/products");
      setResponse(res.data);
      console.log("res", res.data);
    } catch (error) {
      console.log("erorr", error);
    }
  };
  const sortData = (data, sortingOrder) => {
    if (sortingOrder === "asc") {
      return data.sort((a, b) => a.rating.count - b.rating.count);
    } else if (sortingOrder === "desc") {
      return data.sort((a, b) => b.rating.count - a.rating.count);
    }
    return data;
  };

  useEffect(() => {
    fetchData();
  }, []);

  useEffect(() => {
    const sortedData = sortData([...response], filter);
    setResponse(sortedData);
  }, [filter]);
  return (
    <>
      <div>data</div>
      <select
        onChange={(e) => {
          setFilter(e.target.value);
          console.log("e", e.target.value);
        }}
      >
        <option>asc</option>
        <option>desc</option>
      </select>
      {response.length >= 0 ? (
        response.map((item) => {
          return (
            <div className="wrapper">
              <p style={{ width: "10%" }}> {item.id}</p>
              <p style={{ width: "20%" }}> {item.title}</p>
              <p style={{ width: "50%" }}> {item.description}</p>
              <p style={{ width: "10%" }}> {item.price}</p>
              <p style={{ width: "10%" }}> {item.rating.count}</p>
            </div>
          );
        })
      ) : (
        <div> no data </div>
      )}
    </>
  );
};

export default Dropdown;


