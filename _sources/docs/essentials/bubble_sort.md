# Bubble Sort

## Introduction

Bubble sort is the simplest algorithm in which adjacent values are swapped if they are in wrong order.  
**Example**:  
Consider an array represented by variable "array":  
array = [45, 34, 23, 67, 58]  
Result after each iteration is as follows:  
*First iteration*-  
array = [34, 45, 23, 67, 58]  
*Second iteration*-  
array = [34, 23, 45, 67, 58]  
*Third iteration*-  
array = [23, 34, 45, 67, 58]  
*Fourth iteration*-  
array = [23, 34, 45, 58, 67]  

## Algorithm

1. Swap the terms if the next term is greater than the current term  
2. This will push the largest term at the last position  
2. Continue step 1 till the complete array is sorted  

## Pseudocode

### Input

|Variable|Description|
| --- | --- |
|array|Array of elements| 
|n|Number of elements in the given array|

### Code

for i = 1 to n:  
&emsp;# Since the last i terms will always be sorted  
&emsp;for j = 1 to n-i:  
&emsp;&emsp;if array[j] > array[j+1]:  
&emsp;&emsp;&emsp; swap(array[j], array[j])  

### Output

|Variable|Description|
| --- | --- |
|array|Sorted array of elements| 

## Code


```python
array = [45, 34, 23, 67, 58]  

for i in range(len(array)):
    
    # Iterate till n-i terms since last i terms will always be sorted
    for j in range(len(array)-i-1):
        
        # Swap the successive term if it is smaller than the current term
        if array[j] > array[j+1]:
            array[j], array[j+1] = array[j+1], array[j]
            
print("Sorted array is : "+str(array))
```

    Sorted array is : [23, 34, 45, 58, 67]
    


```python

```
