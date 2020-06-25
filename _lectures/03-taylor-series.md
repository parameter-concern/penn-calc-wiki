---
title: Taylor series
description: The Taylor series defined and applied
lecture_number: 3
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
{::options parse_block_html="true" /}
The long polynomial from the last module is actually called a Taylor series about $$x=0$$ (this is referred to as a Maclaurin series in some textbooks, but this course will use the term Taylor series). The last module gave the Taylor series for $$e^x$$, $$\sin x$$, and $$\cos x$$. The logical next question is to ask whether every function has a Taylor series.

The answer is that most *reasonable* functions, and almost all of the functions encountered in this course, have a Taylor series. That is, every reasonable function $$f$$ can be written as

$$
f(x) = \sum_{k=0}^\infty c_k x^k = c_0 + c_1 x + c_2 x^2 + \dotsb.
$$

This module describes how to compute the coefficients $$c_k$$ for a given function $$f$$.

## The definition of a Taylor series at $$x=0$$

The definition of the Taylor series of $$f$$ at $$x=0$$ is

Taylor series at $$x=0$$
: $$
  \begin{equation*}
  f(x) = f(0) + \frac{f'(0)}{1!}x + \frac{f(0)}{2!}x^2 + \frac{f'(0)}{3!}x^3+\dotsb = \sum_{k=0}^\infty \frac{f^{\left(k\right)}(0)}{k!} x^k,
  \end{equation*} 
  $$
  
  where $$f^{\left(k\right)}(0)$$ is the $$k$$th derivative of $$f$$ evaluated at 0. In other words, the coefficient $$c_k$$ mentioned above is given by
  
  $$
  c_k = \frac{f^{\left(k\right)}(0)}{k!} = \frac{1}{k!} \cdot \frac{d^k f}{dx^k}\bigg\vert_0
  $$
{: .mathterm .definition }


This seems circular, since the definition uses the function, and its derivatives, to write down the function. However, the definition only actually requires information about the function at a single point (in this case, 0). It is best to think of the Taylor series as a way of turning a function into a polynomial.

**Example**

Compute the Taylor series for $$e^x$$ using the above definition to see that it matches the given series from the last module. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden">
Here, $$f(x) = e^x$$, and every derivative of $$e^x$$ is $$e^x$$. Therefore, for all $$k$$ we have

$$
 f^{\left(k\right)}(x) = e^x, $$

and so $$f^{\left(k\right)}(0) = 1$$ for all $$k$$. Plugging into the Taylor series formula gives

$$
\begin{align*}
f(x) &= \sum_{k=0}^\infty \frac{f^{\left(k\right)}(0)}{k!} x^k \\
&= \sum_{k=0}^\infty \frac{x^k}{k!} \\
&= 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dotsb,
\end{align*}
$$

as claimed.
</div>

**Example**

Compute the Taylor series for $$f(x) = \sin x$$ using the above definition, and verify it matches the series found using Euler's formula. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden">
Computing the derivatives, and then evaluating at $$x=0$$ gives the following table:

$$
\begin{align*}
f(x) &= \sin(x) & f(0) &= 0 \\
f'(x) &= \cos(x) & f'(0) &= 1 \\
f(x) &= -\sin(x) & f(0) &= 0 \\
f(x) &= -\cos(x) & f(0) &= -1 \\
& \vdots
\end{align*}
$$

Thus,

$$
\begin{align*}
\sin(x) &= 0 + \frac{1}{1!}x + \frac{0}{2!}x^2 + \frac{-1}{3!}x^3 + \dotsb \\
&= x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dotsb,
\end{align*}
$$

confirming what was found last time.
</div>

Example Compute the Taylor series for $$f(x) = x^2-5x+3$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden">
Again, by directly using the definition:

$$
\begin{align*}
f(x) &= x^2-5x+3 & f(0) &= 3 \\
f'(x) &= 2x-5 & f'(0) &= -5 \\
f(x) &= 2 & f(0) &= 2 \\
f(x) &= 0 & f(0) &= 0 \\
& \vdots
\end{align*}
$$

So it follows that

