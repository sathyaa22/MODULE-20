# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 31.03.2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start the program.
2. Initialize the maze as a 2D list of size N x N, containing 1s (open path) and 0s (blocked).
3. Create a solution matrix sol of the same size initialized to 0.
4. Call the recursive utility function solveMazeUtil(maze, 0, 0, sol) starting from cell (0,0).
5. If solveMazeUtil returns True:
   Print the solution matrix.
6. Else:
   Print "Solution doesn't exist".
7. End the program.
   

## Program:
```
Program to implement Rat in a Maze.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
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
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]    
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False    
    printSolution(sol)
    return True     

def solveMazeUtil(maze, x, y, sol):
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
    if isSafe(maze, x, y) == True:
        sol[x][y] = 1
        if solveMazeUtil(maze, x+1, y, sol) == True:
            return True
        if solveMazeUtil(maze, x, y+1, sol) == True:
            return True
        sol[x][y] = 0
        return False

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]              
    solveMaze(maze)
```


## Output:

![image](https://github.com/user-attachments/assets/452bf100-6a3f-44ad-8ae6-cb087900901a)


## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
