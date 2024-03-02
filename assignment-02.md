# CMPS 2200 Assignment 2

**Name:**________Tony _________________

In this assignment we'll work on applying the methods we've learned to analyze recurrences, and also see their behavior
in practice. As with previous
assignments, some of of your answers will go in `main.py` and `test_main.py`. You
should feel free to edit this file with your answers; for handwritten
work please scan your work and submit a PDF titled `assignment-02.pdf`
and push to your github repository.


1. Derive asymptotic upper bounds of work for each recurrence below.
  * $W(n)=2W(n/3)+1$
.  Root = 1
  Level 1 = 2
  Work at leave level = 2^log_3 n
. O( 2^log_3 n) = n^(log_3 2)
.  
.  
.  
  * $W(n)=5W(n/4)+n$
.  Root = n
  Level 1 = 5/4 n
  Leave level = 5^(log_4 n)/ 4^(log_4 n)  * n
    (5/4) ^ log_4 n = n ^ log_4(5/4) * n
    n^(log_4 5 - 1) * n = n ^log_4 5  
.  O(5^(log_4 n)/ 4^(log_4 n) ) = O(n^log_4 5)
.  
.  
.  
  * $W(n)=7W(n/7)+n$
.  Root = n
.  Level1 = n 
.  depth = logn
.  O(n logn)
.  
  * $W(n)=9W(n/3)+n^2$
.  Root n^2
.  Level1 = n^2
. Depth = log_3 n  
.  O(n^2 logn) 
.  
  * $W(n)=8W(n/2)+n^3$
.  root = n^3
.  level1 = n^3
.  Depth = log_2 n
.   O(n^3 logn)
.  
  * $W(n)=49W(n/25)+n^{3/2}\log n$
.  root = n^3/2 * logn
.  level 1 = (n^3/2)/125 * log(n/25)
.  O(n^3/2 * logn)
.  
.  
  * $W(n)=W(n-1)+2$
.  level 0: 2
.  level 1 : 2
.  overall 2*n in O(2n)
.  

  * $W(n)= W(n-1)+n^c$, with $c\geq 1$
.  level 0 : n^c
.  level 1 : (n-1)^c = O(n^c)
.  over all: n * n^c = O(n^(c+1))
.  
.  
  * $W(n)=W(\sqrt{n})+1$
  * level 1 = 1
  * level 2 = 1
  * Depth = $(\sqrt{n}) + $
  * let $2^m = n$ n = log_2 m
  * $(\sqrt{n}$ = 2^(m/2)$
  * W(2^m) = W(2^(m/2)) + 1
  * depth of W(2^m) = log_2 m = O(logm)
  * n = log_2 m
  * Depth of W(n) = O(loglogn)


2. Suppose that for a given task you are choosing between the following three algorithms:

  * Algorithm $\mathcal{A}$ solves problems by dividing them into
      five subproblems of half the size, recursively solving each
      subproblem, and then combining the solutions in linear time.

    W(n) = 5W(n/2) + O(n) = O(n^(log_2 5))
    S(n) = S(n/2) + O(n) = O(n)
    
  * Algorithm $\mathcal{B}$ solves problems of size $n$ by
      recursively solving two subproblems of size $n-1$ and then
      combining the solutions in constant time.

    W(n) = 2W(n-1) + O(1) = O(2^n) 
    S(n) = S(n-1) + O(1) = O(n)
    
  * Algorithm $\mathcal{C}$ solves problems of size $n$ by dividing
      them into nine subproblems of size $n/3$, recursively solving
      each subproblem, and then combining the solutions in $O(n^2)$
      time.
    W(n) = 9W(n/3) + O(n^2) = O(n^2 logn)
    S(n) = S(n/3) + O(n^2) = O(n^2)
    What are the asymptotic running times of each of these algorithms?
    Which algorithm would you choose?
     I will choose the first one, since it had the fasest span and the smallest amount of work.

3. Now that you have some practice solving recurrences, let's work on
  implementing some algorithms. In lecture we discussed a divide and
  conquer algorithm for integer multiplication. This algorithm takes
  as input two $n$-bit strings $x = \langle x_L, x_R\rangle$ and
  $y=\langle y_L, y_R\rangle$ and computes the product $xy$ by using
  the fact that $xy = 2^{n/2}x_Ly_L + 2^{n/2}(x_Ly_R+x_Ry_L) +
  x_Ry_R.$ Use the
  stub functions in `main.py` to implement Karatsaba-Ofman algorithm algorithm for integer
  multiplication: a divide and conquer algorithm that runs in
  subquadratic time. Then test the empirical running times across a
  variety of inputs in `test_main.py` to test whether your code scales in the manner
  described by the asymptotic runtime. Please refer to Recitation 3 for some basic implementations, and Eqs (7) and (8) in the slides https://github.com/allan-tulane/cmps2200-slides/blob/main/module-02-recurrences/recurrences-integer-multiplication.ipynb
 
 


