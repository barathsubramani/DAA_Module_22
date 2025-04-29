# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:29.04.25
## AIM:
To find longest common subsequence using Dynamic Programming.
## Algorithm
1.start the program
2. For i from 0 to n - m:
   a. For j from 0 to m - 1:
      - If T[i + j] != P[j], break the inner loop (mismatch found).
   b. If the inner loop completes without breaking (all characters matched), return i (starting index of match).

3. If no match is found after all iterations, return -1 or indicate no match.

4. Output: Starting index of the first match or message indicating pattern not found.

5. End.
   

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming
Developed by: Soundariyan MN
Register Number: 212222230146
*/
def longest_common_subsequence(X, Y):
    m = len(X)
    n = len(Y)

    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

    lcs_length = dp[m][n]
    lcs = [''] * lcs_length
    i, j = m, n

    while i > 0 and j > 0:
        if X[i - 1] == Y[j - 1]:
            lcs[lcs_length - 1] = X[i - 1]
            i -= 1
            j -= 1
            lcs_length -= 1
        elif dp[i - 1][j] > dp[i][j - 1]:
            i -= 1
        else:
            j -= 1

    return ''.join(lcs)
X = input()
Y = input()

result = longest_common_subsequence(X, Y)
print(result)
```

## Output:
![Screenshot 2025-04-29 142914](https://github.com/user-attachments/assets/996cea98-54f2-44e4-96fa-d1e1afc40b01)



## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
