## Code
``` js
var dailyTemperatures = function (temperatures) {
	let stack = [];
	let resArray = Array(temperatures.length).fill(0)
	
	for (let i = 0; i < temperatures.length; i++) {
		while (stack.length > 0 &&
		temperatures[i] > temperatures[stack[stack.length - 1]]) {
			const idx = stack.pop();
			resArray[idx] = i - idx;
		}
		stack.push(i);
	}
	return resArray;
};
```

## The idea breaks down to:
- Given an array of temps determine the wait for a hotter day
```
**Input:** temperatures = [73,74,75,71,69,72,76,73]
**Output:** [1,1,4,2,1,1,0,0]
```
- First thoughts
	- using a stack will allow this to go through at linear time
	- keep the current temp and see if the next is bigger
	- if not add to stack
	- when one is found return stack length and pop the first!
	- if no bigger is found next keep stack clear
- Had a great first impression on how to solve this. But was uncertain about how to keep the temps tracked
	- upon looking at the answer it is a combo of a for loop and while loop
		- I was trying to figure it out one or the other.
## Notes