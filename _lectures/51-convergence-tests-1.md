---
title: Convergence tests 1
description: Comparison-type tests
lecture_number: 51
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
Unlike the nth term test for divergence from the last module, this module gives several tests which, if successfully applied, give a definitive answer of whether a series converges or not. A common feature of the tests in this module is that they use a comparison.
Integral test for convergence and divergence

This is a test which can definitively tell whether a series converges or diverges. However, it can be harder to apply.

Integral test for convergence and divergence

If $$f(x)$$ is a positive, decreasing function, then for any integer $$m$$,

$$
\begin{equation*} \sum_{n=m}^\infty f(n) \hbox{ converges } \Longleftrightarrow \int_m^\infty f(x)dx \hbox{ converges}. \end{equation*}
$$

The double arrow $$\Longleftrightarrow$$ means if and only if. So the series and integral either both converge, or they both diverge.

To see why, visualize the series as a sum of rectangles with base 1 and height $$f(n)$$. If these rectangles are drawn to the right of the curve $$f(x)$$, then the result is the following figure. Each rectangle is labeled with its area. The combined area of the rectangles completely contains the area under $$f(x)$$, which establishes the inequality shown:

On the other hand, if the rectangles are drawn to the left of the curve $$f(x)$$, then all the rectangles lie below the curve. Their combined area is less than the area under the curve $$f(x)$$, which establishes the inequality shown:

Combining these two inequalities gives

$$
\begin{equation*} \int_1^\infty f(x)dx \leq \sum_{n=1}^\infty f(n) \leq \int_0^\infty f(x)dx. \end{equation*}
$$

If the integral diverges, then the series diverges (by the first inequality). And if the integral converges, then the series converges (by the second inequality). This establishes the integral test.

**Example**

Use the integral test to determine if

$$
\sum_{n=2}^\infty \frac{1}{n \ln(n)}
$$

converges or diverges.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Computing, one finds (using the u-substitution $$u = \ln(x)$$) that

$$
\begin{align*}
\int_2^\infty \frac{1}{x \ln(x)} dx &= \int_{\ln(2)}^\infty \frac{1}{u} du
&= \ln(u) \bigg\vert^\infty_{\ln(2)},
\end{align*}
$$

which diverges since $$\ln(u) \rightarrow \infty$$ as $$u \rightarrow \infty$$. Since the integral diverges, the series also diverges by the integral test.

**Example**

Use the integral test to determine if

$$
\sum_{n=1}^\infty \frac{n}{e^n}
$$

converges or diverges.

<button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden"></div>
{: id="box1b" class="answer-hidden"}


The integral test says the series converges if and only if

$$
\int_{x=1}^\infty \frac{x}{e^x} \, dx = \int_{x=1}^\infty xe^{-x} \, dx
$$

converges. We know this integral converges (recall that $$xe^{-x}$$ is the PDF for the exponential distribution). But we can also compute it again.

This integral is a good candidate for integration by parts, with

$$
\begin{align*}
u &= x & du &= dx
dv &= e^{-x} \, dx & v &= -e^{-x}.
\end{align*}
$$

Thus,

$$
\begin{align*}
\int_{x=1}^\infty xe^{-x} &= -xe^{-x} \bigg\vert_{x=1}^\infty - \int_{x=1}^\infty -e^{-x}\, dx
&= -xe^{-x} - e^{-x} \bigg\vert_{x=1}^\infty
&= 0 - (-e^{-1}-e^{-1})
&= \frac{2}{e}.
\end{align*}
$$

Since the integral converges, the series converges too, by the integral test.
The p-series test

The next example is important enough that it gets its own name: the p-series. This makes use of the p-integrals that we computed earlier.

**Example**

Find the values of $$p$$ for which the series

$$
\sum_{n=1}^\infty \frac{1}{n^p}
$$

converges.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


We know from the integral test that

$$
\sum_{n=1}^\infty frac{1}{n^p}
$$

converges if and only if

$$
\int_{x=1}^\infty \frac{1}{x^p} \, dx
$$

converges. But this integral converges if and only if $$p>1$$, as we saw in the module on p-integrals. Therefore, the p-series converges if and only if $$p>1$$.

The p-series test

The p-series $$\displaystyle \sum_{n=1}^\infty \frac{1}{n^p}$$ converges if and only if $$p>1$$.
Harmonic series

