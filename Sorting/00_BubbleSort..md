## Bubble sort

Bubble sort, sometimes referred to as sinking sort, is a simple sorting algorithm that repeatedly steps through the list, compares adjacent pairs and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. 


```java
public class MyBubbleSort { 
  public static void bubble_srt( int array[ ]) {
    //main 
    logic int n = array. length; 
    int k;
    for ( int m = n; m >= 0; m- -) {
      for ( int i = 0; i < n - 1; i+ +) { 
        k = i + 1; 
        if ( array[i] > array[k] ) { 
          swapNumbers(i, k, array) ; 
        } 
      } 
      printNumbers(array) ; 
    } 
  } 
  
  private static void swapNumbers( int i, int j, int [] array) { 
    int temp; temp = array[i] ; array[i] = array[j] ; array[j] = temp; 
  } 
  
  private static void printNumbers( int [] input) { 
  for ( int i = 0; i < input. length; i+ +) { 
    System. out.print( input[i] + ", " );
    } System. out.println( " \n " );
 } 

 public static void main( String[ ] args) { 
  int [] input = { 4, 2, 9, 6, 23, 12, 34, 0, 1 }; 
  bubble_srt(input) ; 
  } 
 } 
 ```
 
 ## Performance
 
 
 1. Bubble sort has a worst-case and average complexity of О(n2), where n is the number of items being sorted.
 2. Bubble sort should be avoided in the case of large collections. It will not be efficient in the case of a reverse-ordered collection.
 
 
 
 Advantages:
 
The ability to detect that the list is sorted. When the list is already sorted (best-case), 
    the complexity of bubble sort is only O(n). 
    By contrast, most other algorithms, even those with better average-case complexity, 
    perform their entire sorting process on the set and thus are more complex. 
    
Disadvantages:

 Bubble sort also interacts poorly with modern CPU hardware. It produces at least twice as many writes as insertion sort, twice as many cache misses, and asymptotically more branch mispredictions
