## Code
``` js

```

## The idea breaks down to:
- We are given our end point, cars at their distances and the speed of those cars indexed at 0 in an array
```
target = 100, position = [0,2,4], speed = [4,2,1]

step 1
position = [4,4,5], speed = [4,2,1]
fleet [position[0], position[1]] going at slowest speed, 2

Step 2
position = [6,6,6], speed = [2,2,1]
fleet [position[0], position[1], position[2]] going at slowest speed, 1

etc.
a fleet of 3 cars reaches target 100
```
- we are looking for the fleets (groups of cars at the same distance) that arrive at the same time
- Start with initial position
- update position based on speed
- if they meet up they stay at the slowest speed
- the cars move left to right
- First thoughts
	- keep the cars in a map? that way we keep the base speed for when they meet with other cars?
	- have an initial go through by adding the speeds to their indexed counterpoint in position
	- will have to do a while loop to keep adding until they reach the target
	- go with a reducing func
		- if the cars will not catch up to them remove from the array?
	- The cars that are closer to the end are less likely to get in a fleet
## Notes