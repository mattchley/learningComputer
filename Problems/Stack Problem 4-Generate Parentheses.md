## Code
``` js
var generateParenthesis = function(n) {
	const resArray = [];
	const dfs = (lParenthesis, rParenthesis, string) => {
		if (lParenthesis === rParenthesis 
			&& lParenthesis + rParenthesis === n * 2) {
			resArray.push(string);
			return;
		}
	
		if (lParenthesis < n) {
			dfs(lParenthesis + 1, rParenthesis, string + "(");
		}
	
		if (rParenthesis < lParenthesis) {	
			dfs(lParenthesis, rParenthesis + 1, string + ")");
		}

}
dfs(0, 0, "");

return resArray;  
```

## The idea breaks down to:
- Given a number generate all possible combinations of parenthesis
- returns an array of strings
- Requires a [[depth first search approach]] similar to a tree traversal technique
	- **My brain was thinking about how the code could keep track of all the permutations. In the the future when I feel this, keep a DFS in mind**
	- so a 3 parentheses problems yields : ["((()))","(()())","(())()","()(())","()()()"]
	- As the number grows we have to be mindful of the repeating structures
	- all together ala the first 2 in the array
	- separated ala the next 2
	- and fully separated
- First we need to create a recursive function to invoke the depth first search as we create and push the strings to the array.
- Depth first search will  do 1 of 3 things
	- if the count of the available parentheses is equal and the sum is equal to the number desired times 2 push the resulting string to the resArray
	- otherwise add a parenthesis based on the counts of the left or right
		- the count on the parenthesis goes up one and then add a corresponding parenthesis to the string
## Notes