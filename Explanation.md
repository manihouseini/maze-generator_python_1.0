# randomized depth first search

## Recursive implementation

The depth-first search algorithm of maze generation is frequently implemented using backtracking. This can be described with a following recursive routine:

    1. Given a current cell as a parameter
    2. Mark the current cell as visited
    3. While the current cell has any unvisited neighbour cells
        a. Choose one of the unvisited neighbours
        b. Remove the wall between the current cell and the chosen cell
        c. Invoke the routine recursively for the chosen cell
    which is invoked once for any initial cell in the area.

## Iterative implementation

A disadvantage of the first approach is a large depth of recursion – in the worst case, the routine may need to recur on every cell of the area being processed, which may exceed the maximum recursion stack depth in many environments. As a solution, the same backtracking method can be implemented with an explicit stack, which is usually allowed to grow much bigger with no harm.

    1. Choose the initial cell, mark it as visited and push it to the stack
    2. While the stack is not empty
        a. Pop a cell from the stack and make it a current cell
        b. If the current cell has any neighbours which have not been visited
            i. Push the current cell to the stack
            ii. Choose one of the unvisited neighbours
            iii. Remove the wall between the current cell and the chosen cell
            iv. Mark the chosen cell as visited and push it to the stack
