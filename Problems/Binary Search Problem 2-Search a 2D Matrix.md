# Search a 2D Matrix
## Code
``` js
var searchMatrix = function(matrix, target) {
	if(matrix==null||matrix.length==0||matrix[0].length==0)return false;
	
	let mLength = matrix.length;
	let rowLength = matrix[0].length
	let l = 0
	
	// grabs the length of the matrix back to back
	let r = mLength * rowLength -1
	
	while(l<=r){
		// mid point of all the arrays
		let mid = Math.floor((l + r) / 2);
		// the val associtated with the index
		let val = matrix[Math.floor(mid / rowLength)][mid % rowLength];
		
		if (val === target)return true;
		// if val isnt right adjust the pointers
		
		if (val < target)
			l = mid + 1;
		else
			r = mid - 1;
		}
	
	return false
};
```

## The idea breaks down to:
- Given an array of arrays with the features below, find the target value
	- ascending number order
	- each row is bigger than the last
```
matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
*is what it would look like
[1,  3,  5,   7]
[10, 11, 16, 20]
[23, 30, 34, 60]
```
- In the constraints there is nothing saying that the rows and columns will be equal so we must account for these edgecases
- First thoughts are essentially combining the two pointer structure into a matrix capacity.
	- using the while loop and have checks inside the a singular array and a singular row
- 
## Notes
- some of the best times do use a double loop mechanism to access and find the value in the matrix
``` js
var searchMatrix = function(matrix, target) {
    const lenI = matrix.length;
    const lenJ = matrix[0]?.length;
    for(let i=0; i <= lenI -1; i++){
        for(let j=0; j <= lenJ - 1; j++){
            if(matrix[i][j] == target) return true
        }
    }
    return false
};
```
