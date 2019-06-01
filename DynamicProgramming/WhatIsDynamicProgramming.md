Dynamic Programming is mainly an optimization over plain recursion. Wherever we see a recursive solution that has repeated calls for same inputs, we can optimize it using Dynamic Programming. The idea is to simply store the results of subproblems, so that we do not have to re-compute them when needed later. This simple optimization reduces time complexities from exponential to polynomial. For example, if we write simple recursive solution for Fibonacci Numbers, we get exponential time complexity and if we optimize it by storing solutions of subproblems, time complexity reduces to linear.


Dynamic Programming and Recursion:

Dynamic programming is basically, recursion plus using common sense. What it means is that recursion allows you to express the value of a function in terms of other values of that function. Where the common sense tells you that if you implement your function in a way that the recursive calls are done in advance, and stored for easy access, it will make your program faster. This is what we call Memoization - it is memorizing the results of some specific states, which can then be later accessed to solve other sub-problems.

The intuition behind dynamic programming is that we trade space for time, i.e. to say that instead of calculating all the states taking a lot of time but no space, we take up space to store the results of all the sub-problems to save time later.

Let's try to understand this by taking an example of Fibonacci numbers.

Fibonacci (n) = 1; if n = 0
Fibonacci (n) = 1; if n = 1
Fibonacci (n) = Fibonacci(n-1) + Fibonacci(n-2)

So, the first few numbers in this series will be: 1, 1, 2, 3, 5, 8, 13, 21... and so on!

A code for it using pure recursion:

  int fib (int n) {
        if (n < 2)
            return 1;
        return fib(n-1) + fib(n-2);
    }
Using Dynamic Programming approach with memoization:

 void fib () {
        fibresult[0] = 1;
        fibresult[1] = 1;
        for (int i = 2; i<n; i++)
           fibresult[i] = fibresult[i-1] + fibresult[i-2];
    }



When to use dynamic programming?

1. Optimal substructure: In layman terms, if I could break a problem into smaller versions of it, and then combine solutions to the smaller problems, 
		I'll have solved the problem at hand. 

2. Overlapping subproblems: 
	 While solving those smaller problem that leads to the same repetitive calculation steps, we term these as overlapping sub problems. 
	 Hence instead of solving for the same calculation steps over and over, we can store solutions to previous calculated steps it into a memory such as hash map or an array. 
	 
	 
	 
