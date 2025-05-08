# Valid Sudoku
## Code
``` js
const isValidSudoku = (board) => {
  const rows = Array.from({ length: 9 }, () => new Set())
  const colums = Array.from({ length: 9 }, () => new Set())
  const box = Array.from({ length: 9 }, () => new Set())

  for (let i = 0; i < 9; i++) {
    for (let j = 0; j < 9; j++) {
      const val = board[i][j];

      if(val === '.') {
        continue;
      }

      const boxId = Math.floor(i / 3) * 3 + Math.floor(j / 3);

      if (rows[i].has(val) || colums[j].has(val) || box[boxId].has(val)) {
        return false;
      }

      rows[i].add(val);
      colums[j].add(val);
      box[boxId].add(val);
    }
  }
  return true;
}
```

## The idea breaks down to:
- Determine if a `9 x 9` Sudoku board is valid.
	1. Each row must contain the digits `1-9` without repetition.
	2. Each column must contain the digits `1-9` without repetition.
	3. Each of the nine `3 x 3` sub-boxes of the grid must contain the digits `1-9` without repetition.
- Using this break down we can use a few assumptions
	- we can use sets to ensure there aren't any repeating numbers
		- `Array.from({ length: 9 }, () => new Set())`
	- A matrix will need a double for loop
```
for (let i = 0; i < 9; i++) {
    for (let j = 0; j < 9; j++) {
		const val = board[i][j];
   }
}
```
- row/columns can be easily found using i and j
- for the boxes we need a different approach
	- `Math.floor(i / 3) * 3 + Math.floor(j / 3);`
	- this creates a box by index and pushes between 0-9
- before we push to any of the array of sets we can check in the if block first to return false if there
- otherwise push into array of sets
## Notes
- the problem can be seen from a more "human" view by breaking it down by row/column/box
``` js
var isValidSudoku = function (board) {
	let subBoxes = [[], [], []];
	for (let i = 0; i < 9; i++) {
		// grab a row and check for dupes
		let row = board[i].filter(x => x !== '.');
		if (new Set([...row]).size !== row.length) return false;
		
		// grab a column and check for dupes
		let column = board.map(x => x[i]).filter(x => x !== '.');
		if (new Set([...column]).size !== column.length) return false;
		
		// create subboxes
		// probably can be done with a forEach
		subBoxes[0].push(...board[i].slice(0, 3));
		subBoxes[1].push(...board[i].slice(3, 6));
		subBoxes[2].push(...board[i].slice(6));
		
		if (subBoxes[2].length === 9) {
			for (let j = 0; j < 3; j++) {
				let subBox = subBoxes[j].filter(x => x !== '.');
				if (new Set([...subBox]).size !== subBox.length) return false;
			}
			subBoxes.length = 0;
			subBoxes = [[], [], []];
		}
	}
	return true;
};
```