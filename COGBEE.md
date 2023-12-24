immediatly invoked function
service workers 
web workers
var x = 23;
(function() {
var x = 43;
(function random(){
var x;
x++;
console.log("x",x);
x = 21;} )();
} )();
