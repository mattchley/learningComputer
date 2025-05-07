# Group Anagram
## Code
``` js
var groupAnagrams = function(strs) {
	if(strs.length ===1) return [strs]
	
	let res = {};
	
	for (let s of strs) {
		let key = s.split('').sort().join('');
		if (!res[key]) {
		res[key] = [];
		}
		res[key].push(s);
	}
	
	return Object.values(res);
};
```

## The idea breaks down to:
- Given an array of strings return the group of strings that are anagrams in an array
- An anagram is any word that comprises the same letters
- we can check if the words are anagrams of each other by sorting the words alphabetically
- inside the loop we will sort each word and add it to an object
	- if the sorted word is already in the obj we add that word to the value
	- if not we create an empty array at that key
- after we sort it all out we simply return the Object values.
	- this returns an array by default base on how JS deals with the Object.values method

## Notes