$$
f(x) = 3-5x+\frac{2}{2!}x^2 = 3-5x+x^2
$$

(since all the subsequent derivatives are 0), which is the original function. This should not be a surprise, since the Taylor series represents a function as a long polynomial (henceforth called by its proper name: series). If $$f$$ was a polynomial to begin with, it stands to reason that the Taylor series for $$f$$ should just be $$f$$ itself.
</div>

## Why Taylor series matter

The big idea of this module is that the Taylor series can be thought of as an operator (a machine) which turns a function into a series. This is a useful operator because some functions are hard (or even impossible) to express using combinations of familiar functions. Nevertheless, these functions can often be understood by computing their Taylor series.

**Example**

The *Bessel function*, denoted $$J_0$$, is best defined by its Taylor series:

$$
\begin{align*}
J_0 &= \sum_{k=0}^\infty (-1)^k \frac{x^{2k}}{2^{2k} (k!)^2} \\
&= 1 - \frac{1}{2^2} x^2 + \frac{1}{2^4(2!)^2}x^4 - \frac{1}{2^6 (3!)^2}x^6 + \dotsb
\end{align*}
$$

This series has only the even powers of $$x$$, and it alternates, which is reminiscent of the series for cosine. One difference is that the denominator in the Bessel function grows more quickly than the denominator in the series for cosine. Thus, we might expect the graph to be a wave with a decreasing amplitude, which is exactly what we find:

![Bessel]({{ site.baseurl }}/assets/images/Bessel.png)
{: .mathimg }

It turns out that the Bessel function describes many physical phenomena, including the shape of a hanging chain as it is rotated, and the shape of the waves formed after a stone is thrown into a pool of water.

## Taylor series as polynomial approximants

The main reason Taylor series are useful is that they turn a potentially complicated function into something simple: a polynomial. Granted, this polynomial is infinitely long in general, but in practice it is only necessary to compute the first few terms to get a good, local approximation of the function. The more terms one includes, the better the polynomial approximates the function.

As an example, consider a particle on the number line with position function $$p(t)$$. At time 0, say its position is 5. Then one approximation of its position as a function of time is $$p_0(t) = 5$$. Given more information, say its velocity at time 0 is 3, the approximation becomes better. The next approximation as a function of time is $$p_1(t) = 5+3t$$. Now, suppose its acceleration at time 0 is $$-4$$. Then $$p_2(t) = 5+3t-\frac{4}{2}t^2 = 5+3t-2t^2$$ is an even better polynomial approximation of the position function.

![Approximants]({{ site.baseurl }}/assets/images/Approximants.png)
{: .mathimg }

## Exercises

- What is the Taylor series of $$x^4-3x^3+2x^2+7x-3$$. This should be an easy one!
- What is the Taylor series of $$(x-2)^2(x-3)$$? This, also, should not be *too* hard...
- Compute a few derivatives and figure out the first few terms of the Taylor series of $$\displaystyle\frac{1}{1-x}$$. Have you seen this series before?
- What are the first two nonzero terms in the Taylor series of $$\sqrt[3]{1-2x}$$?
- What is the coefficient of the cubic term in the Taylor series of $$e^{-3x}$$?
- Use what you know about Taylor series to determine the third derivative of $$\sin^3(2x)\cos^2(3x)$$ at $$x=0$$. That's a *lot* easier than computing the derivatives!
- The ERF function is defined in terms of a difficult integral:
  
  $$
  ERF(x) = \frac{2}{\sqrt{\pi}}\int_0^x e^{-t^2}\, dt
  $$
  
- Even if you don't remember integrals all that well, you know how to integrate a polynomial, right? So, Taylor expand the integrand and integrate term by term to get the Taylor series for ERF.
- What is the third derivative of ERF(x) at zero?
- Why does a Taylor series have all those $$n!$$ terms in the denominator? Let's see. Compute the Taylor series of $$f(x) = (1+x)^5$$ by (1) using the binomial theorem (or multiplication) to expand that power; then (2) by differentiating the function and using the Taylor series formula. What do you notice when you keep computing higher derivatives?
