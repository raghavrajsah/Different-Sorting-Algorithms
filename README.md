# Sorting Algorithms 

This repository provides implementations and detailed explanations of various sorting algorithms. It covers the fundamental concepts, pseudocode, time complexity, space complexity, advantages, disadvantages, and usage scenarios for each algorithm. Ideal for students and professionals looking to deepen their understanding of sorting techniques and improve their coding skills.

## Contents

- **Bubble Sort**: Basic sorting algorithm with adjacent swaps.
- **Selection Sort**: Finds the minimum element and places it in the correct position.
- **Insertion Sort**: Builds the sorted array one element at a time.
- **And more...**

Each algorithm includes:
- **Conceptual Overview**
- **Example Walkthrough**
- **Java Implementation**
- **Complexity Analysis**
- **Practical Use Cases**


## 1. Bubble Sort

### Concept
- In Bubble Sort, we repeatedly compare adjacent items and swap them if the second item is bigger than the first.
- With each pass through the array (outer loop), the largest number in the unsorted portion of the array "bubbles" to the end.

### Example
Given an array: [5, 3, 8, 4, 2]

- **First Pass**:
  - Compare 5 and 3. Swap to get [3, 5, 8, 4, 2]
  - Compare 5 and 8. No swap.
  - Compare 8 and 4. Swap to get [3, 5, 4, 8, 2]
  - Compare 8 and 2. Swap to get [3, 5, 4, 2, 8]
- **Second Pass**:
  - Compare 3 and 5. No swap.
  - Compare 5 and 4. Swap to get [3, 4, 5, 2, 8]
  - Compare 5 and 2. Swap to get [3, 4, 2, 5, 8]
  - The largest element (8) is now in its correct position.

Repeat the process until the array is sorted: [2, 3, 4, 5, 8]

### Time Complexity
- **Best Case**: \(O(n)\) (when the array is already sorted)
- **Average Case**: \(O(n^2)\)
- **Worst Case**: \(O(n^2)\)

### Space Complexity
- \(O(1)\) (in-place sorting)

### Advantages of Bubble Sort
- **Simplicity**: Easy to understand and implement.
- **Small Data Sets**: Efficient for very small datasets or lists that are nearly sorted.
- **Educational**: Useful for educational purposes to introduce sorting algorithms and basic algorithmic concepts.

### Disadvantages
- **Inefficiency**: Not suitable for large datasets due to its quadratic time complexity.

### Usage Scenarios
- **Small Arrays**: When dealing with very small arrays where the overhead of more complex algorithms is not justified.
- **Nearly Sorted Arrays**: When the array is already or almost sorted, Bubble Sort can be efficient with its best-case time complexity of \(O(n)\).


### Sample Java Implementation

Here's a sample Java implementation of Bubble Sort:

```java
public class BubbleSort{

    public static void bubblesort(int[] arr){

        for(int i=0;i<arr.length;i++){
            for(int j=0; j<arr.length-1;j++){
                if(arr[j]>arr[j+1]){
                    swap(arr, j,j+1);
                }
            }
        }
    }
    public static void swap(int[] arr,int a, int b){
        int c = arr[a];
        arr[a]=arr[b];
        arr[b]=c;
    }    
}
```


## 2. Selection Sort

### Concept
- In Selection Sort, we repeatedly find the minimum element from the unsorted portion of the array and move it to the sorted portion.
- With each iteration, the smallest element in the unsorted part is selected and swapped with the first unsorted element.

### Example
Given an array: [5, 3, 8, 4, 2]

- **Initial State**: [5, 3, 8, 4, 2]
- **First Pass**:
  - Find the minimum element (2).
  - Swap 2 with the first element: [2, 3, 8, 4, 5]
- **Second Pass**:
  - Find the next minimum element (3).
  - Swap 3 with the second element: [2, 3, 8, 4, 5]
- **Third Pass**:
  - Find the next minimum element (4).
  - Swap 4 with the third element: [2, 3, 4, 8, 5]
- **Fourth Pass**:
  - Find the next minimum element (5).
  - Swap 5 with the fourth element: [2, 3, 4, 5, 8]

The array is now sorted: [2, 3, 4, 5, 8]

### Time Complexity
- **Best Case**: \(O(n^2)\)
- **Average Case**: \(O(n^2)\)
- **Worst Case**: \(O(n^2)\)

### Space Complexity
- \(O(1)\) (in-place sorting)

### Advantages of Selection Sort
- **Simplicity**: Easy to understand and implement.
- **Small Data Sets**: Works well for small datasets.
- **Memory Efficiency**: Requires only \(O(1)\) extra space.

### Disadvantages
- **Inefficiency**: Not suitable for large datasets due to its quadratic time complexity.
- **Stability**: Not a stable sort, as it may change the relative order of equal elements.

### Usage Scenarios
- **Small Arrays**: When dealing with small arrays where the overhead of more complex algorithms is not justified.
- **Memory Constraints**: When additional memory is a concern, as Selection Sort uses a constant amount of space.


### Sample Java Implementation

```java
public class SelectionSort{

    public static void selectionsort(int[] arr){
        
       for(int i =0; i<arr.length-1;i++){
        int min =i;
        for(int j=i+1;j<arr.length;j++){
            if(arr[j]<arr[min]){
                min=j;
            }
        }
        if(min!=i){
            swap(arr,i,min);
        }
       }
    }
```

