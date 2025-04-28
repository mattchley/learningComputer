## 1: Reverse String
Example: "abc" -> "cba"

``` js
let string = "abc"
let stack = [];
let resString = ""

%% loop through string to add to stack %%
for (let i = 0; i < string.length; i++) {  
	stack.push(string[0])
}

%% now that the string is in the stack we can pop from it and return to new string %%
for (let i = 0; i < stack.length; i++) {
%% pop returns form the end of the array %%
	resstring += stack.pop()
}

return 
```