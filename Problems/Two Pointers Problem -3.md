# 3Sum
## Code
``` js
var threeSum = function(nums) {
    let res = [];
    nums.sort((a, b) => a - b);

    for (let i = 0; i < nums.length; i++) {
        if (i > 0 && nums[i] === nums[i-1]) {
            continue;
        }
        
        let j = i + 1;
        let k = nums.length - 1;

        while (j < k) {
            let total = nums[i] + nums[j] + nums[k];

            if (total > 0) {
                k--;
            } else if (total < 0) {
                j++;
            } else {
                res.push([nums[i], nums[j], nums[k]]);
                j++;

                while (nums[j] === nums[j-1] && j < k) {
                    j++;
                }
            }
        }
    }
    return res;    
};
```

## The idea breaks down to:
- loop through an array and find the 3 numbers that sum up to zero
	- return the 3 different numbers in an array of array where there indexes are all different
	- Valid : `-1,-1,2`
	- the must be distinct triplets meaning `-1,-1,2` and `-1,2,-1` are just 1 triplet
```
Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
```
- First thoughts we can sort the numbers in ascending order to quickly jump over the first number of the triplet
```
nums = [-1,0,1,2,-1,-4] -> [-4,-1,-1,0,1,2]
```
- after the sort we need a consistent holder of the first number
	- using a for loop we can set the base number
- once we have the base number we can use more typical two pointer formulation

## Notes
- maybe use a set to prevent duplicate triplets from being used?