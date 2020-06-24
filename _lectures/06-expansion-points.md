---
title: Expansion points
description: Taylor series expansions about other points
lecture_number: 6
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
Up until now, Taylor series expansions have all been at $$x=0$$. The Taylor series at $$x=0$$ gives a good approximation to the function near 0. But what if we want a good approximation to the function near a different point $$a$$? That is the topic of this module.
Expansion points

A function $$f$$ has a Taylor series expansion about any point $$x=a$$ provided that $$f$$ and all its derivatives exist at $$a$$. The definition of the Taylor series for $$f$$ about $$x=a$$ is

$$
\begin{align*}
f(x) &= f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \dotsb
&= \sum_{k=0}^\infty \frac{f^{\left(k\right)}(a)}{k!}(x-a)^k.
\end{align*}
$$

We say this is a series in $$(x-a)$$. A different way to view this series is by making the change of variables $$x = a+h$$. After cancellation, this yields

$$
\begin{align*}
f(a+h) &= f(a) + f'(a)h + \frac{f''(a)}{2!}h^2 + \dotsb
&= \sum_{k=0}^\infty \frac{f^{\left(k\right)}(a)}{k!}h^k.
\end{align*}
$$
Taylor polynomial for approximation

Recall that the first few terms of the Taylor series for $$f$$ about $$x=0$$ gives a polynomial (the Taylor polynomial) which is a good approximation for $$f$$ near 0. Similarly, the Taylor polynomial for $$f$$ about $$x=a$$ gives a polynomial which is a good approximation of $$f$$ near $$x=a$$. Note, however, that as the input gets further away from the expansion point $$a$$, the approximation gets worse.

Example Find the Taylor series for $$f(x) = 3x^2-x+4$$ about $$x=2$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Computing the derivatives, and evaluating at $$x=2$$, one finds

$$
\begin{align*}
f(x) &= 3x^2-x+4 & f(2) &= 14
f'(x) &= 6x-1 & f'(2) &= 11
f(x) &= 6 & f(2) &= 6
f(x) &= 0 & f(2) &= 0.
\end{align*}
$$

And all the subsequent derivatives are 0. So from the definition, one finds that

$$
\begin{align*}
f(x) &= 14 + 11(x-2) + \frac{6}{2!}(x-2)^2
&= 14 + 11(x-2) + 3(x-2)^2.
\end{align*}
$$

This appears to be different than the polynomial $$f$$ with which we began. If one multiplies out this polynomial and collects like terms, however, the result is the original polynomial. This should not be surprising, since the best polynomial approximation to a polynomial is the polynomial itself, even factored into a slightly different form.

Example Compute the Taylor series expansion for $$\ln(x)$$ about $$x=1$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Begin by computing the first few derivatives and evaluating at $$x=1$$:

$$
\begin{align*}
f(x) &= \ln(x) & f(1) &= 0
f'(x) &= x^{-1} & f'(1) &=1
f(x) &= -x^{-2} & f(1) &= -1
f(x) &= 2x^{-3} & f(1) &= 2.
\end{align*}
$$

The pattern that emerges is $$f^{\left(k\right)}(x) = (-1)^{k-1}(k-1)!x^{-k}$$. To see that the pattern holds, check that

$$
 \begin{equation*} f^{\left(k+1\right)}(x) = (-1)^{k-1} (-k)(k-1)!x^{-k-1} = (-1)^k k! x^{-(k+1)}, \end{equation*} 
$$ as desired. So by induction, the pattern holds. It follows that $$f^{\left(k\right)}(1) = (-1)^{k-1}(k-1)!$$ for $$k \geq 1$$. Plugging in to the formula, one finds that

$$
\begin{align*}
\ln(x) &= \sum_{k=1}^\infty \frac{(-1)^{k-1}(k-1)!}{k!}(x-1)^k
&= \sum_{k=1}^\infty (-1)^{k-1} \frac{(x-1)^k}{k}
&= (x-1) - \frac{(x-1)^2}{2} + \frac{(x-1)^3}{3} - \frac{(x-1)^4}{4}+\dotsb.
\end{align*}
$$