The series $$\sum \frac{1}{n}$$, known as the harmonic series, diverges by to the p-series test. This is a significant fact to keep in mind because the harmonic series diverges even though the terms of the series go to 0. Thus, the harmonic series is a demonstration that the nth term test is a test for divergence only and cannot be used to show a series converges.

Note that the harmonic series is a sort of boundary between convergence and divergence. The series $$\sum \frac{1}{n^{.999}}$$ diverges, but the series $$\sum \frac{1}{n^{1.001}}$$ converges.

**Example**

The p-series test proves the convergence of two examples from the last module: $$\sum \frac{1}{n^2}$$ and $$\sum \frac{1}{n^3}$$.

**Example**

Determine the values of $$p$$ for which the series

$$
\sum_{n=2}^\infty \frac{1}{n (\ln n)^p}
$$

converges.

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


Making the substitution

$$
\begin{align*}
u &= \ln x
du &= \frac{1}{x} \, dx,
\end{align*}
$$

we see that

$$
\int_{x=2}^\infty \frac{1}{x (\ln x)^p} \, dx = \int_{u = \ln 2}^\infty \frac{1}{u^p} \, du.
$$

This integral (again from our knowledge of the p-integral) converges if and only if $$p>1$$. Therefore, by the integral test, the series

$$
\sum_{n=2}^\infty \frac{1}{n (\ln n)^p}
$$

converges if and only if $$p>1$$.
Comparison test

The integral test compared a series to its related integral. This test compares one series to another.

Comparison test

Let $$a_n$$ and $$b_n$$ be positive sequences such that $$b_n>a_n$$ for all $$n$$. It follows that

- if $$\sum b_n$$ converges, then $$\sum a_n$$ converges.
- if $$\sum a_n$$ diverges, then $$\sum b_n$$ diverges. 

In other words, if a series is smaller than a convergent series, then it converges too. If a series is bigger than a divergent series, then it diverges too.
Caveat

It is critical that the inequality be in the correct direction. A series which is larger than a convergent series might converge or diverge. A series which is smaller than a divergent series might converge or diverge.

**Example**

Show that $$\sum \frac{\ln(n)}{n}$$ diverges.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Note that $$\frac{\ln(n)}{n} > \frac{1}{n}$$. Since $$\sum \frac{1}{n}$$ diverges, the series $$\sum \frac{\ln(n)}{n}$$ diverges too, by the comparison test.

**Example**

Show that

$$
\sum_{n=4} \frac{n^3-2n^2-10}{n^5+7}
$$

converges.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Note that

$$
\frac{n^3-2n^2-10}{n^5+7} < \frac{n^3}{n^5} = \frac{1}{n^2},
$$

since the numerator on the left is smaller, and the denominator on the left is bigger. So

$$
\sum_{n=4}^\infty \frac{n^3-2n^2-10}{n^5+7} < \sum_{n=4}^\infty \frac{1}{n^2}.
$$

$$\sum \frac{1}{n^2}$$ converges (p-series test from above), and so

$$
\sum_{n=4}^\infty \frac{n^3-2n^2-10}{n^5+7}
$$

converges as well, by the comparison test.

**Example**

Determine whether

$$
\sum_{n=2}^\infty \frac{1}{\ln(n!)}
$$

converges or diverges. Hint: try for a rough upper bound or lower bound on $$n!$$ and see which one gives the right comparison.

<button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


A lower bound for $$n!$$ might be $$2^n$$ (or any exponential). This gives

$$
\begin{align*}
\sum \frac{1}{\ln(n!)} &< \sum \frac{1}{\ln(2^n)}
&= \sum \frac{1}{n \ln(2)}
&= \frac{1}{\ln 2} \sum \frac{1}{n},
\end{align*}
$$

which diverges, since it is a constant multiple of the harmonic series. This comparison does not go in the right direction, since our original series is smaller than a divergent series. Thus, we should try going in the other direction to find an upper bound for $$n!$$.

A rough upper bound for $$n!$$ is $$n^n$$. This gives

$$
\begin{align*}
\sum \frac{1}{\ln(n!)} &> \sum \frac{1}{\ln(n^n)}
&= \sum \frac{1}{n \ln(n)}.
\end{align*}
$$

