# fibonacci

function fibonacci(n) {
  var fibSeries = [0, 1];

  for (var i = 2; i < n; i++) {
    fibSeries[i] = fibSeries[i - 1] + fibSeries[i - 2];
  }

  return fibSeries;
}

// Example: Generate the first 10 Fibonacci numbers
var result = fibonacci(10);
console.log(result); // Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
