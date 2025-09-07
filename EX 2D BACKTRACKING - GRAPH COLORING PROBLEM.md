# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM

## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
Start the program.

Define a class Graph with:

__init__(vertices): Initializes the graph with adjacency matrix representation.

isSafe(v, colour, c): Checks if assigning color c to vertex v is valid by ensuring no adjacent vertex already has the same color.

graphColouringUtil(m, colour, v):

If all vertices are assigned colors (v == self.v), return True.

Try all colors 1 to m:

If isSafe is True, assign the color to vertex v.

Recursively assign colors to the remaining vertices.

If recursion fails, backtrack by resetting colour[v] = 0.

If no color can be assigned, return False.

graphColouring(m): Initializes the color list and starts coloring from the first vertex.

Create a graph object with 4 vertices and define the adjacency matrix.

Set m = 3 (maximum colors allowed).

Call the graphColouring(m) function.

If a solution exists, print the assigned colors for each vertex.

Otherwise, print failure.

Stop the program. 

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: Dinesh M
Register Number: 212222040039
class Graph:
    def __init__(self,vertices):
        self.v=vertices
        self.graph=[[0 for column in range(vertices)] for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.v:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=0
        return False
    def graphColouring(self,m):
        colour=[0]*self.v
        if not self.graphColouringUtil(m,colour,0):
            return False
        return colour
g=Graph(4)
g.graph=[[0,1,1,1],[1,0,1,0],[1,1,0,1],[1,0,1,0]]
m=3
result=g.graphColouring(m)
if result:
    print("Solution exist and Following are the assigned colours:")
    for c in result:
        print(c,end=" ")
else:
    print("f")
*/
```

## Output:

<img width="1380" height="444" alt="Screenshot 2025-09-07 172549" src="https://github.com/user-attachments/assets/e98026e3-8fa8-4fe3-b865-8f758c487d43" />


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
