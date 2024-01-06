# coding
import React, { useState } from "react";

const Dropdown = () => {
  const [arr, setArr] = useState([]);
  const [todo, setTodo] = useState("");
  const clickHandler = () => {
    setArr([...arr, todo]);
  };
  const deleteHandler = (index) => {
    const updatedTasks = [...arr];
    updatedTasks.splice(index, 1);
    setArr(updatedTasks);
  };
  return (
    <>
      <input
        type="text"
        value={todo}
        onChange={(e) => setTodo(e.target.value)}
      />
      <button onClick={clickHandler}>add </button>
      {arr.map((item, index) => {
        return (
          <div style={{ display: "flex" }} key={index}>
            <div>{item}</div>
            <button onClick={() => deleteHandler(index)}>Delete</button>
          </div>
        );
      })}
    </>
  );
};

export default Dropdown;
