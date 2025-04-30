----
### Basic Functionality
- Follows a First In, First Out structure.
- What ever is the most recent thing added to stack is what will be removed first.
- has 5 typical functions
	- push - adds to the stack
	- pop - removes and returns the item from the stack
	- peek - returns the first item on the stack
	- isEmpty - checks if the stack has items in it, returns true/false
	- size - returns how many items in a stack
### When to implement
- 
----
### How to implement
1. Using an array for quick usage
	``` js
const stack = [];

stack.push("item1");
stack.push("item2");
stack.push("item3");
%% ["item1", "item2", "item3"] %%

stack.pop();
%% "item1" %%
%% ["item2", "item3"]  %%

stack[0];
%% "item2"  %%

Array.isArray(stack) && stack.length === 0;
%% false %%

stack.length;
%% 2 %%
```
2. Creating your own class to implement a stack
``` js
class Stack{
	constructor(){
		this.items = [];
	}
%% push function %%
	push(element){
	this.items.push(element)
	}

%% pop function %%
	pop(){
	if(this.isEmpty()){
		return "stack is Empty"
	}
	return this.items.pop()
	}

%% peek function %%
	peek(){
	if(this.isEmpty()){
		return "stack is Empty"
	}
	reutn this.items[this.items.length - 1]
	}

%% isEmpty function %%
	isEmpty(){
	return this.items.length === 0
	}

%% size function %%
	size(){
	return this.items.length
	}
}
```
----
### Sample Problems: 
LeetCode filtered for Stacks https://leetcode.com/problem-list/stack/
1 - Basic  practice [ https://leetcode.com/problems/baseball-game/description/?envType=problem-list-v2&envId=stack]
2 - set up and list of problems at bottom [https://www.geeksforgeeks.org/implementation-stack-javascript/#]

### Neetcode Problems
1. [[Stack problem 1-Valid Parentheses]] [https://leetcode.com/problems/valid-parentheses/description/]
2. [[Stack problem 2-Min Stack]] [https://leetcode.com/problems/min-stack/]
3. [[Stack Problem 3-Evaluate Reverse Polish Notation]] [https://leetcode.com/problems/evaluate-reverse-polish-notation/description/]
4. Generate Parentheses [https://leetcode.com/problems/generate-parentheses/]
5. Daily Temperatures [https://leetcode.com/problems/daily-temperatures/]
6. Car Fleet [https://leetcode.com/problems/car-fleet/]
7. Largest Rectangle in Histogram [https://neetcode.io/problems/largest-rectangle-in-histogram]


[[Stack Practice]]