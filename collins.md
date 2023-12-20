#programming  1
Given an array of integers Arr of size N and a number K. Return the maximum sum of a subarray of size K.
 
NOTE*: A subarray is a contiguous part of any given array.
 
Example 1:
 
Input:
N = 4, K = 2
Arr = [100, 200, 300, 400]
Output:
700
Explanation:
Arr3  + Arr4 =700,
which is maximum.
Example 2:
 
Input:
N = 4, K = 4
Arr = [100, 200, 300, 400]
Output:
1000
Explanation:
Arr1 + Arr2 + Arr3 + Arr4 =1000,
which is maximum.

coding
function maxSubarraySum(arr, k) {
  let maxSum = 0;
  let currentSum = 0;

  // Calculate the sum of the first subarray of size k
  for (let i = 0; i < k; i++) {
    currentSum += arr[i];
  }

  // Iterate through the array to find the maximum sum
  for (let i = k; i < arr.length; i++) {
    currentSum = currentSum - arr[i - k] + arr[i];
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
}

// Example usage:
const arr1 = [100, 200, 300, 400];
const k1 = 2;
console.log(maxSubarraySum(arr1, k1)); // Output: 700

const arr2 = [100, 200, 300, 400];
const k2 = 4;
console.log(maxSubarraySum(arr2, k2)); // Output: 1000


#programming 2
input:
[
	{"ProductID": 20, "Qty":90}
	{"ProductID": 10, "Qty":23}
	{"ProductID": 40, "Qty":254}
	{"ProductID": 70, "Qty":21}
	{"ProductID": 90, "Qty":940}
]
 
output: 
{
	{"20" : 90},
	{"10" : 23},
	{"40" : 254},
	{"70" : 21},
	{"90" : 940},
}

coding

const transformedObject = {};

inputArray.forEach(item => {
  transformedObject[item.ProductID] = item.Qty;
});

console.log(transformedObject);


#programming 3

get method  vs  but post method  limitations

GET Method Limitations
1.Data Size Limitation:

GET requests typically have a limit on the amount of data that can be sent. This limit is imposed by both browsers and servers. 
Sending large amounts of data via GET may lead to truncated or incomplete requests.

2.Idempotence and Safety:

According to HTTP semantics, GET requests should be idempotent and safe.
Idempotence means that making the same request multiple times should have the same effect as making it once.
















