## Code
``` js
let stack = [];

let parentheses = {
	')': '(',
	'}': '{',
	']': '[',
}

// for loop to iterate
for (const c of s) {
		if (Object.values(parentheses).includes(c)) {
			stack.push(c);
		} else if (parentheses.hasOwnProperty(c)) {
			if (!stack.length || parentheses[c] !== stack.pop()) {
				return false;
			}
	}
}

return stack.length === 0
```
Code above solves the problem with obj/hash implementation

The idea breaks down to:
1. Based on the parameters of the question _Every close bracket has a corresponding open bracket of the same type_ so we can set our code to look for closing brackets more than opening.
2. We need to iterate through the string and add/remove from the stack when there is a valid and opposite parentheses
3. there needs to be a stack to store the elements that have been seen but not partnered
4. an obj/hash will be used if the opposite parentheses match
5. As we iterate through the loop is the stack ends up empty we have valid parentheses if not it is invalid.
## Notes
The flow that occurs with "([])"
	1. The loop grabs "(" and the stack is empty
	2. Object.values is looking for a corresponding closing 