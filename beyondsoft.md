coding 1 
// Write a function that prints numbers from 1 to n. But for multiples of 3, print "Fizz" instead of the number, and for multiples of 5, print "Buzz". For numbers which are multiples of both three and five, print "FizzBuzz".


const fizzFunc = (num) => {
    
   for(let i =1; i<=num; i++){
       if(i%5===0 && i%3===0){
       console.log("FizzBuzz")
       }
       else if(i%5===0){
       console.log("Buzz")
       }
       else if (i%3===0){
           console.log("Fizz")
       }
       else{
           console.log(i)
       }
   }

}

fizzFunc(31)


   debouncing 
   event propagation

   redux workflow
   
   

   
    


