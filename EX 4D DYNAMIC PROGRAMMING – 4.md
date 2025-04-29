# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:29.04.25
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.
## Algorithm
1. Input two strings: str1 and str2.

2. If either string is empty, return the length of the other string (insert all remaining characters).

3. If the last characters of both strings match, make a recursive call by reducing both strings by one character.

4. If the last characters don’t match, recursively compute the minimum of:
   - Inserting a character,
   - Deleting a character,
   - Replacing a character,
   then add 1 to the result for the current operation.

5. Repeat this process until both strings are empty or matched, and return the minimum number of operations needed.
   

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method
Developed by: Soundariyan MN
Register Number: 212222230146
*/
def ed(x,y,m,n):
    if m==0:
        return n
    if n==0:
        return m
    if x[m-1]==y[n-1]:
        return ed(x,y,m-1,n-1)
    return 1+min(ed(x,y,m-1,n-1),ed(x,y,m,n-1),ed(x,y,m-1,n))
x=input()
y=input()
print("Edit Distance",ed(x,y,len(x),len(y)))
```

## Output:

![Screenshot 2025-04-29 143507](https://github.com/user-attachments/assets/a24851dc-a8b6-420a-8955-c4bd140d420c)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
