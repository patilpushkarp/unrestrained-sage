# Selection Sort

## Introduction

Assuming we are sorting in ascending, selection sort algorithms attempts to divide the given array into two subarray. One subarray is sorted and the other one is unsorted. In every iteration, selection sort finds the minimum number from the unsorted subaaray and append it to the sorted subarray.  
**Example**:
Consider an array represented by variable "array":  
array = [45, 34, 23, 67, 58]
Result after each iteration is as follows:  
*First iteration*-  
array = [23, 45, 34, 67, 58]  
*Second iteration*-  
array = [23, 34, 45, 67, 58]  
*Third iteration*-  
array = [23, 34, 45, 58, 67]

## Algorithm

1. Set the index of the minimum number in the array to be 0.  
2. Find the index of minimum element.  
3. If possible, swap the minimum element with the 0th element.  
4. Increment the index of the minimum number by 1 i.e. point to the index to the next element.  
5. Continue the process till the complete array is sorted.  

## Pseudocode

### Inputs

|Variable|Description|
| --- | --- |
|array|Array of elements| 
|n|Number of elements in the given array|

### Code

for i = 0 to n-1  
&emsp;  
&emsp; # Assign index of min element to the first element  
&emsp; min_index = i  
&emsp;  
&emsp; # Search for the minimum from the subsequent elemenets in the array  
&emsp; for j = i to n-1  
&emsp;&emsp; if array[i] > array[j]  
&emsp;&emsp;&emsp; min_index = j  
&emsp;&emsp;  
&emsp; swap the value at min_index with ith element

### Output

|Variable|Description|
| --- | --- |
|array|Sorted array of elements| 

## Code


```python
array = [45, 34, 23, 67, 58]

for i in range(len(array)):
    
    # Assign min_index the index of first element
    min_index = i
    
    for j in range(i, len(array)):
        
        # Find the index of the minimum term in the unsorted array
        if array[i] > array[j]:
            min_index = j
    
    # Swap the minimum value with the ith term
    array[i], array[min_index] = array[min_index], array[i]
    
print("Sorted array is : "+str(array))
```

    Sorted array is : [23, 34, 45, 58, 67]
    


```python

```
