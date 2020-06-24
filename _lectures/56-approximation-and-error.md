---
title: Approximation and error
description: How to estimate an infinite series
lecture_number: 56
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
Given a series that is known to converge but for which an exact answer is not known, how does one find a good approximation to the true value? One way to get an approximation is to add up some number of terms and then stop. But how many terms are enough? How close will the result be to the true answer? That is the motivation for this module.
Error defined

Given a convergent series

$$
\begin{equation*} s = \sum_{n=0}^\infty a_n. \end{equation*}
$$

Recall that the partial sum $$s_k$$ is the sum of the terms up to and including $$a_k$$, i.e.,

$$
\begin{align*}
s_k &= a_0+a_1+a_2+\ldots+a_k
&= \sum_{n=0}^k a_n.
\end{align*}
$$

Then the error $$E_k$$ is the difference between $$s_k$$ and the true value $$s$$, i.e.,

$$
\begin{align*}
E_k &= s - s_k
&= \sum_{n=0}^\infty a_n - \sum_{n=0}^k a_n
&= a_{k+1}+a_{k+2}+a_{k+3}+\ldots
&= \sum_{n=k+1}^\infty a_n.
\end{align*}
$$

In other words, the error is the sum of all the terms from the infinite series which were not included in the partial sum.
Alternating series error bound

For a decreasing, alternating series, it is easy to get a bound on the error $$E_k$$:

$$
\begin{equation*} \vertE_k\vert \leq \verta_{k+1}\vert. \end{equation*}
$$

In other words, the error is bounded by the next term in the series.
Note

If the series is strictly decreasing (as is usually the case), then the above inequality is strict.

To see why the alternating bound holds, note that each successive term in the series overshoots the true value of the series. In other words, if $$S$$ is the true value of the series,

$$
\begin{align*}
a_0 &> S
a_0 - a_1 &< S
a_0 - a_1 + a_2 &> S.
\end{align*}
$$

The above figure shows that if one stops at $$a_0 - a_1+a_2-a_3$$, then the error $$E_3$$ must be less than $$a_4$$.
**Example**

What is the minimum number of terms of the series

$$
\begin{equation*} \sum_{n=1}^\infty (-1)^{n+1} \frac{1}{n^2} \end{equation*}
$$

one needs to be sure to be within $$\frac{1}{100}$$ of the true sum?

The goal is to find $$k$$ so that $$\vertE_k\vert \leq \frac{1}{100}$$. Since $$\vertE_k\vert \leq \verta_{k+1}\vert$$, the question becomes for which value of $$k$$ is $$\verta_{k+1}\vert \leq \frac{1}{100}$$? If $$k=9$$, then $$\verta_{k+1}\vert = \frac{1}{100}$$, and so by the alternating series error bound, $$\vertE_9\vert \leq \frac{1}{100}$$. Thus 9 terms are required to be within $$\frac{1}{100}$$ of the true value of the series.
Integral test for error bounds

Another useful method to estimate the error of approximating a series is a corollary of the integral test. Recall that if a series $$\sum f(n)$$ has terms which are positive and decreasing, then

$$
\begin{equation*} \int_{m+1}^\infty f(x)dx < \sum_{n=m+1}^\infty f(n) < \int_{m}^\infty f(x)dx. \end{equation*}
$$

But notice that the middle quantity is precisely $$E_m$$. So

$$
\begin{equation*} \int_{m+1}^\infty f(x)dx < E_m < \int_{m}^\infty f(x)dx. \end{equation*}
$$

This bound is nice because it gives an upper bound and a lower bound for the error.
**Example**

How many terms of the series

$$
\begin{equation*} \sum_{n=1}^\infty \frac{1}{n^3} \end{equation*}
$$

must one add up so that the Integral bound guarantees the approximation is within $$\frac{1}{100}$$ of the true answer?

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


If one adds up the first $$m$$ terms, then by the integral bound, the error $$E_m$$ satisfies

$$
\begin{align*}
E_m &< \int_m^\infty \frac{dx}{x^3}
& = \frac{x^{-2}}{-2} \bigg\vert^\infty_m
&= \frac{1}{2m^2}.
\end{align*}
$$

Setting $$\frac{1}{2m^2} \leq \frac{1}{100}$$ gives that $$m^2 \geq 50$$, so $$m \geq 8$$. Thus, $$m=8$$ is the minimum number of terms required so that the Integral bound guarantees we are within $$\frac{1}{100}$$ of the true answer.
Note

If you actually compute the partial sums using a calculator, you will find that 7 terms actually suffice. But remember, we want the guarantee of the integral test, which only ensures that $$\frac{1}{128} < E_7 < \frac{1}{98}$$, despite the fact that in reality, $$E_7 \approx .009 < .01$$.
Taylor approximations

