## Counting Sort

In Counting sort, the frequencies of distinct elements of the array to be sorted is counted and stored in an auxiliary array, by mapping its value as an index of the auxiliary array.


* Counting sort is a sorting technique based on keys between a specific range. 
* It works by counting the number of objects having distinct key values (kind of hashing). 
* Then doing some arithmetic to calculate the position of each object in the output sequence.


### Example.

For simplicity, consider the data in the range 0 to 9. 

Input data: 1, 4, 1, 2, 7, 5, 2

#### Step 1: Take a count array to store the count of each unique object.

```
  Index:     0  1  2  3  4  5  6  7  8  9
  Count:     0  2  2  0   1  1  0  1  0  0
```

#### Step 2:  Modify the count array such that each element at each index stores the sum of previous counts. 

```
  Index:     0  1  2  3  4  5  6  7  8  9
  Count:     0  2  4  4  5  6  6  7  7  7
```

The modified count array indicates the position of each object in the output sequence.


#### Step:3 Output each object from the input sequence followed by decreasing its count by 1.
  
  Process the input data: 1, 4, 1, 2, 7, 5, 2. Position of 1 is 2.
  Put data 1 at index 2 in output. Decrease count by 1 to place 
  next data 1 at an index 1 smaller than this index.
  
  
  
```java

// Counting sort which takes negative numbers as well  
import java.util.*; 
  
class CountingSort  
{ 
  
    static void countSort(int[] arr)  
    { 
        int max = Arrays.stream(arr).max().getAsInt(); 
        int min = Arrays.stream(arr).min().getAsInt(); 
        int range = max - min + 1; 
        int count[] = new int[range]; 
        int output[] = new int[arr.length]; 
        for (int i = 0; i < arr.length; i++)  
        { 
            count[arr[i] - min]++; 
        } 
  
        for (int i = 1; i < count.length; i++)  
        { 
            count[i] += count[i - 1]; 
        } 
  
        for (int i = arr.length - 1; i >= 0; i--)  
        { 
            output[count[arr[i] - min] - 1] = arr[i]; 
            count[arr[i] - min]--; 
        } 
  
        for (int i = 0; i < arr.length; i++) 
        { 
            arr[i] = output[i]; 
        } 
    } 
  
    static void printArray(int[] arr)  
    { 
        for (int i = 0; i < arr.length; i++)  
        { 
            System.out.print(arr[i] + " "); 
        } 
        System.out.println(""); 
    } 
  
    // Driver code 
    public static void main(String[] args) 
    { 
        int[] arr = {-5, -10, 0, -3, 8, 5, -1, 10}; 
        countSort(arr); 
        printArray(arr); 
    } 
}  


Output:

-10 -5 -3 -1 0 5 8 10 

```


### Points to be noted:
1. Counting sort is efficient if the range of input data is not significantly greater than the number of objects to be sorted. Consider the situation where the input sequence is between range 1 to 10K and the data is 10, 5, 10K, 5K.
2. It is not a comparison based sorting. It running time complexity is O(n) with space proportional to the range of data.
3. It is often used as a sub-routine to another sorting algorithm like radix sort.
4. Counting sort uses a partial hashing to count the occurrence of the data object in O(1).
5. Counting sort can be extended to work for negative inputs also.
