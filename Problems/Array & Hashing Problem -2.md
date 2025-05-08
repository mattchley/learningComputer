# Valid Anagram
## Code
``` js
var isAnagram = function (s, t) {
	if (s.length !== t.length) return false
    
    const counter = new Map()

    for (let char of s){
        counter.set(char, (counter.get(char) || 0) + 1)
    }
    for (let char of t){
        if (counter.has(char) === false || counter.get(char) === 0){
            return false
        }
        counter.set(char, counter.get(char) -1)
    }
    return true
};
```

## The idea breaks down to:
- first compare the 2 strings
	- if they are not the same length they cannot be Anagrams
-  After that we create a map and loop through 1 of the strings to track the count of each character
- Second create a loop to subtract the characters from the available or return false if the character is not found

## Notes
- there is a way to do this that is a bit more clever by using an array that is the length of the alphabet to track the counts
- The characters can easily be converted to their position in the alphabet with a method
	- `'a'.charCodeAt(0)`
	- where 'a' is a placeholder for whatever string used
- and for the first loop you fill the array like so the [] subtraction returns the first chars position at 0 index
``` js
const count = Array(26).fill(0);
    for (let char of s) {
        count[char.charCodeAt(0) - 'a'.charCodeAt(0)] += 1;
    }
```
 - then follow the same subtraction process in the second loop