Recall that the Taylor series for a function $$f$$ about 0 is given by

$$
\begin{align*}
f(x) &= \sum_{n=0}^\infty \frac{f^{\left(n\right)}(0)}{n!} x^n
&= f(0) + f'(0)x + \frac{f''(0)}{2!}x^2+\dotsb.
\end{align*}
$$

The Taylor polynomial of degree $$N$$ is the approximating polynomial which results from truncating the above infinite series after the degree $$N$$ term:

$$
\begin{align*}
f(x) &\approx \sum_{n=0}^N \frac{f^{\left(n \right)}(0)}{n!} x^n
&= f(0) + f'(0)x + \frac{f''(0)}{2!}x^2+\dotsb + \frac{f^{\left(N\right)}(0)}{N!}x^N.
\end{align*}
$$

This is a good approximation for $$f(x)$$ when $$x$$ is close to 0. How good an approximation is it? That is the purpose of the last error estimate for this module.

As in previous modules, let $$E_N(x)$$ be the error between the Taylor polynomial and the true value of the function, i.e.,

$$
f(x) = \sum_{n=0}^N \frac{f^{\left(n \right)}(0)}{n!} x^n + E_N(x).
$$

Notice that the error $$E_N(x)$$ is a function of $$x$$. In general, the further away $$x$$ is from $$0$$, the bigger the error will be.

A first, weak bound for the error is given by

$$
E_N(x) \leq C x^{N+1}
$$

for some constant $$C$$ and $$x$$ sufficiently close to 0. In other words, $$E_N(x)$$ is $$O(x^{N+1})$$. A stronger bound is given in the next section.
Taylor remainder theorem

The following gives the precise error from truncating a Taylor series:

Taylor remainder theorem

The error $$E_N(x)$$ is given precisely by

$$
\begin{equation*} E_N(x) = \frac{f^{\left(N+1\right)}(t)}{(N+1)!}x^{N+1}, \end{equation*}
$$

for some $$t$$ between 0 and $$x$$, inclusive. So if $$x<0$$, then $$x \leq t \leq 0$$, and if $$x>0$$, then $$0 \leq t \leq x$$.
**Example**

Consider the case when $$N=0$$. The Taylor remainder theorem says that

$$
\begin{equation*} f(x) = f(0) + f'(t)x, \end{equation*}
$$

for some $$t$$ between 0 and $$x$$. Solving for $$f'(t)$$ gives

$$
\begin{equation*} f'(t) = \frac{f(x)-f(0)}{x-0}, \end{equation*}
$$

for some $$0<t<x$$ if $$x>0$$ and $$x<t<0$$ if $$x<0$$, which is precisely the statement of the Mean value theorem. Therefore, one can think of the Taylor remainder theorem as a generalization of the Mean value theorem.
Taylor error bound

As it is stated above, the Taylor remainder theorem is not particularly useful for actually finding the error, because there is no way to actually find the $$t$$ for which the equation holds. There is a slightly different form which gives a bound on the error:

Taylor error bound

$$
\begin{equation*} \vertE_N(x)\vert \leq \frac{C}{(N+1)!} \vertx\vert^{N+1}, \end{equation*}
$$

where $$C$$ is the maximum value of $$\vertf^{\left(N+1\right)}(t)\vert$$ over all $$t$$ between 0 and $$x$$, inclusive.
**Example**

Estimate $$\sqrt{e}$$ using

$$
\begin{equation*} e^{1/2} \approx 1 + \frac{1}{2} + \frac{(1/2)^2}{2!} + \frac{(1/2)^3}{3!} \approx 1.64, \end{equation*}
$$

and bound the error.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


The function is $$f(x) = e^x$$, and the approximating polynomial used here is

$$
\begin{equation*} e^x \approx 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!}. \end{equation*}
$$

Then according to the above bound,

$$
\begin{equation*} \vertE_3(x)\vert \leq \frac{C}{4!}\vertx\vert^4, \end{equation*}
$$

where $$C$$ is the maximum of $$f^{\left(4 \right)}(t) = e^t$$ for $$0 \leq t \leq x$$. Since $$e^t$$ is an increasing function, $$C = e^x$$. Thus,

$$
\begin{equation*} \vertE_3(x)\vert \leq \frac{e^x}{4!}x^4. \end{equation*}
$$

Thus,

$$
\begin{equation*} \vertE_3(1/2)\vert \leq \frac{e^{1/2}}{4!}(1/2)^4 < \frac{1}{100}. \end{equation*}
$$

