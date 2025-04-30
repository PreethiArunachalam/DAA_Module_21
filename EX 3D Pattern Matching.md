# EX 3D Pattern Matching
## DATE: 29/03/25
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm
1. Initialize two pointers i (for s1) and j (for s2) at 0.
2. Compare characters of s1 and s2 at current positions:
 . If characters match, increment both i and j.
 . If characters do not match, reset i to i - j + 1 and j to 0.
3. Repeat step 2 until either:
4. All characters of s2 are matched (j == len(s2)), or
5. End of s1 is reached.
6. If a match is found, return the starting index i - len(s2).
7. If no match is found, return 0.

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: Preethi A A 
Register Number: 212222110035 
*/
```
```
def BF(s1,s2):
    #Start here
    i = 0
    j = 0
    while(i < len(s1) and j < len(s2)):
        if(s1[i] ==  s2[j]):
            i += 1
            j += 1
        else:
            i = i - j + 1
            j = 0
    if(j >= len(s2)):
        return i - len(s2)
    else:
        return 0
    #End here
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)
```
## Output:

![image](https://github.com/user-attachments/assets/6713449a-b45b-4f87-907e-98e6ed55de5c)

## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
