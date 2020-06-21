---
title: Power series
description: Interval and radius of convergence
lecture_number: 54
topic_number: 5
layout: lecture
mathjax: true
---
Sequences can be thought of as the discretization of a function. This module goes in the opposite direction: turning a sequence into a function called a power series.
Power series

Given a sequence ($a_n$), the power series associated with ($a_n$) is the infinite sum ($\displaystyle f(x) = \sum_{n=0}^\infty a_n x^n$).
Example

The power series associated with the sequence ($a_n = 1$) is the function ($f(x) = 1+x+x^2+x^3+\ldots$).
Example

All of the Taylor series encountered earlier in the course are power series. For instance, the Taylor series for the exponential is the power series associated with the sequence ($a_n = \frac{1}{n!}$).
Example

The Lucas numbers ($L_n$) are like the Fibonacci numbers but with different initial conditions. ($L_0 = 2$) and ($L_1 = 1$), and ($L_n = L_{n-1} + L_{n-2}$). So the sequence begins ($L = (2,1,3,4,7,11,18,\ldots)$).

Find the closed-form function ($L(x)$) given by the power series

(:latex:) \begin{align*} L(x) &= L_0 + L_1x + L_2x^2 + L_3x^3 + \dotsb
&= \sum_{n=0}^\infty L_n x^n. \end{align*} (:latexend:)

This is known in the field of combinatorics as the generating function for the sequence ($L_n$).

(:toggle hide show="Answer" box2:)

Begin by writing out the series ($L(x)$), ($xL(x)$), and ($x^2L(x)$):

(:latex:) \begin{align*} L(x) &= L_0 + L_1x + L_2 x^2 + L_3x^3 + L_4x^4 + \dotsb
xL(x) &= \quad \quad L_0 x + L_1x^2 + L_2x^3 + L_3x^4 + \dotsb
x^2L(x) &= \quad \quad \quad \quad \quad L_0x^2 + L_1x^3 + L_2x^4 + \dotsb \end{align*} (:latexend:)

Now note what happens when we take ($L(x) - xL(x)-x^2L(x)$) and collect like terms. Because of the recurrence, all of the coefficients of the form ($L_n - L_{n-1} - L_{n-2} = 0$), which leaves only two terms in the power series:

(:latex:) \begin{align*} L(x) - xL(x)-x^2L(x) &= L_0 + (L_1-L_0)x + (L_2-L_1-L_0)x^2 + (L_3-L_2-L_1)x^3 + \dotsb
&= L_0 + (L_1-L_0)x + 0 x^2 + 0x^3 + 0x^4 + \dotsb
&= 2 + (1-2)x
&= 2-x. \end{align*} (:latexend:)

Now, solving for ($L(x)$) by factoring and dividing gives

(:latex:) \[ L(x) = \frac{2-x}{1-x-x^2}. \] (:latexend:)

These power series have lots of useful applications in enumeration and asymptotic analysis, among other things. But the rest of this module will deal with convergence. Given a sequence ($(a_n)$), for what values of ($x$) does its associated power series ($f(x) = a_0 + a_1 x + a_2 x^2 + \dotsb$) converge?
Interval and radius of convergence

Recall that some Taylor series had restrictions on the values of ($x$) for which the series equaled the function (e.g. geometric series, ($\ln(1+x)$), ($\Arctan(x)$)). In other words, the series converges for some values of ($x$) and diverges for other values of ($x$).

In general, given a power series ($f(x) = \sum a_n x^n$), the goal is to find the values of ($x$) for which the series converges. The following theorem tells us that the set of such values is always an interval:

Given

(:latex:) \[ f(x) = \sum_{n=0}^\infty a_n x^n, \] (:latexend:)

there exists some ($0 \leq R \leq \infty$) such that

    the series converges absolutely if ($|x|<R$);
    the series diverges if ($|x|> R$);
    might converge or diverge when ($x = R$) or ($x=-R$). 

