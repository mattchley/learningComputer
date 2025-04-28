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
	}

%% size function %%
}
```
----
### Sample Problems: 
LeetCode filtered for Stacks https://leetcode.com/problem-list/stack/
1 - Basic  practice [ https://leetcode.com/problems/baseball-game/description/?envType=problem-list-v2&envId=stack]