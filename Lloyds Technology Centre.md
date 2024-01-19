console.log("hello1");

(async function() {
  await new Promise(resolve => setTimeout(resolve, 2000));
  console.log("hello2");
})();

debounce
pure function

redux work flow

reducer is a pure function
