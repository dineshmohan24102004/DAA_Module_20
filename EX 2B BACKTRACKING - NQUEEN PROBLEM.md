# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
Start the program.

Read the value of N (size of the chessboard).

Initialize an N × N board with all entries as 0.

Define the function isSafe(board, row, col) to check if a queen can be safely placed at (row, col) by verifying:

No queen exists in the same row on the left side.

No queen exists in the upper left diagonal.

No queen exists in the lower left diagonal.

Define the recursive function solveNQUtil(board, col) which:

Returns True if all queens are placed (col >= N).

Otherwise, for each row in the current column:

If isSafe is true, place a queen (board[row][col] = 1).

Recursively call solveNQUtil for the next column.

If recursion fails, backtrack by removing the queen (board[row][col] = 0).

In solveNQ():

Call solveNQUtil(board, 0).

If a solution exists, print the board configuration with queens placed as 1.

Otherwise, display "Solution does not exist".

Stop the program. 

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: Dinesh M
Register Number: 212222040039

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    for i in range(N):
        if isSafe(board, i, col):
            board[i][col]=1
            if solveNQUtil(board, col+1):
                return True
            board[i][col]=0
    return False
      
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

*/
```

## Output:

<img width="1277" height="445" alt="Screenshot 2025-09-07 172206" src="https://github.com/user-attachments/assets/3b12f6d8-6120-42cb-90ca-f51f5f7c006a" />


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
