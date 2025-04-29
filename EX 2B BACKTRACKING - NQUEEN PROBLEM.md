# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 31.03.2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start the program.
2. Input the number N (size of the board and number of queens).
3. Initialize an N x N chessboard with all entries set to 0.
4. Call solveNQUtil(board, 0) to begin placing queens column-wise starting from column 0.
5. If the function returns True, print the board.
6. If it returns False, print "Solution does not exist".
7. End the program.


## Program:
```
Program to implement N-Queen problem using backtracking.
Developed by: SATHYAA R
Register Number: 212223100052 
```

```
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False

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
            if solveNQUtil(board, col+1)==True:
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
 
solveNQ()
```


## Output:

![image](https://github.com/user-attachments/assets/eb868f01-b176-4e81-8868-7c3ea0d96672)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
