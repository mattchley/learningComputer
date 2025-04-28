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
1. We need to iterate through the string and add/remove from the stack when there is a valid and opposite parentheses
2. there needs to be a stack to store the elements that have been seen but not partnered
3. an obj/hash will be used if the opposite parentheses match
4. As we iterate through the loop is the stack ends up empty we have valid parentheses if not it is invalid.
## Notes
