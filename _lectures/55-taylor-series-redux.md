---
title: Taylor series redux
description: Details about Taylor series convergence
lecture_number: 55
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
The last module took a sequence $$\left(a_n\right)$$ and turned it into a power series $$\displaystyle f(x) = \sum_{n=0}^\infty a_n x^n$$. This module turns this around and asks can we go from a function $$f(x)$$ to a sequence $$\left(a_n\right)$$? The answer is yes, and this is the familiar process of computing the Taylor series for the function. Recalling the Taylor series for $$f$$:

$$
f(x) = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \dotsb = \sum_{n=0}^\infty \frac{1}{n!} f^{\left(n\right)}(0)x^n,
$$

we see that $$a_n = \frac{1}{n!} f^{\left(n\right)}(0)$$ is the sequence corresponding to $$f(x)$$. We could also center the Taylor series at a different point, and get a different sequence, but for now let's keep things centered at 0.

Now that we have turned our function into its Taylor series, we come back to the questions deferred from earlier in the course:

- For what values of $$x$$ does a function's Taylor series converge?
- Does the Taylor series converge to the function? 

These questions are the topics of this module.
Taylor series convergence

We now have the tools to see when a power series converges, so the answer to the first question is that the series

$$
\sum_{n=0}^\infty a_n x^n = \sum_{n=0} \frac{1}{n!} f^{\left(n\right)}(0) x^n
$$

converges absolutely for $$\vertx\vert<R$$, where

$$
\begin{align*}
R & = \lim_{n \rightarrow \infty} \frac{\verta_n\vert}{\verta_{n+1}\vert}
& = \lim_{n \rightarrow \infty} \frac{f^{\left(n\right)}(0)}{n!} \cdot \frac{\left(n+1\right)!}{f^{\left(n+1\right)}(0)}
&= \lim_{n \rightarrow \infty} \left(n+1\right) \frac{f^{\left(n\right)}(0)}{f^{\left(n+1\right)}(0)}.
\end{align*}
$$

Within the interval of convergence, differentiation and integration of a power series are nice, in that they can be done term by term:

- $$\displaystyle \frac{df}{dx} = \sum_{n=0}^\infty n a_n x^{n-1}$$
- $$\displaystyle \int f(x)\, dx = \sum_{n=0}^\infty \frac{a_n}{n+1} x^{n+1} + C$$ 

Why is this useful? Being able to differentiate and integrate term by term allows us to compute the Taylor series for various functions by differentiating or integrating the Taylor series for other functions.
**Example**

Compute the Taylor series for $$\arctan x$$ by noting that $$\frac{d}{dx} \arctan x = \frac{1}{1+x^2}$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


We have that

$$
\begin{align*}
\frac{d}{dx} \arctan x &= \frac{1}{1+x^2}
&= 1- x^2+x^4 - x^6 + x^8 - \dotsb,
\end{align*}
$$

for $$\vertx\vert<1$$. Thus, for $$\vertx\vert<1$$, we can safely integrate both sides of this equation to find

$$
\begin{align*}
\arctan x &= \int \left(1- x^2+x^4 - x^6 + x^8 - \dotsb\right)dx
&= x - \frac{x^3}{3} + \frac{x^5}{5} - \frac{x^7}{7} + \frac{x^9}{9} - \dotsb + C.
\end{align*}
$$

By checking $$\arctan(0) = 0$$, we find that the integration constant $$C=0$$. Thus for $$\vertx\vert<1$$ we have

$$
\arctan x = x - \frac{x^3}{3} + \frac{x^5}{5} - \dotsb = \sum_{n=0}^\infty (-1)^n \frac{x^{2n+1}}{2n+1}.
$$

**Example**

Show that the power series $$f(x) = 1 + 2x + 3x^2 + 4x^3+ 5x^4 + \dotsb$$ can be written as $$\frac{1}{(1-x)^2}$$ for $$\vertx\vert<1$$. Hint: try integrating both sides and see what familiar function you get.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Integrating both sides gives

