# Contains Duplicate
## Code
``` js
var containsDuplicate = function(nums) {
	let map = new Map();
	let maxIndex = nums.length
	
	for(let i = 0; i< maxIndex; i++){
		let ele = nums[i]
		if(!map.get(ele)){
			map.set(ele, 1)
		} else{
			return true
		}
	}
	return false
};
```

## The idea breaks down to:
- Given an array of numbers return true or false if the array contains duplicates
- Try to go through the array minimally
- best way to check if a num exists is to use the Map data structure to store a number
	- plus the map get function is very fast
- loop through the array
- pushing a number to map if it doesn't exist
- then an if check if it does exist
- if so return false otherwise return true


## Notes
``` js
let set = new Set(nums)
return set.size !== nums.length
```
- Found a faster and more concise of writing the code by using the Set data Structure
- The Set Data Structure already removes duplicates
- So if the resulting Set does not equal the original length of the numbers return true otherwise false
- could also further optimize by using a loop to check the set as it goes to return false earlier 