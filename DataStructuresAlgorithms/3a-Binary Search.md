----
### Basic Functionality: 
%% what functions can be used on the structure include time complexities%% 

### When to implement
- 
----
### How to implement
- using a while loop the basic implementation looks like
``` js
const iterativeFunction = (arr, target) => {
    let start = 0, end = arr.length - 1;

    // Iterate while start not meets end
    while (start <= end) {

        // Find the mid index
        let mid = Math.floor((start + end) / 2);

        // If element is present at 
        // mid, return True
        if (arr[mid] === target) return true;

        // Else look in left or 
        // right half accordingly
        else if (arr[mid] < target)
            start = mid + 1;
        else
            end = mid - 1;
    }

    return false;
}

```
- using a recursive implementation
``` js
const recursiveFunction = (arr, target, start, end) => {

    // Base Condition
    if (start > end) return false;

    // Find the middle index
    let mid = Math.floor((start + end) / 2);

    // Compare mid with given key x
    if (arr[mid] === target) return true;

    // If element at mid is greater than x,
    // search in the left half of mid
    if (arr[mid] > target)
        return recursiveFunction(arr, target, start, mid - 1);
    else

        // If element at mid is smaller than x,
        // search in the right half of mid
        return recursiveFunction(arr, target, mid + 1, end);
}
```

### Neetcode Problems: 
1. Binary Search Problem 1-Binary Search
2. Binary Search Problem 2-Search a 2D Matrix
3. Binary Search Problem 3-Koko Eating Bananas
4. Binary Search Problem 4-Find minimum 
5. Binary Search Problem 5-
6. Binary Search Problem 6-
7. Binary Search Problem 7-

