#promise .race
#html select



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


