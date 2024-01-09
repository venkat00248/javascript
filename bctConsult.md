how react works 
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
