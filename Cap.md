#1. duplicates in Aa Array 

let arr=[1,2,4,5,6,5,3,7,8,9,7,7];

const newArr = [...new Set(arr)]
console.log("m", newArr)
