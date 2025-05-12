----
### Basic Functionality: 
%% what functions can be used on the structure include time complexities%% 

### When to implement
- 
----
### How to implement
%% include base set up for code %%
``` js
const iterativeFunction = (arr, target) => {
    let start = 0, end = arr.length - 1;

    // Iterate while start not meets end
    while (start <= end) {

        if (arr[mid] < target)
            start = mid + 1;
        else
            end = mid - 1;
    }

    return false;
}

```


### Neetcode Problems: 
1. [[Two Pointers Problem -1]][https://leetcode.com/problems/valid-palindrome/]
2. [[Two Pointers Problem -2]][https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/]
3. [[Two Pointers Problem -3]][https://leetcode.com/problems/3sum/]
4. [[Two Pointers Problem -4]][https://leetcode.com/problems/container-with-most-water/]
5. [[Two Pointers Problem -5]][https://leetcode.com/problems/trapping-rain-water/]

