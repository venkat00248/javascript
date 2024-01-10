how react works 
overview and flow of redux and redux principle
shadow dom 

# coding 1 


 function lengthOfLastWord(s) {
    let length = 0;
    let end = s.length - 1;

    // Skip trailing spaces
    while (end >= 0 && s[end] === ' ') {
        end--;
    }

    // Count the length of the last word
    while (end >= 0 && s[end] !== ' ') {
        length++;
        end--;
    }

    return length;
}

// Test cases
console.log(lengthOfLastWord("Hello World"));  // Output: 5
console.log(lengthOfLastWord("   fly me   to   the moon  "));  // Output: 4
console.log(lengthOfLastWord("luffy is still joyboy"));  // Output: 6












const lengthOfLastWord = (s) => {
  let length = 0;
  let lastWordFound = false;
 
  for (let i = s.length - 1; i >= 0; i--) {
    if (s[i] !== ' ') {
      length++;
      lastWordFound = true;
    } else if (lastWordFound) {
      break;
    }
  }
 
  return length;
};
