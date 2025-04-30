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
The main take away here is knowing that keep nums until and operator and then do the two nums

## Notes