The interval of convergence is the interval ($\left(-R,R\right)$), possibly with the endpoints included (they need to be individually checked in general). The radius of convergence is half the length of the interval of convergence.

The method for finding the interval of convergence is to use the ratio test to find the interval where the series converges absolutely and then check the endpoints of the interval using the various methods from the previous modules.

Previously, when using the ratio test, one computed ($\rho$) and then checked if ($\rho<1$), ($\rho>1$), or ($\rho=1$). Now, the goal is to find the values of ($x$) for which the series ($\sum a_n x^n$) converges absolutely, i.e. for which ($\rho<1$). So ($\rho$) is computed, in terms of ($x$), and is set to be less than 1. This gives an interval of values for ($x$) which the series converges absolutely. Once this interval has been determined, the endpoints must be checked for convergence as well.
Radius of convergence

For a general power series ($f(x) = a_0 + a_1x + a_2 x^2 + \dotsb$), what is the radius of convergence ($R$) in terms of the sequence ($a_n$)? Note that

(:latex:) \begin{align*} \rho &= \lim_{n \rightarrow \infty} \frac{|a_{n+1}x^{n+1}|}{|a_nx^n|}
&= \lim_{n \rightarrow \infty} \frac{|a_{n+1}|}{|a_n|} |x|. \end{align*} (:latexend:)

And for absolute convergence ($\rho < 1$). So in terms of the ($a_n$), we get absolute convergence when

(:latex:) \[ \lim_{n \rightarrow \infty} \frac{|a_{n+1}|}{|a_n|} |x| < 1, \] (:latexend:)

or equivalently,

(:latex:) \[ |x| < \lim_{n \rightarrow \infty} \frac{|a_n|}{|a_{n+1}|}. \] (:latexend:)

Thus, we have shown that the radius of convergence of the series ($f(x) = a_0 + a_1x + a_2x^2+\dotsb$) is given by

(:latex:) \[ R = \lim_{n \rightarrow \infty} \frac{|a_n|}{|a_{n+1}|}. \] (:latexend:)
Example

Find the interval and radius of convergence for the power series

(:latex:) \begin{equation*} \sum_{n=1}^\infty \frac{n}{2^n}x^n \end{equation*} (:latexend:)

(:toggle hide show="Answer" box3:)

Using the ratio test for absolute convergence, one computes

(:latex:) \begin{align*} \rho &= \lim_{n \rightarrow \infty} \left| \frac{a_{n+1}}{a_n}\right|
&= \lim_{n \rightarrow \infty} \left| \frac{(n+1) x^{n+1}/2^{n+1}}{nx^n/2^n} \right|
&= \lim_{n \rightarrow \infty} \frac{n+1}{2^{n+1}} \cdot \frac{2^n}{n} |x|
&= \lim_{n \rightarrow \infty} \frac{1}{2} \frac{n+1}{n} |x|
&= \frac{|x|}{2}. \end{align*} (:latexend:)

Setting ($\rho<1$) means ($\frac{|x|}{2}<1$), hence ($|x|<2$). So for all ($-2 < x < 2$), the series converges absolutely.

Checking the endpoint ($x=-2$) gives the series

(:latex:) \begin{align*} \sum_{n=1}^\infty \frac{n}{2^n}(-2)^n &= \sum_{n=1}^\infty \frac{n}{2^n} (-1)^n 2^n
&= \sum_{n=1}^\infty (-1)^n n, \end{align*} (:latexend:)

which diverges by the nth term test for divergence. Similarly, the endpoint ($x=2$) gives the series

(:latex:) \begin{equation*} \sum_{n=1}^\infty \frac{n}{2^n}2^n = \sum_{n=1}^\infty n, \end{equation*} (:latexend:)

which diverges, also by the nth term test. Thus, both endpoints diverge and so the interval of convergence is ($\left(-2,2\right)$). The radius of convergence is 2.
Example

Find the interval of convergence for

(:latex:) \begin{equation*} \sum_{n=1}^\infty (-1)^n \frac{x^n}{n} \end{equation*} (:latexend:)

