## Docs for maze-gen solving API

### Exports

Async function, params:
```
maze -> 2D array of SquareRender instances,
hookFn -> async function
```
Return value:
```
maze (same as param)
```

### Constraints

Everytime a change is made on the maze array (i.e. continue path):
```js
await hookFn(maze);
```

### SquareRender API

```js
Properties:
- open : { up, right, down, left } <booleans> // Which sides of this square have walls, 4 booleans
- visited : <boolen> // If this sqaure has been visited

Methods:
- visit (sidesArr <number array (range 0 - 3) (ideal count 2)>) // When a player enters a Square. Normal use: visit( [entrySide, exitSide] ). Returns the instance.
- unvisit () // Reverse all visits through .visit(...). Returns the instance.
- markGoal () // Mark this sqaure as a goal.
        
Meta:
- Sides layout:
    Top : 0,
    Right : 1,
    Down : 2,
    Left : 3
```
