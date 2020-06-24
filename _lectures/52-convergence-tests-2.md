---
title: Convergence tests 2
description: Geometric series-type tests
lecture_number: 52
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
This module deals with the root test and the ratio test for convergence. Unlike the tests from the previous module, the tests of this module can be applied without having to find a good series to compare.

Recall that the geometric series

$$
1+x+x^2+x^3+\dotsb
$$

converges to $$\frac{1}{1-x}$$ provided that $$\vertx\vert<1$$. This fact is at the heart of both the root test and the ratio test.
Root test

The Root test

Given a series $$\sum a_n$$, with all $$a_n>0$$, let

$$
\begin{equation*} \rho = \lim_{n \rightarrow \infty} \sqrt[n]{a_n}. \end{equation*}
$$

If $$\rho<1$$, then $$\sum a_n$$ converges. If $$\rho>1$$, then $$\sum a_n$$ diverges. Finally, if $$\rho = 1$$, then the test is inconclusive.

<button class="toggle" data-box="#boxA">Answer</button>

<div id="boxA" class="answer-hidden"></div>
{: id="boxA" class="answer-hidden"}


Recall what it means that $$\lim \sqrt[n]{a_n} = \rho$$. It means that for a given $$\epsilon > 0$$, there exists an $$M$$ such that for all $$n>M$$,

$$
\left\vert \sqrt[n]{a_n} - \rho \right\vert < \epsilon.
$$

In other words, for $$n$$ sufficiently big, $$\sqrt[n]{a_n} \approx \rho$$, and so $$a_n \approx \rho^n$$. This says that, roughly speaking, the series is eventually geometric with common ratio $$\rho$$. Hence, the series converges for $$\rho<1$$ and diverges for $$\rho>1$$.

The root test works best when the term $$a_n$$ involves an nth power, or can be expressed as an nth power, although it can be used in other situations as well.

**Example**

Determine if

$$
\sum \left(\frac{n}{2n+1}\right)^n
$$

converges or diverges.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Computing, one finds that

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \sqrt[n]{a_n}
&= \lim_{n \rightarrow \infty} \sqrt[n]{\left(\frac{n}{2n+1}\right)^n}
&= \lim_{n \rightarrow \infty} \frac{n}{2n+1}
&= \frac{1}{2}.
\end{align*}
$$

Since $$\rho<1$$, the series converges by the root test.

**Example**

Determine if

$$
\sum \left(\frac{n}{n+1}\right)^{n^2}
$$

converges or diverges.

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Computing, one finds that

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \sqrt[n]{\left(\frac{n}{n+1}\right)^{n^2}}
&= \lim_{n \rightarrow \infty} \left(\frac{n}{n+1}\right)^n
&= \lim_{n \rightarrow \infty} \frac{1}{(1+1/n)^n}
&= \frac{1}{e}.
\end{align*}
$$

The last step above follows from the fact that $$\lim_{n \rightarrow \infty} (1+1/n)^n = e$$. Thus, $$\rho<1$$ and so the series converges by the root test.

**Example**

Use the root test on the p-series

$$
\sum_{n=1}^\infty \frac{1}{n^p}.
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


Trying the root test gives

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \sqrt[n]{\frac{1}{n^p}}
&= \lim_{n \rightarrow \infty} \left(\frac{1}{n^{1/n}}\right)^p
&= 1,
\end{align*}
$$

and so the root test is inconclusive.

The last step above follows from the fact that $$\lim_{n \rightarrow \infty} n^{1/n} = 1$$. Let $$y = \lim_{n \rightarrow \infty} n^{1/n}$$. Taking the natural log of both sides gives

$$
\begin{align*}
\ln(y) &= \lim_{n \rightarrow \infty} \frac{1}{n} \ln(n)
&= \lim_{n \rightarrow \infty} \frac{\ln(n)}{n}
&= 0.
\end{align*}
$$

Thus $$y = e^0 = 1$$, as desired.
Ratio test

The Ratio Test

Given a series $$\sum a_n$$, with all $$a_n>0$$, let

$$
\begin{equation*} \rho = \lim_{n \rightarrow \infty} \frac{a_{n+1}}{a_n}. \end{equation*}
$$

If $$\rho<1$$, then the series $$\sum a_n$$ converges. If $$\rho>1$$, then the series $$\sum a_n$$ diverges. If $$\rho = 1$$, then the test is inconclusive (the series might converge or diverge).

<button class="toggle" data-box="#boxB">Answer</button>

<div id="boxB" class="answer-hidden"></div>
{: id="boxB" class="answer-hidden"}


As in the justification for the root test, $$\frac{a_{n+1}}{a_n}$$ is eventually very close to $$\rho$$, and remains close to $$\rho$$ ever after. Roughly speaking, then $$a_{n+1} \approx \rho a_n$$ for all sufficiently big $$n$$. But that means that after a while, the series becomes roughly geometric with common ratio $$\rho$$. Therefore, when $$\rho<1$$ the series converges, and when $$\rho>1$$ the series diverges.

