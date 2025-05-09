----
### Basic Functionality: 
- Binary Search is a searching technique that works on the Divide and Conquer approach. It is used to search for any element in a sorted array.

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
1. [[Binary Search Problem 1-Binary Search]][https://leetcode.com/problems/binary-search/]
2. [[Binary Search Problem 2-Search a 2D Matrix]][https://leetcode.com/problems/search-a-2d-matrix/]
3. [[Binary Search Problem 3-Koko Eating Bananas]][https://leetcode.com/problems/koko-eating-bananas/]
4. [[Binary Search Problem 4-Find Minimum In Rotated Sorted Array]][https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/]
5. [[Binary Search Problem 5-Search In Rotated Sorted Array]][https://neetcode.io/problems/find-target-in-rotated-sorted-array]
6. [[Binary Search Problem 6-Time Based Key Value Store]][https://leetcode.com/problems/time-based-key-value-store/]
7. [[Binary Search Problem 7-Median of Two Sorted Arrays]][https://neetcode.io/problems/median-of-two-sorted-arrays]

