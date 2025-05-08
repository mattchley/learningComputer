# Product of Array Except Self
## Code
``` js
var productExceptSelf = function (nums) {
    const res = Array(nums.length).fill(1);

    let left = 1;
    for (let i = 0; i < nums.length; i++) {
        res[i] *= left;
        left *= nums[i];
    }

    let right = 1;
    for (let i = nums.length - 1; i >= 0; i--) {
        res[i] *= right;
        right *= nums[i];
    }

    return res;
};
```

## The idea breaks down to:
- Multiply all numbers in array except itself
``` js
[1,2,3,4] -> [24,12,8,6]
index 0 = 2*3*4
index 1 = 1*3*4
index 2 = 1*2*4
index 3 = 1*2*3
```
- First thought is to use a map and reduce and to have an exception based on index to prevent multiplying itself
	- This does work but is not the optimal nor the fastest way to do so
``` js
function productOfArrayExceptSelf(array){
    return array.map(function (_, i) {
        return array.reduce(function (acum, val, j) {
            return acum * (i === j ? 1 : val);
        }, 1);
    });
}
```
- The optimal solution is to take a prefix sum approach
- Start by creating the res array full of 1s
	- any number multiplied by 1 is itself
- Then we apply a version of a reduce method going left and right
	- where the left/right is the accum
	- the first line is the actual math that we put in the resArr by multiplying it by the value in the array
	- the second line updates the accum value to be used in the next iteration
- 
## Notes