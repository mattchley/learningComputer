# Two Sum
## Code
``` js
var twoSum = function(nums, target) {
	for(let i = 0; i < nums.length; i++){
		let num = nums[i]
		let secondNumIndex = nums.indexOf(target- num)
		if(secondNumIndex !== -1 && secondNumIndex !== i) {
			return [i, secondNumIndex]
			}
	}
};
```

## The idea breaks down to:
- Find the two numbers that add up to the target number from an array and return the index of the numbers
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
```
- Sorting is not advisable because the answer is returning the index not the actual numbers
- Straight forward is to:
	- loop through array by index
	- subtract the indexed number by the target
	- search for the difference
	- the only problem is if there is a repeating number 
## Notes
- we can account for the repeating numbers by creating an obj to store what has been passed over
``` js
    const pairIdx = {};

    for (let i = 0; i < nums.length; i++) {
        const num = nums[i];
        if (target - num in pairIdx) {
            return [i, pairIdx[target - num]];
        }
        pairIdx[num] = i;
    }    
```