# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 08.04.2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start the program.
2. Input the size of the set, size.
3. Initialize an empty list a.
4. Read size integer values and append them to list a.
5. Input the target sum target.
6. Set n = len(a) (number of elements).
7. Call the recursive function SubsetSum(a, 0, 0, target, n):
8. If it returns True:
   Print all elements in a.
   Print "True, subset found".
9. Else:
   Print all elements in a.
   Print "False, subset not found".
10. End the program.
    

## Program:
```
Program to implement Subset sum problem.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def SubsetSum(a,i,sum,target,n):    
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a, i+1, sum, target, n) or SubsetSum(a, i+1, sum+a[i], target, n)

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")
```


## Output:

![image](https://github.com/user-attachments/assets/14b75a1f-a565-44cf-a030-354cdac58a8a)


## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
