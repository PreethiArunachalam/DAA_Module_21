# EX 3A Knight Tour & Count Path
## DATE: 18/03/25
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight

## Algorithm
1. Define all 8 possible moves a knight can make. Create a queue and insert the starting position with distance = 0.
2. Use a 2D list to keep track of visited positions to avoid cycles or re-processing.
3. While the queue is not empty, remove the front cell and check if it's the target.
4. For each of the 8 possible knight moves, if the new position is within bounds and not visited, mark it visited and add it to the queue with distance +1.
5. If the target is reached, return the current distance. If the queue is exhausted without reaching the target, return infinity.

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: Preethi A A 
Register Number: 212222110035 
*/
```
```
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
     
    # add your code here
    dx =[-2, -1, 1, 2, -2, -1, 1, 2]
    dy =[-1, -2, -2, -1, 1, 2, 2, 1]
    
    queue = []
    queue.append(cell(knightpos[0], knightpos[1],0))
    
    visited = [[False for _ in range(N+1)] for _ in range(N+1)]
    visited[knightpos[0]][knightpos[1]] =True
    
    while len(queue)>0:
        curr = queue.pop(0)
        
        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist
        
        for i in range(8):
            x = curr.x +dx[i]
            y = curr.y +dy[i]
            
            if isInside(x,y,N) and not visited[x][y]:
                visited[x][y]= True
                queue.append(cell(x,y,curr.dist+1))
    return float('inf')
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```
## Output:

![image](https://github.com/user-attachments/assets/5ac1b792-3b8b-42ee-8132-8510a24ed959)

## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
