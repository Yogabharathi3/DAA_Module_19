# EX 1B Merge Sort
## DATE:15.02.2025
## AIM:
To write a python program to sort the first half of the list using merge sort.

## Algorithm
1. If the array has more than one element, split it into two halves.
2. Recursively apply merge sort on both halves.
3. Compare elements of both halves and merge them into a sorted array.
4. Copy any remaining elements from the left or right half.
5. Return the fully sorted array.
   
## Program:
```
/*
Program to implement Merge Sort
Developed by:YOGABHARATHI S 
Register Number:212222230179  
*/
```
```
def Merge_Sort(S):
    n = len(S)
    current_size = 1

    while current_size < n:
        left = 0
        while left < n - 1:
            mid = min(left + current_size - 1, n - 1)
            right = min(left + 2 * current_size - 1, n - 1)

            merge(S, left, mid, right)
            left += 2 * current_size

        current_size *= 2


def merge(S, left, mid, right):
    n1 = mid - left + 1
    n2 = right - mid

    L = [S[left + i] for i in range(n1)]
    R = [S[mid + 1 + i] for i in range(n2)]

    i = j = 0
    k = left

    while i < n1 and j < n2:
        if L[i] <= R[j]:
            S[k] = L[i]
            i += 1
        else:
            S[k] = R[j]
            j += 1
        k += 1

    while i < n1:
        S[k] = L[i]
        i += 1
        k += 1

    while j < n2:
        S[k] = R[j]
        j += 1
        k += 1


# Driver code
if __name__ == '__main__':
    # User input for array size
    n = int(input())

    # User input for array elements
    S = []
    for i in range(n):
        element = int(input())
        S.append(element)

    print("The Original array is: ", S)
    Merge_Sort(S)
    print("Array after sorting is: ", S)

```
## Output:
![image](https://github.com/user-attachments/assets/fb2b7027-544f-47cc-9f58-68936dda1a9e)

## Result:
The program successfully sorts the first half of the given array using merge sort. where only the first half is sorted, and the second half remains unchanged.
