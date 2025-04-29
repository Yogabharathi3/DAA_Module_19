# EX 1C Quick Sort
## DATE:18.02.2025
## AIM:
To write a python program to implement quick sort using tha last element as pivot on the list of float values.

## Algorithm
1. Select a pivot element from the array (commonly the first or last element).
2. Partition the array into two subarrays: elements less than pivot and elements greater than or equal to pivot.
3. Place the pivot between the two subarrays at its correct position.
4. Recursively apply Quick Sort to the left subarray.
5. Recursively apply Quick Sort to the right subarray. 

## Program:
```
/*
Program to implement implement quick sort using the last element as pivot on the list of float values.
Developed by:Yogabharathi S
Register Number:212222230179  
*/
```
```
def partition(arr, low, high):
    i = low - 1
    pivot = arr[high]

    for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1

def quick_sort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        print("pivot: ", arr[pi])
        quick_sort(arr, low, pi - 1)
        quick_sort(arr, pi + 1, high)

# Take input from the user
def take_input():
    n = int(input())
    arr = []
    for i in range(n):
        arr.append(float(input()))
    return arr

# Example usage
if __name__ == "__main__":
    arr = take_input()
    quick_sort(arr, 0, len(arr) - 1)
    print(arr)
```
## Output:
![image](https://github.com/user-attachments/assets/8cbeb305-d7b3-4ce9-b9ea-1e340f1e3d77)
## Result:
The program successfully sorts the input array using the QuickSort algorithm, arranging the elements in ascending order.
