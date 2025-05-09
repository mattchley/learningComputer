# Container With Most Water
## Code
``` js
var maxArea = function(height) {
	let maxArea = 0;
	
	let l = 0;
	let r = height.length - 1;
	
	while (l < r) {
		// calculate the currentArea and test for Max Area
		maxArea = Math.max(maxArea, (r - l) * Math.min(height[l], height[r]));
		
		// adjust positions based on which pointer is taller
		if (height[l] < height[r]) {
			l++;
		} else {
			r--;
		}
	}
	return maxArea;
};
```

## The idea breaks down to:
- Given an array of numbers that represent the height of a container determine the two best heights and single best distance between to return the highest volume.
```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
```
- if we select the heights at index 1 and index 8 we can multiply the smallest height of the 2 selected and the distance to determine the volume
	- smallest height is 7
	- longest distance is 7
	- 7 x 7 = 49
- First thought is to use a two pointer to dynamic shift and check the volume as we go through the array
- in the while loop we need to keep track of the current max volume and check against previous maxes
	- We can use the built in `Math.max()` and `Math.min()` methods to do this as we go
- then move the pointers based on the results
## Notes