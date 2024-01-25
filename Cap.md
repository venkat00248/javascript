# for long strings use Template literals 
# life cycle methods
#  event delegation
#  redux middlewares
#1. duplicates in Aa Array 

# 1  way 
let arr=[1,2,4,5,6,5,3,7,8,9,7,7];

const newArr = [...new Set(arr)]
console.log("m", newArr)

# 2 way

let array = [1, 2, 3, 4, 4, 5, 6, 6];
function removeDuplicates(arr){
return  arr.filter((value, index) => {
    return arr.indexOf(value) === index;
});
}
console.log(removeDuplicates(array));

# 3 way

let array = [1, 2, 3, 4, 4, 5, 6, 6];
let uniqueArray = [];

array.forEach((value) => {
    if (!uniqueArray.includes(value)) {
        uniqueArray.push(value);
    }
});

console.log(uniqueArray);
# 4 way 
const array = [1,2,5,3,2,6,3]

const filterFunc = (arr) => {
const updatedArr = []
     for(let i = 0; i<=arr.length-1; i++){
           if (updatedArr.indexOf(arr[i]) === -1) {
            updatedArr.push(arr[i]);
        }
         
     }
    
    return updatedArr
    
}

console.log("Welcome to Programiz!",filterFunc(array));

react lifecycle methods 
redux middlewares
es6  fetures
