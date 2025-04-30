# EX 3B Hamiltonian Circuit Problem
## DATE: 22/03/25
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Initialize a path list of size N with all values as -1, and set the starting vertex path[0] = 0.
2. Define a recursive function to try adding all unvisited vertices to the path, one by one.
3. At each step, check if the current vertex is adjacent to the previous vertex and has not been used yet.
4. If a valid vertex is found, place it in the path and recursively check the next position.
5. If the full path of length N is built, return True; if no valid path is found, return False.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: Preethi A A 
Register Number: 212222110035
*/
```
```
def Hamiltonian_path(adj, N):
    def is_hamiltonian_path(path, pos):
        if pos == N:
            return True
        
        for v in range(N):
            if adj[path[pos - 1]][v] == 1 and v not in path:
                path[pos] = v
                
                if is_hamiltonian_path(path, pos + 1):
                    return True
                
                path[pos] = -1
        
        return False

    path = [-1] * N
    
    path[0] = 0
    
    if not is_hamiltonian_path(path, 1):
        return False
    
    return True
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```
## Output:

![image](https://github.com/user-attachments/assets/e8de5ae0-637c-43f6-85b5-307fa02c13da)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
