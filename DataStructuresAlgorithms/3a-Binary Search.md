----
### Basic Functionality: 
%% what functions can be used on the structure include time complexities%% 

### When to implement
- 
----
### How to implement
- using a while loop the basic implementation looks like
``` js
const iterativeFunction = ()=>(arr, x) {
    let start = 0, end = arr.length - 1;

    // Iterate while start not meets end
    while (start <= end) {

        // Find the mid index
        let mid = Math.floor((start + end) / 2);

        // If element is present at 
        // mid, return True
        if (arr[mid] === x) return true;

        // Else look in left or 
        // right half accordingly
        else if (arr[mid] < x)
            start = mid + 1;
        else
            end = mid - 1;
    }

    return false;
}

```
- using a recursive implementation
``` js
const recursiveFunction = function (arr, x, start, end) {

    // Base Condition
    if (start > end) return false;

    // Find the middle index
    let mid = Math.floor((start + end) / 2);

    // Compare mid with given key x
    if (arr[mid] === x) return true;

    // If element at mid is greater than x,
    // search in the left half of mid
    if (arr[mid] > x)
        return recursiveFunction(arr, x, start, mid - 1);
    else

        // If element at mid is smaller than x,
        // search in the right half of mid
        return recursiveFunction(arr, x, mid + 1, end);
}
```

### Neetcode Problems: %% add links to the leetCode problems below and create separate notes for each %%
1. 

