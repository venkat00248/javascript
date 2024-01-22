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


# prime numbers

function generatePrimes(n) {
  var primes = [];

  for (var i = 2; i <= n; i++) {
    if (isPrime(i)) {
      primes.push(i);
    }
  }

  return primes;
}

function isPrime(num) {
  for (var j = 2; j < num; j++) {
    if (num % j === 0) {
      return false;
    }
  }
  return num > 1;
}

// Example: Generate prime numbers from 1 to 20
var result = generatePrimes(20);
console.log(result); // Output: [2, 3, 5, 7, 11, 13, 17, 19]