$$
\begin{align*}
\int f(x)dx &= \int (1 + 2x + 3x^2 + \dotsb) dx
&= x + x^2 + x^3 + \dotsb
&= \frac{x}{1-x},
\end{align*}
$$

by recognizing that this is the geometric series. Now, differentiating both sides gives that

$$
f(x) = \frac{1}{(1-x)^2},
$$

as desired. Note that this only holds within the interval of convergence for the geometric series, $$\vertx\vert<1$$.
**Example**

The Fresnel Integral $$C(x)$$ is defined by

$$
C(x) = \int_{t=0}^x \cos(t^2) dt.
$$

There is no elementary expression for this integral, but it can be expressed as a series by expanding the series for $$\cos$$ and then integrating term by term:

$$
\begin{align*}
C(x) &= \int_{t=0}^x \cos(t^2) dt
&= \int_{t=0}^x \left(\sum_{n=0}^\infty (-1)^n \frac(t^2)^{2n}}{(2n)!} \right) dt
&= \sum_{n=0}^\infty (-1)^n \frac{t^{4n+1}}{\left(2n\right)! \left(4n+1\right) \bigg\vert_{t=0}^x
&= \sum_{n=0}^\infty (-1)^n \frac{x^{4n+1}}{\left(2n\right)! \left(4n+1\right)}.
\end{align*}
$$

Taylor series convergence to a function

Now, we consider the second question above: when a Taylor series converges, does it always converge to the function? Unfortunately, not always. Even with a smooth $$f$$, and $$x$$ within the interval of convergence, it is possible that the Taylor series does not converge to $$f$$. The following definition is used for functions whose Taylor series do converge to the functions themselves:

Definition: Real-analytic function

A function $$f$$ is real-analytic at $$x=a$$ if for $$x$$ sufficiently close to $$a$$,

$$
f(x) = \sum_{n=0}^\infty \frac{1}{n!} f^{\left(n\right)}(a)(x-a)^n.
$$

That is, a function $$f$$ is real-analytic at $$a$$ if the Taylor series for $$f$$ converges to $$f$$ near $$a$$.

Almost all the functions we have encountered in this course are real-analytic. However, there are examples of smooth functions which are not real-analytic, as the next example shows.
**Example**

Consider the function

$$
f(x) = \begin{cases} e^{-1/x} & \hbox{ if } x > 0
0 & \hbox{ if } x \leq 0.\end{cases}
$$

To show that this function is smooth, we must show that its derivative exists at $$x=0$$ (everywhere else it is a composition of nice functions, so we need not worry). We use the definition of the derivative:

$$
\begin{align*}
\frac{df}{dx} \bigg\vert_{x=0} &= \lim_{h \rightarrow 0^+} \frac{f(h)-f(0)}{h}
&= \lim_{h \rightarrow 0^+} \frac{1}{h}e^{-1/h}.
\end{align*}
$$

This can either be thought of as a $$0/0$$ case for l'Hospital's rule, or we can do a change of variables $$t = \frac{1}{h}$$, which gives the limit

$$
\begin{align*}
\lim_{h \rightarrow 0^+} \frac{1}{h}e^{-1/h} &= \lim_{t \rightarrow \infty} t e^{-t}
&= \lim_{t \rightarrow \infty} \frac{t}{e^t}
&= 0,
\end{align*}
$$

since the exponential beats a polynomial asymptotically. So $$f'(0) = 0$$. It turns out that all of the higher derivatives of $$f$$ at 0 are 0 as well. So if we tried to expand this as a Taylor series, we would have

$$
\begin{align*}
f(x) &= f(0) + f'(0)x + \frac{1}{2!} f''(0) x^2 + \dotsb
&= 0 + 0x + 0x^2+\dotsb
&= 0.
\end{align*}
$$

So the Taylor series for $$f$$ converges to 0, despite the fact that $$f$$ is non-zero for $$x>0$$. 