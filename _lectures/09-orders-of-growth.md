---
title: Orders of growth
description: Relative growth of the most common functions
lecture_number: 9
topic_number: 1
layout: lecture
mathjax: true
---
When dealing with limits as ($x\rightarrow 0$), it is the lowest order term (i.e. the term with the smallest power) which matters the most, since higher powers of ($x$) are very small when ($x$) is close to 0. On the other hand, as ($x \rightarrow \infty$), what is known as the asymptotic growth of a function. In this case, it is the highest order term which matters the most. This module deals with limits of both types and provides a more formal notion of how quickly a function grows or shrinks.
Hierarchy of functions going to infinity

First, consider the monomial ($x^n$), where ($n$) is a fixed, positive integer. Looking at the graphs of these monomials, it becomes clear that as ($x \rightarrow \infty$), ($x^{n+1} > x^n$):

What happens when the functions involved are not polynomials? For example, how does the growth of the exponential compare to a polynomial? Or factorial and exponential?

In general, one can compare the asymptotic growth of the functions ($f$) and ($g$) by considering the limit ($\lim_{x \rightarrow \infty} \frac{f(x)}{g(x)}$). If this limit is ($\infty$), then ($f$) dominates. If the limit is 0, then ($g$) dominates. And if the limit is a constant, then ($f$) and ($g$) are considered equal (asymptotically).

Example

Compare exponential growth and polynomial growth. (:toggle hide show="Answer" box1a:)

