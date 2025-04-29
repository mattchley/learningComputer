## Code
``` js
var MinStack = function() {
	this.stack =[];
};

MinStack.prototype.push = function(val) {
	let min_val = this.getMin();
	if (min_val === null || min_val > val) {
		min_val = val;
	}
	this.stack.push([val, min_val])
};

  
/**
* @return {void}
*/

MinStack.prototype.pop = function() {
	this.stack.pop()
};

  
/**
* @return {number}
*/

MinStack.prototype.top = function() {
	return this.stack.length ? this.stack[this.stack.length - 1][0] : null;
};

  
/**
* @return {number}
*/

MinStack.prototype.getMin = function() {
	return this.stack.length ? this.stack[this.stack.length - 1][1] : null;
};
```

## The idea breaks down to:
Follow the creation of a custom stack class like on the main page.
The only difference is the check for the minStack in the push function.
The push function stores an array in the stack that has the values sorted already. 
%% Making a psuedo bubble sort %%
```
value being pushed -> [2, -1]
```
As a result any retrieval will be an array with 2 elements in it thus:
- top() returns the first in the array
- getMin returns the second in array
## Notes