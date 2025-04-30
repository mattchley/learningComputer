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
- the stack 
the stack ho

## Notes
1. Youtube vid for info :https://www.youtube.com/watch?v=xWSO1PF8AwI