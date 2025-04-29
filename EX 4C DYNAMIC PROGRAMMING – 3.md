# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:29.4.25
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.
## Algorithm
1. Input a string of length n.

2. Consider all possible substrings of the input string.

3. For each substring, check if the first and last characters are the same:
   - If yes, add 2 to the result from the inner substring.
   - If not, take the maximum length found by either removing the first or the last character.

4. Start with substrings of length 1 and build up to the full string length.

5. The result is the maximum length found where characters form the same sequence forwards and backwards.
  

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it
Developed by: Soundariyan MN
Register Number: 212222230146 
*/
def Lps(X):
    n=len(X)
    dp=[[0 for _ in range(n)] for _ in range(n)]
    for x in range(n):
        dp[x][x]=1
    for l in range(2,n+1):
        for i in range(n-l+1):
            j=i+l-1
            if X[i]==X[j]:
                dp[i][j]=dp[i+1][j-1]+2
            else:
                dp[i][j]=max(dp[i+1][j],dp[i][j-1])
    return dp[0][n-1]
X=input()
print("The length of the LPS is",Lps(X))
        
```

## Output:

![Screenshot 2025-04-29 143307](https://github.com/user-attachments/assets/2917a518-26d5-4c3f-bd89-650527533b39)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
