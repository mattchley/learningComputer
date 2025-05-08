# Two Sum II - Input Array Is Sorted
## Code
``` js
var twoSum = function(numbers, target) {
	let l = 0;
	let r = numbers.length - 1;
	
	while (l < r) {
		let total = numbers[l] + numbers[r];
		if (total === target) return [l + 1, r + 1];
		total > target ? r--: l++
	}

};
```

## The idea breaks down to:
- given an array of sorted numbers and a target return the numbers by index that sum up to target
```
Input: numbers = [2,7,11,15], target = 9
Output: [1,2]
```
- First thought is to use the two pointers system with the left pointer staying stationary while the right moves independently
- have the 2 pointers work by check if they add up the the target or not
- We can also make this faster by noticing the array is sorted
	- any number after the left pointer that is bigger than the target can be ignored and shift our pointers
- depending on the difference we can change a certain pointer
	- if the total is larger than the target we move the right pointer back
	- smaller we move the left pointer forward
## Notes