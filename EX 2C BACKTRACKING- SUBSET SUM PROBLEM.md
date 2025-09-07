# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
Start the program.

Read the size of the set n.

Input n integers from the user and store them in the list a[].

Read the target sum value.

Define a recursive function SubsetSum(a, i, sum, target, n) which:

Returns True if i == n and sum == target.

Recursively checks two possibilities for each element a[i]:

Include the element in the subset (sum + a[i]).

Exclude the element from the subset.

If either recursive call returns True, then a valid subset exists.

Otherwise, return False.

Call the function starting from index 0 with initial sum 0.

If the function returns True, print the elements of the array and display "True, subset found".

Otherwise, print the elements of the array and display "False, subset not found".

Stop the program.  

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: Dinesh M
Register Number: 212222040039

def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if  SubsetSum(a,i+1,sum+a[i],target,n):
        return True
    if  SubsetSum(a,i+1,sum,target,n):
        return True
    return False
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


*/
```

## Output:
<img width="1299" height="768" alt="Screenshot 2025-09-07 172355" src="https://github.com/user-attachments/assets/987e010f-9811-43cd-9bbe-7fb1c23a41c3" />



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
