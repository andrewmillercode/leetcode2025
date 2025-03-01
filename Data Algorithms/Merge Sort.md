# Merge Sort
is a divide-and-conquer algorithm that sorts an array by first breaking it down into subarrays, and then combining each subarray together the correct way so that it is sorted.

- Time Complexity: O(N*log(N)) 
- Space Complexity: O(N) (Array has to be rebuilt) 

<img src="https://gamedevacademy.org/wp-content/uploads/2021/08/Merge_sort_algorithm_diagram-1.png.webp"/>

```
def mergeSort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    leftHalf = arr[:mid]
    rightHalf = arr[mid:]

    sortedLeft = mergeSort(leftHalf)
    sortedRight = mergeSort(rightHalf)

    return merge(sortedLeft, sortedRight)

def merge(left, right):
    result = []
    i = j = 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])

    return result

unsortedArr = [3, 7, 6, -10, 15, 23.5, 55, -13]
sortedArr = mergeSort(unsortedArr)
print("Sorted array:", sortedArr)
```





