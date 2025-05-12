# Binary Search
## Code
``` js
var search = function(nums, target) {
	let l = 0
	let r = nums.length-1
	
	while(l < r){
	
		let mid = l + Math.floor((r-l +1)/2);
		
		if(target < nums[mid]){
				r = mid -1
			} else{
				l = mid
			}
	}
	
	return nums[l] == target? l : -1
};
```

## The idea breaks down to:
- Take a **sorted** array and find the target value and return it's index
	- the catch is writing something that is `O(log n)` time
- First thoughts
	- using 2 pointers we can go through the array faster than doing one sided
	- We can use the typical functionality of a two pointers set up with the checks and adjustment of the pointers
	- All that is new is using the mid point(binary search) to see if we move the left or right pointer as we go based on the index
```
nums = [-1,0,3,5,9,12], target = 9

l = 0, r = 5

mid = 5 - 0 +1 -> 6/2 -> 3 + (0) = 3

is target, 9 bigger or smaller than 5?

shift left or right pointer as needed

In this case we shift l pointer index to the mid index of 3 and keep r pointer stationary

Then loop again

```
## Notes