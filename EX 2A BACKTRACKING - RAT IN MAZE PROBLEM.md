# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To write a Python program to solve the Rat in a Maze problem using backtracking, where the rat must find a path from the top-left corner to the bottom-right corner of a maze represented by a 2D matrix.


## Algorithm
Start the program.

Initialize the maze as a 4 × 4 grid, where 1 represents a valid path and 0 represents a blocked path.

Create a solution matrix sol of the same size, initialized with 0.

Define a function isSafe(maze, x, y) to check if the current cell (x, y) is within bounds and open (1).

Define a recursive function solveMazeUtil(maze, x, y, sol) that:

Marks the current cell (x, y) in sol.

Checks if the destination (N-1, N-1) is reached; if yes, return True.

Moves forward in the maze by:

Trying the downward move (x+1, y).

Trying the rightward move (x, y+1).

If both moves fail, backtrack by resetting sol[x][y] = 0 and return False.

In the main function solveMaze(maze):

Call solveMazeUtil(maze, 0, 0, sol).

If a solution exists, print the solution matrix.

Otherwise, display "Solution doesn't exist".

Stop the program.  

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: Dinesh M
Register Number:212222040039

N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False



if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)



*/
```

## Output:

<img width="1259" height="377" alt="Screenshot 2025-09-07 171924" src="https://github.com/user-attachments/assets/ba91f368-729f-4977-8423-3c3a9aed5a7f" />


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
