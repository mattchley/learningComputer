# Top K Frequent Elements
## Code
``` js
var topKFrequent = function(nums, k) {
	let map = new Map();
	
	nums.forEach(ele=>map.set(ele, (map.get(ele) || 0) + 1))

	let sorted = Array.from(map.entries()).sort((a, b) => b[1] - a[1]);
	
	return sorted.slice(0, k).map(entry => entry[0]);
};
```

## The idea breaks down to:
- given an array of numbers and a target frequency return an array of the numbers at or above the target frequency
- Create a Map and loop through the array to get the frequency of any number
- Now we have their frequencies we can sort them by their entries (aka the key and value)
	- the entries are accessed as an array [ 1 , 3]
	- one being the number in the original array and three is the frequency
	- so when we sort we have to grab the array at index 1
- Now that the array is sorted we can slice the array based on the cut off at K
	- it'll be in descending order due to the b-a
- then we can map that slices array based on the key
## Notes