# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:29.04.25
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm
1. Input: Two strings X of length m and Y of length n.

2. Create a 2D table `dp` of size (m+1) x (n+1), initialized with 0.

3. For each character in X and Y:
   - If X[i-1] == Y[j-1], set dp[i][j] = dp[i-1][j-1] + 1.
   - Track the maximum value in dp[i][j] and its position (this gives the longest substring length and endpoint).

4. After filling the table, use the max value to retrieve the substring from either X or Y.

5. Output: The longest common substring and its length.
   

## Program:
```
/*
Program to implement the longest common substring problem.
Developed by: Soundariyan MN
Register Number: 212222230146 
*/
def LCS(X, Y, m, n):
 
    maxLength = 0          
    endingIndex = m        
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]
if __name__ == '__main__':
    X = input()
    Y = input()
    m = len(X)
    n = len(Y)
    print('The longest common substring is', LCS(X, Y, m, n))

```

## Output:
![Screenshot 2025-04-29 143059](https://github.com/user-attachments/assets/90d31491-2152-48bf-b055-38e1b374d224)



## Result:
Thus the program was executed successfully for finding the longest common substring .