The ratio test works best when $$a_n$$ involves exponential functions and factorials, since in these situations there is a lot of cancellation. It does not work well with ratios of polynomials, because the test is inconclusive.

**Example**

Determine if the series

$$
\sum \frac{n}{3^n}
$$

converges or diverges.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Here, $$a_n = \frac{n}{3^n}$$. Computing, one finds

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \frac{a_{n+1}}{a_n}
&= \lim_{n \rightarrow \infty} \frac{\left(n+1\right)/\left(3^{n+1}\right)}{n/3^n}
&= \lim_{n \rightarrow \infty} \frac{n+1}{3^{n+1}}\cdot \frac{3^n}{n}
&= \lim_{n \rightarrow \infty} \frac{1}{3}\frac{n+1}{n}
&= \frac{1}{3}.
\end{align*}
$$

$$\rho<1$$, and so by the ratio test, the series converges.

**Example**

Determine if the series

$$
\sum \frac{n!}{(2n)!}
$$

converges or diverges.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


In this example, $$a_n = \frac{n!}{(2n)!}$$. Computing gives

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \frac{a_{n+1}}{a_n}
&= \lim_{n \rightarrow \infty} \frac(n+1)!}{\left[2(n+1)\right]!} \cdot \frac{(2n)!}{n!}
&= \lim_{n \rightarrow \infty} \frac{n+1}{\left(2n+2\right)\left(2n+1\right)
&= \lim_{n \rightarrow \infty} \frac{n+1}{4n^2+6n+2}
&= 0.
\end{align*}
$$

So $$\rho<1$$, and the series converges by the ratio test.

**Example**

Show that the ratio test is inconclusive on the p-series $$\sum \frac{1}{n^p}$$.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Computing shows that

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \frac{1/(n+1)^p}{1/n^p}
&= \lim_{n \rightarrow \infty} \frac{n^p}{(n+1)^p}
&= \lim_{n \rightarrow \infty} \left( \frac{n}{n+1} \right)^p
&= 1,
\end{align*}
$$

and so the ratio test is inconclusive.

**Example**

Determine if the series

$$
\sum_{n=0}^\infty \frac{4^n}{(2n)!}
$$

converges or diverges.

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


There is a quick, tricky way to see that this converges, which is to note that

$$
\sum_{n=0}^\infty \frac{4^n}{(2n)!} = \sum_{n=0}^\infty \frac{2^{2n}}{(2n)!},
$$

which is the Taylor series for $$\cosh x$$ with $$x=2$$. We know $$\cosh$$ converges everywhere, so we know this series converges.

Alternatively, we can use the ratio test. We have $$a_n = \frac{4^n}{(2n)!}$$. Therefore

$$
\begin{align*}
\rho &= \lim_{n \rightarrow \infty} \frac{a_{n+1}}{a_n}
&= \lim_{n \rightarrow \infty} \frac{4^{n+1}}(2(n+1))!} \cdot \frac{(2n)!}{4^n}
&= \lim_{n \rightarrow \infty} \frac{4 \cdot 4^n}{(2n+2)\cdot (2n+1) \cdot (2n)!} \cdot \frac{(2n)!}{4^n}
&= \lim_{n \rightarrow \infty} \frac{4}{\left(2n+2\right)\cdot \left(2n+1\right)
&= 0.
\end{align*}
$$

Since $$\rho<1$$, this series converges by the ratio test, confirming what we already knew.
Summary of methods for a positive series

There is no foolproof method for determining the convergence or divergence of a series. However, here is a rough guide for tests to try. Given a series $$\sum a_n$$, where $$a_n>0$$ for all $$n$$:

- Do the terms go to 0? If $$\lim_{n \rightarrow \infty} a_n \neq 0$$, then by the nth term test, the series diverges. (If $$\lim_{n \rightarrow \infty} a_n = 0$$, then the test is inconclusive).
- Does $$a_n$$ involve exponential functions like $$c^n$$ where $$c$$ is constant? Does $$a_n$$ involve factorial? Then the ratio test should be used.
- Is $$a_n$$ of the form $$(b_n)^n$$ for some sequence $$b_n$$? Then use the root test.
- Does ignoring lower order terms make $$a_n$$ look like a familiar series (e.g. p-series or geometric series)? Then use the comparison test or the limit test.
- Does the sequence $$a_n$$ look easy to integrate? Then use the integral test. 


## Exercises

- Determine whether the following series converges or diverges 

$$
\sum_{n=2}^\infty \frac{1}{\ln^n(n)}
$$

$$
\sum_{n=1}^\infty \frac{2^n3^{4n}}{n!}
$$

What does the ratio test say about the convergence of 

$$
\sum_{n=1}^\infty \frac{2n(2n-2)(2n-4) \dots 2}{(2n-1)(2n-3) \dots 1}
$$

