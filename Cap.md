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