This series diverges (see the example earlier in this module). Therefore, the original series, which is bigger than a divergent series, also diverges.
Limit test

The final test of this module is a slightly different type of comparison. Recall that when comparing two functions $$f$$ and $$g$$ to see which is "bigger" asymptotically, one computes the limit

$$
\lim_{n \rightarrow \infty} \frac{f(n)}{g(n)}.
$$

If this limit is infinite, then $$f$$ is bigger. If the limit is 0, then $$g$$ is bigger. If the limit is $$L$$ where $$0<L<\infty$$, then the two functions are roughly equal (up to a constant multiple). It is this third case that is used for this test (sometimes called the Limit comparison test):

Limit test

Let $$a_n$$ and $$b_n$$ be positive series. If $$\lim_{n \rightarrow \infty} \frac{a_n}{b_n} =L$$ and $$0<L<\infty$$, then the series $$\sum a_n$$ and $$\sum b_n$$ either both converge or both diverge.

The key to the limit test is finding a suitable sequence $$b_n$$ which is approximately equal to $$a_n$$ in the limit. Often, $$a_n$$ will be a ratio, in which case the lower order terms in the numerator and denominator can be dropped, and what is left will be $$b_n$$. Ideally, it will be easy to see if $$\sum b_n$$ converges or diverges. Finally, one must check that $$0 < \lim_{n \rightarrow \infty} \frac{a_n}{b_n} < \infty$$.

**Example**

Show that

$$
\sum \frac{n^2-n}{n^3+7}
$$

diverges.

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


By dropping the lower order terms in the numerator and denominator, one finds

$$
\frac{n^2-n}{n^3+7} \approx \frac{n^2}{n^3} = \frac{1}{n}.
$$

So $$b_n = \frac{1}{n}$$ is a good choice. Assuming the above approximation is not too rough, the work is done since the harmonic series, $$\sum \frac{1}{n}$$, diverges.

To make sure the approximation is not too rough, compute the limit

$$
\begin{align*}
\lim_{n \rightarrow \infty} \frac{a_n}{b_n} &= \lim_{n \rightarrow \infty} \frac{\left(n^2-n\right)/\left(n^3+7\right)}{1/n}
&= \lim_{n \rightarrow \infty} \frac{n(n^2-n)}{n^3+7}
&= \lim_{n \rightarrow \infty} \frac{n^3-n^2}{n^3+7}
&= 1.
\end{align*}
$$

Thus, by the limit test, $$\sum \frac{n^2-n}{n^3+7}$$ and $$\sum \frac{1}{n}$$ either both converge or both diverge. Since $$\sum \frac{1}{n}$$ diverges, so too must $$\sum \frac{n^2-n}{n^3+7}$$.

**Example**

Determine whether $$
\sum \sin \left(\frac{1}{n}\right)
$$

converges or diverges.

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


With an unusual series like this, the nth term test is a good first thing to try. But it is inconclusive since $$\sin(1/n) \rightarrow 0$$ as $$n \rightarrow \infty$$.

To get a handle on how this function acts, note that when $$n$$ is large, $$1/n$$ is small, and so we can use the Taylor series for $$\sin x$$ about 0:

$$
\sin \left(\frac{1}{n}\right) = \frac{1}{n} + O\left(\frac{1}{n^3}\right).
$$

Thus, $$\sin(1/n) \approx \frac{1}{n}$$, which means $$\frac{1}{n}$$ is a good candidate for $$b_n$$ in the limit test. This will work:

$$
\begin{align*}
\lim_{n \rightarrow \infty} \frac{a_n}{b_n} &= \lim_{n \rightarrow \infty} \frac{\sin(1/n)}{1/n}
&= \lim_{n \rightarrow \infty} \frac{1/n + O(1/n^3)}{1/n}
&= 1.
\end{align*}
$$

Since $$\sum b_n = \sum \frac{1}{n}$$ diverges (harmonic series), it follows by the limit test that $$\sum \sin(1/n)$$ diverges also.

## Exercises

- Determine whether the following series converges or diverges 

$$
\sum_{n=1}^{\infty} \frac{n+4}{n (2+n^4)^{1/3}}
$$

$$
\sum_{n=1}^{\infty} \frac{\vert\sin(n)^n\vert}{n^2}
$$

