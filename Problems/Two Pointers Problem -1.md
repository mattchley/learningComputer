# Valid Palindrome
## Code
``` js
var isPalindrome = function(s) {
	let pureLetters = s.toLowerCase().replace(/[^a-z0-9]/g, "")
	
	let l = 0;
	let r = pureLetters.length - 1;
	
	while (l < r) {
		if (pureLetters[l] !== pureLetters[r]) {
			return false
			};
	
		l++;
		r--;
	}
	return true;
};
```

## The idea breaks down to:
- Return true or false if a string is a palindrome
- First thought:
	- the string can have things other than letters in it
		- `, : etc`
	- and upper case or lowercase letters
	- need to standardize the string first
	- then use 2 pointers to check if the front and back letters match
		- create the pointers to start at 0 and the end of the string
		- check if the letters are not equal return false
		- otherwise in/de-crement the pointers

## Notes
- This can be done faster without the 2 pointers by simplifying the process and reversing strings
- this works because when we reverse the string it reorders the placement of letters. A palindrome ill have the same positioning regardless
``` js
var isPalindrome = function (s) {
	let alphaOnly = s.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
	let reverseString = alphaOnly.split("").reverse().join("");
	return alphaOnly === reverseString
};
```
