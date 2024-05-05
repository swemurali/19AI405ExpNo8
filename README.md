# EX-08 Solve Cryptarithmetic Problem a CSP(Constraint Satisfaction Problem) using Python.
### Aim:
To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python. &emsp;&emsp;**DATE :27.03.2024**
### Procedure:
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br>
           G A M E S<br>

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
### Algorithm:
For this problem, we will define a node, which contains a letter and its corresponding values.<br>
isValid(nodeList, count, word1, word2, word3)<br>
Input − A list of nodes, the number of elements in the node list and three words.<br>
Output − True if the sum of the value for word1 and word2 is same as word3 value.<br>
```
Begin
   m := 1
   for each letter i from right to left of word1, do
      ch := word1[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            brea
      done
      val1 := val1 + (m * nodeList[j].value)
      m := m * 10
   done
   m := 1
   for each letter i from right to left of word2, do
      ch := word2[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            break
      done
      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done
   m := 1
   for each letter i from right to left of word3, do
      ch := word3[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            break
      done
      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done
   if val3 = (val1 + val2), then
      return true
   return false
End


Developed By: KARTHIKEYAN R 
Register No : 212222240046
```




### Program:
```Python
from itertools import permutations
def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm
        # Check for leading zeros
        if S == 0 or M == 0:
            continue
        # Check the equation constraints
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y
        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY
    return None
solution = solve_cryptarithmetic()
if solution:
    SEND, MORE, MONEY = solution
    print(f'SEND = {SEND}')
    print(f'MORE = {MORE}')
    print(f'MONEY = {MONEY}')
else:
    print("No solution found.")
```
### Output:
![Screenshot 2024-04-24 153657](https://github.com/ROHITJAIND/EX-08-SOLVE-CRYPTARITHMETIC-PROBLEM-A-CONSTRAINT-SATISFACTION-PROBLEM-USING-PYTHON/assets/118707073/762733ce-a092-4162-a187-74ff61a867f2)

### Result:
Thus a Cryptarithmetic Problem was solved using Python successfully.
