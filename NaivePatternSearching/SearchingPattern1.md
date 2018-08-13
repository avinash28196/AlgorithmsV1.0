# Searching for Patterns

Given a text txt[0..n-1] and a pattern pat[0..m-1], write a function search(char pat[], char txt[]) that prints all occurrences of pat[] in txt[]. 


```python
# Python program for Naive Pattern Searching
def search(pat, txt):
    M = len(pat)
    N = len(txt)
 
    # A loop to slide pat[] one by one
    for i in xrange(N-M + 1):
 
        # For current index i, check for pattern match
        for j in xrange(M):
            if txt[i + j] != pat[j]:
                break
 
        if j == M: # if pat[0...M-1] = txt[i, i + 1, ...i + M-1]
            print "Pattern found at index " + str(i)
 
# Driver program to test the above function
txt = "AABAACAADAABAAABAA"
pat = "AABA"

```


Output:
Pattern found at index 0 
Pattern found at index 9 
Pattern found at index 12

What is the best case?
The best case occurs when the first character of the pattern is not present in text at all.

txt[] = "AABCCAADDEE";
pat[] = "FAA";
The number of comparisons in best case is O(n).


What is the worst case ?
The worst case of Naive Pattern Searching occurs in following scenarios.
1) When all characters of the text and pattern are same.

txt[] = "AAAAAAAAAAAAAAAAAA";
pat[] = "AAAAA";


2) Worst case also occurs when only the last character is different.

txt[] = "AAAAAAAAAAAAAAAAAB";
pat[] = "AAAAB";
The number of comparisons in the worst case is O(m*(n-m+1)). Although strings which have repeated characters are not likely to appear in English text, they may well occur in other applications (for example, in binary texts). The KMP matching algorithm improves the worst case to O(n). We will be covering KMP in the next post. Also, we will be writing more posts to cover all pattern searching algorithms and data structures.

Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above.
