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
	this.st.push([val, min_val])
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
	return this.st.length ? this.st[this.st.length - 1][0] : null;
};

  
/**
* @return {number}
*/

MinStack.prototype.getMin = function() {
	return this.st.length ? this.st[this.st.length - 1][1] : null
};
```

## The idea breaks down to:
Follow the creation of a custom stack class like on the main page.
The only difference is the check for the minStack in the push function.
The top() returns 

## Notes