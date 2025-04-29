# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 15.04.2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Start the program.
2. Input the number of vertices V and the adjacency matrix graph representing the graph.
3. Input the number of colors m.
4. Initialize a list colour of size V with all values 0 (indicating no colors assigned yet).
5. Call the recursive utility function graphColourUtil(m, colour, 0) starting from vertex 0.
6. If the utility function returns True, print the color assigned to each vertex.
7. Else, print "Solution does not exist".
8. End the program.


## Program:
```
Program to implement Graph Coloring Problem using backtracking.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
class Graph():
    def __init__(self, vertices):
        self.V=vertices
        self.graph=[[0 for column in range(vertices)] for row in range(vertices)]
        
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
     
    def graphColourUtil(self, m, colour, v):
        if v==self.V:
            return True          
        for c in range(1, m+1):
            if self.isSafe(v, colour, c)==True:
                colour[v]=c
                if self.graphColourUtil(m, colour, v+1)==True:
                    return True
                colour[v]=0
       
    def graphColouring(self, m):
        colour=[0]*self.V
        if self.graphColourUtil(m, colour, 0)==None:
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c, end=' ')
        return True
```


## Output:

![image](https://github.com/user-attachments/assets/7d70854b-9846-4fb2-b63b-d71d349bb95c)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