Note that with the change of variables $$h = x-1$$ (and hence $$x = h+1$$, we find that $$
 \ln(1+h) = h - \frac{h^2}{2} + \frac{h^3}{3} - \frac{h^4}{4} + \dotsb, $$

which is the same series we found earlier for $$\ln(1+x)$$.

Note that the Taylor polynomial is only a good approximation to the function on the domain of convergence. For functions whose domain of convergence is the entire number line, this is not a concern. But for functions such as $$\ln x$$, the Taylor polynomials will only be a good approximation within the domain of convergence, which is $$0 < x < 2$$. Outside of that domain, the Taylor polynomials diverge wildly from $$\ln x$$, as shown here:

Even within a function's domain of convergence, a Taylor polynomial's approximation gets worse as the input gets further away from $$a$$. One way to improve an approximation is to include more and more terms of the Taylor series in the Taylor polynomial. However, this involves computing more and more derivatives. Another way to improve the approximation for $$f(x)$$ is to choose an expansion point $$a$$ which is close to $$x$$.

Example Use the Taylor polynomial of degree 2 for $$f(x) = \sqrt{x}$$ about $$x=1$$ to approximate $$\sqrt{10}$$. Then repeat the process about $$x=9$$ and compare the results. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Using the definition, one finds

$$
\begin{align*}
f(x) &= \sqrt{x} & f(1) &= 1 & f(9) &= 3
f'(x) &= \frac{1}{2\sqrt{x}} & f'(1) &= \frac{1}{2} & f'(9) &= \frac{1}{6}
f(x) &= -\frac{1}{4x^{3/2}} & f(1) &= -\frac{1}{4} & f''(9) &= -\frac{1}{108}
\end{align*}
$$

Thus, the Taylor polynomial about $$x=1$$ is

$$
\begin{align*}
\sqrt{x} & \approx 1 + \frac{1}{2}(x-1) - \frac{1/4}{2!}(x-1)^2
&= 1 + \frac{1}{2}(x-1) - \frac{1}{8}(x-1)^2.
\end{align*}
$$

And the corresponding approximation is

$$
\begin{align*}
\sqrt{10} &\approx 1 + \frac{1}{2}\cdot 9 - \frac{1}{8} \cdot 9^2
&\approx -4.6,
\end{align*}
$$

which is obviously quite far off the mark. On the other hand, the Taylor polynomial about $$x=9$$ is

$$
\begin{align*}
\sqrt{x} & \approx 3 + \frac{1}{6}(x-9) - \frac{1/{108}}{2!}(x-9)^2
&= 3 + \frac{1}{6}(x-9) - \frac{1}{216}(x-9)^2.
\end{align*}
$$

And the corresponding approximation is

$$
\begin{align*}
\sqrt{10} &\approx 3 + \frac{1}{6}\cdot 1 - \frac{1}{216} \cdot 1^2
&\approx 3.1620,
\end{align*}
$$

which is quite a good approximation of $$\sqrt{10}\approx 3.1623$$.
Caveat for compositions

When computing the Taylor expansion for the composition $$f \circ g$$ about $$x=a$$, one must be careful of expansion points. In particular, one cannot simply take the series for $$g$$ at $$x=a$$ and plug it into the series for $$f$$ at $$x=a$$.

Example Consider the expansion for $$e^{\cos(x)}$$ about $$x=0$$. Although $$\cos(x) = 1-\frac{x^2}{2!} +\dotsb$$, and $$e^x = 1+x+\frac{x^2}{2!}+\dotsb$$, one will run into trouble trying to write

$$
 \begin{equation*} e^{\cos(x)} = 1+(1-\frac{x^2}{2!} +\dotsb) + \frac{1}{2}(1-\frac{x^2}{2!} +\dotsb)^2 + \dotsb. \end{equation*} 
$$

The trouble is that collecting like terms requires adding up infinitely many things. For instance, the constant term above is $$1+1+\frac{1}{2}+\dotsb$$. The reason this is a problem is that Taylor series are supposed to give a good polynomial approximation of a function without requiring too much computation or information about the function.

Remember that $$e^x = 1+x+\frac{x^2}{2}+\dotsb$$ is a good approximation when $$x$$ is near 0. However, when $$x$$ is near 0, $$\cos(x)$$ is near 1. So plugging the series for $$\cos(x)$$ into the series for $$e^x$$ does not give a good approximation.

To avoid this problem when computing the Taylor series for the composition $$f \circ g$$ at $$x=a$$, one should plug the Taylor expansion of $$g$$ about $$x=a$$ into the expansion of $$f$$ about $$x=g(a)$$. In the above example, the expansion of $$e^x$$ about $$x=1$$ is

$$
 \begin{equation*} e^x = e + e(x-1) + \frac{e}{2!}(x-1)^2 + \dotsb, \end{equation*} 
$$ so

$$
\begin{align*}
e^{\cos(x)} &= e + e\left[\left(1-\frac{x^2}{2!}+\dotsb\right)-1\right] + \frac{e}{2!}\left[\left(1-\frac{x^2}{2!}+\dotsb\right)-1\right]^2 + \dotsb
&= e + e(-\frac{x^2}{2} + \dotsb) + \frac{e}{2}(-\frac{x^2}{2}+\dotsb)^2 + \dotsb
&= e - \frac{e}{2}x^2 + \dotsb.
\end{align*}
$$
EXERCISES:

- Without using a calculator, find a decimal approximation to $$\sqrt{83}$$ by Taylor-expanding $$\sqrt{x}$$ about $$a=81$$ and using the zero-th and first order terms.
- Without using a calculator, find a decimal approximation to $$\sqrt[3]{124}$$ using linear approximation. How close was your answer to truth?
- Without using a calculator, find a decimal approximation to $$\cos(1)$$ [in radians!] using linear approximation. How close was your answer to truth? (Hint: $$\pi/3\approx 1$$...)
- Taylor expand $$\sin x$$ about $$x=\pi$$ and compute all the terms. Does what you get make sense?
- Use completing the square and the geometric series to get the Taylor expansion about $$x=2$$ of $$ \frac{1}{x^2+4x+3} $$
- Approximate $$1004^{1/3}$$ using the zeroth and first order terms of the Taylor series. 