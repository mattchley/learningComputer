## Code
``` js
/**
* @param {string[]} tokens
* @return {number}
*/

var evalRPN = function (tokens) {
	let stack = [];
	for (let c of tokens) {
		switch (c) {
			case "+":
				stack.push(stack.pop() + stack.pop());
				break;
			case "-":{
				let second = stack.pop();
				let first = stack.pop();
				stack.push(first - second);
				break;
			}
			case "/":{
				let second = stack.pop();
				let first = stack.pop();
				stack.push(parseInt(first / second));
				break;
			}
			case "*":
				stack.push(stack.pop() * stack.pop());
				break;
			default:
			stack.push(parseInt(c));
		}
	}

	return stack[0];
};
```

## The idea breaks down to:
- The main take away here is we need numbers more than we need the operators
- the stack will hold numbers until we hit a operator
- then we use a switch case to determine the order of operations
	- Pay particular attention to '-' and '/' because their positioning matters
- After the operation is done we have to store the resulting value in the stack
- as we do several steps the resulting values gets closer to the beginning of the stack
- return stack[0] for the ultimate result

## Notes
1. Youtube vid for a guided view :https://www.youtube.com/watch?v=xWSO1PF8AwI
2. this can be done with a if/else statement but 