(:toggle hide show="Answer" box4:)

Using the ratio test gives

(:latex:) \begin{align*} \rho &= \lim_{n \rightarrow \infty} \left|\frac{x^{n+1}}{n+1} \frac{n}{x^n} \right|
&= \lim_{n \rightarrow \infty} \frac{|x|n}{n+1}
&= |x|. \end{align*} (:latexend:)

Setting this less than 1 gives ($|x|<1$) so the interval is ($\left(-1,1\right)$). Checking the endpoint ($x=1$) gives the alternating harmonic series which converges. The other endpoint ($x=-1$) gives the harmonic series which diverges. So the interval of convergence is ($(-1,1]$).
Shifted power series

Recall that the Taylor series for a function can be computed at a point ($c$) other than 0. In this case the series took the form

(:latex:) \[ f(x) = a_0 + a_1(x-c) + a_2(x-c)^2 + a_3(x-c)^3 + \dotsb \] (:latexend:)

Such a power series is said to be centered at ($c$), since the interval of convergence for the series will be centered at ($c$). To see why, carry out the calculation as above (replacing all the ($|x|$)'s with ($|x-c|$)'s) to find that the series converges absolutely when

(:latex:) \[ |x-c| < \lim_{n \rightarrow \infty} \frac{|a_n|}{|a_{n+1}|} = R. \] (:latexend:)

So the radius of convergence is the same (it only depends on the sequence ($a_n$)), and it is only the center of the interval that has changed. Thus, the interval of convergence is ($(c-R,c+R)$), and again one must individually check the endpoints.
Example

Find the interval of convergence for

(:latex:) \begin{equation*} \sum_{n=1}^\infty (-1)^n \frac{(x+3)^n}{n^2} \end{equation*} (:latexend:)

(:toggle hide show="Answer" box5:)

The interval of convergence will be centered at ($-3$). We can take a short cut and just compute the radius of convergence ($R = \lim \frac{|a_n|}{|a_{n+1}|}$), where ($a_n = \frac{(-1)^n}{n^2}$). This gives ($R = 1$).

Then the interval of convergence is ($(-3-1,-3+1) = (-4,-2)$), and it remains to check the endpoints. At ($x=-4$), we get ($\sum \frac{1}{n^2}$), which converges by p-series. At ($x=-2$), we get the alternating p-series ($\sum (-1)^n \frac{1}{n^2}$), which converges by alternating test. Thus, the interval of convergence is ($\left[-4,-2\right]$).
Example

Find the interval of convergence for

(:latex:) \[ \sum_{n=2}^\infty \frac{\left(2x+5\right)^n}{\ln n}. \] (:latexend:)

(:toggle hide show="Answer" box6:)

It takes a little rearranging before this takes the form of a shifted series as defined above (the problem is the coefficient of 2 on the ($x$)). The 2 can be factored out, and what results is

(:latex:) \begin{align*} \sum_{n=2}^\infty \frac{\left(2x+5\right)^n}{\ln n} &= \sum_{n=2}^\infty \frac{2^n(x+5/2)^n}{\ln n}
&= \sum_{n=2}^\infty \frac{2^n}{\ln n} (x+5/2)^n, \end{align*} (:latexend:)

which is now of the form given above. Note that this series is centered at ($-5/2$). The radius of convergence is

(:latex:) \begin{align*} R &= \lim_{n \rightarrow \infty} \frac{2^n}{\ln(n)}\cdot \frac{\ln(n+1)}{2^{n+1}}
&= \frac{1}{2} \end{align*} (:latexend:)

(since the ratio of logs goes to 1). Thus, the interval of convergence is ($(-3,-2)$). Checking the endpoints, one finds convergence at ($x=-3$) (by alternating series test) and divergence at ($x=-2$) (by comparison of ($\sum \frac{1}{\ln n}$) with the harmonic series, for example).

So the interval of convergence is (-3,-2)$). 