Fix an integer ($n$), and compute the limit (using l'Hopital repeatedly):

(:latex:) \begin{align*} \lim_{x \rightarrow \infty} \frac{x^n}{e^x} &= \lim_{x \rightarrow \infty} \frac{nx^{n-1}}{e^x}
&= \lim_{x \rightarrow \infty} \frac{n(n-1)x^{n-2}}{e^x}
&= \vdots
&= \lim_{x \rightarrow \infty} \frac{n!}{e^x}
&= 0 \end{align*} (:latexend:)

(note that ($n$) is fixed, so ($n!$) is a constant). Thus, the exponential dominates the monomial ($x^n$) (and thus any polynomial as well).

Example

Compare the asymptotic behavior of ($\ln^n x$) (for some fixed integer ($n$)) and ($x$). (:toggle hide show="Answer" box1b:)

Again, using L'Hopital's rule repeatedly gives

(:latex:) \begin{align*} \lim_{x \rightarrow \infty} \frac{\ln^n x}{x} &= \lim_{x \rightarrow \infty} \frac{n \ln^{n-1} x \frac{1}{x}}{1}
&= \lim_{x \rightarrow \infty} \frac{n \ln^{n-1} x}{x}
&= \vdots
&= \lim_{x \rightarrow \infty} \frac{n!}{x}
&= 0, \end{align*} (:latexend:)

since ($n!$) is a constant here. This shows any polynomial beats any constant power of logarithm.

Example

Compare the asymptotic growth of the factorial and the exponential. (:toggle hide show="Answer" box1c:)

First, when ($x$) is not an integer, the factorial is defined by

(:latex:) \[ x! = \int_{t=0}^\infty t^x e^{-t} \, dt. \] (:latexend:)

This definition shares properties with the traditional definition of factorial: ($x! = x \cdot (x-1)!$), and ($0! = 1$), and they coincide when ($x$) is an integer. It is not critical to know this integral definition, but know that ($n! = n(n-1)(n-2)\dotsb 3 \cdot 2 \cdot 1$) for an integer ($n$).

When ($x$) is an integer, note that ($e^x$) is ($e$) multiplied with itself ($x$) times. On the other hand, ($x!$) has ($x$) factors, most of which are bigger than ($e$) (at least when ($x$) is bigger than, say, 5). So as ($x$) increases to ($x+1$), ($e^x$) only gains another factor of ($e$), but ($x!$) gains a factor of ($x+1$). This explains why ($x!$) grows faster than ($e^x$) (and similarly for any exponential function).

Thus we have the following hierarchy of growth, from greatest to smallest:

    Factorial: ($x! = x(x-1)(x-2)\dotsm 3 \cdot 2 \cdot 1$).
    Exponential: ($c^x$) for any ($c>1$) (usually ($c=e$)).
    Polynomial: ($x^k$) for any ($k>0$).
    Logarithmic: ($\ln(x)$) and other related functions. 

When a pair of functions are of a similar type, such as ($e^x$) and ($3^{\sqrt x}$), one must compare these using the limit of the ratio of the functions, as above.
Hierarchy of functions going to 0

As above, first consider monomials ($x^n$). As ($x \rightarrow 0$), the inequality for monomials is the reverse of what it was for ($x \rightarrow \infty$). That is, as ($x \rightarrow 0$), we find that ($x^n > x^{n+1}$). Intuitively, small numbers become even smaller when you raise them to higher powers.

It is important to keep track of whether a limit is going to 0 or ($\infty$), since in the first case, the lowest order terms dominate, and in the second case the highest order terms dominate.

Example Compute ($\displaystyle \lim_{x \rightarrow 0} \frac{2x^3-x^2+x}{x^3+2x}$) and ($\displaystyle \lim_{x \rightarrow \infty} \frac{2x^3-x^2+x+1}{x^3+2x+2}$). (:toggle hide show="Answer" box1:)

As ($x \rightarrow 0$), the higher powers of ($x$) go to 0 quickly, leaving the lowest order terms ($\frac{x}{2x} = \frac{1}{2}$) in the limit.

As ($x \rightarrow \infty$), it is the highest order terms (the ($x^3$) terms) which dominate, so ignoring the lower order terms leaves ($\frac{2x^3}{x^3} = 2$) in the limit.
Big-O notation

When dealing with limits as ($x \rightarrow 0$) or ($x \rightarrow \infty$), it is best to have a formal notation for the approximations which result from dropping higher or lower order terms. Big-O notation, pronounced "big oh", provides this formality.

Big-O notation, ($x \rightarrow 0$)

The function ($f(x)$) is in ($O(x^n)$), as ($x \rightarrow 0$) if

(:latex:) \[ |f(x)| < C|x|^n \] (:latexend:)

for some constant ($C$) and all ($x$) sufficiently close to 0. Put another way, a function ($f(x)$) is in ($O(x^n)$), for ($x$) close to 0, if ($f(x)$) approaches 0 at least as fast as a constant multiple of ($x^n$).

More generally, a function ($f(x)$) is in ($O(g(x))$), as ($x \rightarrow 0$) if

(:latex:) \[ |f(x)| < C|g(x)|, \] (:latexend:)

for some constant ($C$) and ($x$) sufficiently close to 0.

Big-O notation, as ($x \rightarrow 0$), can be thought of as a more specific way of saying higher order terms. Just as Taylor series could include a different number of terms before indicating the rest is higher order terms (depending on the situation), the same is true for big-O.

Example

Express ($\arctan(x)$) using big-O notation as ($x \rightarrow 0$). (:toggle hide show="Answer" box1d:)

By taking the Taylor series for ($\arctan(x)$), we find that (:latex:) \[ \arctan(x)= x - \frac{x^3}{3} + O(x^5) \] (:latexend:) as ($x \rightarrow 0$).

We could also say

(:latex:) \[ \arctan(x)= x - O(x^3) \] (:latexend:) as ($x \rightarrow 0$).

The definition for big-O as ($x \rightarrow \infty$) is almost identical, except the bound needs to apply for all ($x$) sufficiently large.

Big-O notation, ($x \rightarrow \infty$)

The function ($f(x)$) is in ($O(x^n)$), as ($x \rightarrow \infty$) if

(:latex:) \[ |f(x)| < C|x|^n \] (:latexend:)

for some constant ($C$) and all ($x$) sufficiently large. In other words, a function ($f(x)$) is in ($O(x^n)$), as ($x \rightarrow \infty$), if ($f(x)$) approaches infinity no faster than a constant multiple of ($x^n$).

More generally, ($f(x)$) is in ($O(g(x))$), as ($x \rightarrow \infty$) if

(:latex:) \[ |f(x)| < C |g(x)| \] (:latexend:)

for some constant ($C$) and all ($x$) sufficiently large.

Example

The monomial ($x^n$) is in ($O(e^x)$) as ($x \rightarrow \infty$) for any (fixed) ($n$). This is a restatement of the above fact that the exponential dominates polynomials as ($x \rightarrow \infty$).

Example

Show that ($x \sqrt{x^2 + 3x + 5} = x^2 + \frac{3}{2}x + O(1)$) as ($x \rightarrow \infty$). Hint: use the binomial series. (:toggle hide show="Answer" box1e:)

Recall that the binomial series

(:latex:) \[ (1+x)^\alpha = 1 + \alpha x + \frac{\alpha (\alpha - 1)}{2!} x^2 + \ldots \] (:latexend:)

requires that ($|x|<1$). So we must do a little algebra to get the square root to be of this form. Factoring out a ($x^2$) will do the trick:

(:latex:) \begin{align*} x \sqrt{x^2+3x+5} &= x \sqrt{x^2 \left( 1 + \frac{3}{x} + \frac{5}{x^2} \right)}
&= x^2 \left(1 + \frac{3}{x} + \frac{5}{x^2} \right)^{1/2}
&= x^2 \left( 1 + \frac{1}{2}\left(\frac{3}{x} + \frac{5}{x^2}\right) + O\left(\frac{1}{x^2}\right) \right)
&= x^2 + \frac{3}{2}x + O(1), \end{align*} (:latexend:)

since all the terms involving ($\frac{1}{x^2}$) become constants when multiplied by ($x^2$).

Example

Justify the following statements as ($x \rightarrow 0$):

    ($5x+3x^2$) is in ($O(x)$) but is not in ($O(x^2)$).
    ($\sin x$) is in ($O(x)$) but is not in ($O(x^2)$).
    ($\ln(1+x)-x$) is in ($O(x^2)$) but is not in ($O(x^3)$).
    ($1 - \cos(x^2)$) is in ($O(x^4)$) but is not in ($O(x^5)$).
    ($\sqrt{x}$) is not in ($O(x^n)$) for any ($n \geq 1$).
    ($e^{-1/x^2}$) is in ($O(x^n)$) for all ($n$). 

(:toggle hide show="Answer" box1f:)

The first four of these can be justified by looking at the Taylor series and then finding the monomial of the lowest power (remember that as ($x \rightarrow 0$), the dominant term is that of the lowest power).

To see that ($\sqrt{x}$) is not in ($O(x^n)$) for any ($n \geq 1$), we must show that given any constant ($C$) and ($\epsilon>0$), there exists some ($x < \epsilon$) such that

(:latex:) \[ \sqrt{x} > C x^n \] (:latexend:)

(this is the negation of the definition of big oh). Solving the above inequality for ($x$), one finds that if

(:latex:) \[ x < \left(\frac{1}{C}\right)^{2/(2n-1)}, \] (:latexend:)

then ($\sqrt{x} > C x^n$), and so ($\sqrt{x}$) is not in ($O(x^n)$) for any ($n$).

Finally, to see that ($e^{-1/x^2}$) is in ($O(x^n)$), it suffices to show that

(:latex:) \[ e^{-1/x^2} < |x|^n \] (:latexend:)

for all ($x$) sufficiently small. Taking natural log of both sides (this preserves the inequality since log is an increasing function) gives

(:latex:) \[ -\frac{1}{x^2} < n \ln|x|. \] (:latexend:)

Rearranging this (recall that multiplying an inequality by a negative number reverses the inequality) gives

(:latex:) \[ \frac{1}{n} > -x^2 \ln |x|. \] (:latexend:)

But recall from a previous module that ($ x \ln x \rightarrow 0$) as ($x \rightarrow 0^+$). This ensures that no matter the (fixed) value of ($n$), for sufficiently small ($x$) we will have

(:latex:) \[ \frac{1}{n} > -x^2 \ln |x|, \] (:latexend:)

and hence

(:latex:) \[ e^{-1/x^2} < |x|^n, \] (:latexend:)

as desired.

Example

Justify the following statements as ($x \rightarrow \infty$):

    ($\arctan x$) is in ($O(1)$) as well as ($O(x^n)$) for any ($n \geq 0$).
    ($x \sqrt{1+x^2}$) is in ($O(x^2)$) but is not in ($O(x^{3/2})$).
    ($\ln \sinh x$) is in ($O(x)$) but is not in ($O(\ln x)$).
    ($\cosh x$) is in ($O(e^x)$) but is not in ($O(x^n)$) for any ($n \geq 0$).
    ($\ln (x^5)$) is in ($O(\ln x)$) as well as ($O(x^n)$) for all ($n$).
    ($x^x$) is in ($O(e^{x^n})$) for all ($n>1$). 

(:toggle hide show="Answer" box2:)

    Note that as ($x \rightarrow \infty$), ($\arctan x \rightarrow \frac{\pi}{2}$). Thus ($\arctan x$) is bounded, and so it is in ($O(1)$).
    Using the binomial series, as in a previous example, shows that 

(:latex:) \begin{align*} x \sqrt{1 + x^2} &= x \left(x^2\left(1+ \frac{1}{x^2}\right)\right)^{1/2}
&= x^2 \left(1+ \frac{1}{x^2}\right)^{1/2}
&= x^2 \left( 1 + \frac{1}{2}\frac{1}{x^2} + O\left(\frac{1}{x^4}\right) \right)
&= x^2 + O(1). \end{align*} (:latexend:)

Thus, ($x \sqrt{1+x^2}$) is in ($O(x^2)$), but no power smaller than ($x^2$).

    For large ($x$), ($e^{-x}$) is very small, and so ($\sinh x \approx \frac{e^x}{2}$). Therefore, 

(:latex:) \[ \ln \sinh x \approx \ln \frac{e^x}{2} = x - \ln 2. \] (:latexend:)

is in ($O(x)$) but not in ($O(\ln x)$), since logarithms are smaller than polynomials.

    Similarly, ($\cosh x \approx \frac{e^x}{2}$) for large ($x$). Hence ($\cosh$) is in ($O(e^x)$) but cannot be bounded by any polynomial.
    A handy property of logarithms tells us that 

(:latex:) \[ \ln (x^5) = 5 \ln x, \] (:latexend:)

which is in ($O(\ln x)$) since it is itself a multiple of ($\ln x$).

    Fix ($n>1$). It suffices to show that for large enough ($x$), we have 

(:latex:) \[ x^x < e^{x^n}. \] (:latexend:)

Taking the logarithm of both sides gives

(:latex:) \[ x \ln x < x^n \quad \Leftrightarrow \quad \ln x < x^{n-1}. \] (:latexend:)

We saw earlier that any positive power of ($x$) beats the logarithm for large values of ($x$). So (since ($n >1$)) this inequality holds for large ($x$), and so ($x^x$) is in ($O(e^{x^n})$).
Application: Error Analysis

When approximating a function by the first few terms of its Taylor series, there is a trade-off between convenience (the ease of the computation) and accuracy. Big-O notation can help keep track of this error.

Example Consider the approximation, for ($x$) close to 0,

(:latex:) \begin{align*} \sin(x^2)e^x &= \left(x^2 + O(x^6)\right)(1 + O(x))
& = x^2 + x^2 \cdot O(x) + O(x^6) + O(x^6)\cdot O(x)
& = x^2 + O(x^3). \end{align*} (:latexend:)

So the error of approximating ($\sin(x^2)e^x \approx x^2$) can be bounded by ($Cx^3$), for some ($C$) when ($x$) is small. Determining a good ($C$), in general, is tricky, and there is more on error bounds in Taylor Remainder Theorem.
Application: Computational Complexity

In computer science, an algorithm is a sequence of steps used to solve a problem. For example, there are algorithms to sort a list of numbers and algorithms to find the prime factorization of a number. Computational complexity is a measure of how efficient an algorithm is. Basically, a computer scientist wants to know roughly how the number of computations carried out by the computer will grow as the input (e.g. the length of the list to be sorted, or the size of the number to be factored) gets larger.
Example: Multiplication

Consider how much work is required to multiply two ($n$)-digit numbers using the usual grade-school method. There are two phases to working out the product: multiplication and addition.

First, multiply the first number by each of the digits of the second number. For each digit in the second number this requires ($n$) basic operations (multiplication of single digits) plus perhaps some "carries", so say a total of ($2n$) operations for each digit in the second number. This means that the multiplication phase requires ($n \cdot (2n)$) basic operations.

The addition phase requires repeatedly adding ($n$) digit numbers together a total of ($n-1$) times. If each addition requires at most ($2n$) operations (including the carries), and there are ($n-1$) additions that must be made, it comes to a total of ($(2n)(n-1)$) operations in the addition phase.

Adding these totals up gives about ($4n^2$) total operations. Thus, the total number of basic operations that must be performed in multiplying two ($n$) digit numbers is in ($O(n^2)$) (since the constant coefficient does not matter).

The reason the constant coefficient does not really matter when thinking about computational complexity, is that a faster computer can only improve the speed of a computation by a constant factor. The only way to significantly improve a computation is to somehow drastically cut the number of operations required to perform the operation. The next example shows an example of how important algorithmic improvements can be on computational complexity.
Example: Sorting

In sorting algorithms, the most basic operation is the comparison. For a sorting algorithm, one wants to know how many comparisons of two numbers will be made, on average.

One common sorting algorithm, which is used by most people who are sorting items by hand, is called Insertion Sort. It turns out that the number of comparisons for Insertion Sort, on average, is ($O(n^2)$) as ($n \rightarrow \infty$), where ($n$) is the length of the list of numbers to be sorted.

A more sophisticated sorting algorithm, called Mergesort, uses ($O(n\ln(n))$) comparisons on average. This may not seem like a significant improvement over Insertion Sort, but consider the number of comparisons used to sort a list of 1000000 integers: Insertion Sort would use on the order of ($1000000^2 = 10^{12}$) comparisons on average, where as Mergesort uses on the order of ($13 \times 10^6$) comparisons. To put that in perspective, if Mergesort took a half second to complete the computation, Insertion Sort would take over ten hours!
Big O in Other Areas of Mathematics
Stirling's formula

Stirling's formula gives an asymptotic approximation for ($x!$):

(:latex:) \[ \ln (x!) = x \ln x - x + O(\ln x). \] (:latexend:)

In a slightly more precise form, it can be written

(:latex:) \[ x! = \sqrt{2\pi x} \left(\frac{x}{e}\right)^x \left(1+O\left(\frac{1}{x}\right)\right). \] (:latexend:)
Prime number theorem

In number theory, one very important function, ($\pi(x)$), is defined to be the number of primes less than or equal to ($x$). The Prime Number Theorem says that

(:latex:) \begin{align*} \pi(x) &= \hbox{ number of primes $\leq x$ }
&= \frac{x}{\ln x} \left(1 + O\left(\frac{1}{\ln x}\right)\right). \end{align*} (:latexend:)
EXERCISES

    Compute the following limits. 

(:latex:) \[ \displaystyle \lim_{x \to +\infty} \frac{e^{2x}}{x^3 + 3x^2 +4}

 \]

(:latexend:)

(:latex:) \[\displaystyle \lim_{x \rightarrow +\infty} \frac{e^{3x}}{e^{x^2}}

 \]

(:latexend:)

(:latex:) \[\displaystyle \lim_{x \rightarrow +\infty} \frac {e^x (x-1)!}{x!}

 \]

(:latexend:)

(:latex:) \[\displaystyle \lim_{x \rightarrow +\infty} \frac (x^2-3)(x^2+3){2x^4-2x^2+1}

 \]

(:latexend:)

(:latex:) \[\displaystyle \lim_{x \to +\infty} \frac{2^x + 1}{(x+1)!}

 \]

(:latexend:)

(:latex:) \[\displaystyle \lim_{x \to +\infty} \frac{(3 \ln x)^n}{(2x)^n}

 \]

(:latexend:)

    Simplify the following asymptotic expression as ($x\to 0$) 

(:latex:) \[ f(x) = \left( x - x^2 + O(x^3)\right)\cdot\left(1+2x + O(x^3)\right) \] (:latexend:)

    Simplify the following asymptotic expression as ($x\to \infty$) 

(:latex:) \[ f(x) =\left( x^3 + 2x^2 + O(x)\right)\cdot\left(1+\frac{1}{x}+O\left(\frac{1}{x^2}\right)\right) \] (:latexend:)

    Here are some rules for positive functions with ($x\to\infty$): 

(:latex:) \[ O(f(x)) + O(g(x)) = O(f(x) + g(x)) \] \[ O(f(x))\cdot O(g(x)) = O(f(x)\cdot g(x))\] (:latexend:)

Using these, show that (:latex:) \[ O\left(\frac{5}{x}\right) + O\left(\frac{\ln(x^2)}{4x}\right) \] (:latexend:) simplifies to (:latex:) \[ \displaystyle O\left(\frac{\ln x}{x}\right) \] (:latexend:)

    Which of the following are in ($O(x^2)$) as ($x \to 0 $)? 

(:latex:) \[x \ln(1+x) \] \[ 5x^2+6x+1 \] \[1-e^{-x} \] \[ x \sqrt{x^2+4x^3+5x^6} \] \[x \sinh^2(3x) \] \[\frac{x^2}{\ln(1+x)} \] (:latexend:) 