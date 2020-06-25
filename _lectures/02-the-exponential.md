---
title: The Exponential
description: The exponential function defined
lecture_number: 2
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
{::options parse_block_html="true" /}
This module deals with a very important function: the exponential. The first question one might ask is: what is the exponential function $$e^x$$? We know certain values of the function such as $$e^0 = 1$$, but what about an irrational input such as $$e^\pi$$, or an imaginary input $$e^i$$? Is it possible to make sense of these values?

The following definition answers these questions.

The Exponential $$e^x$$
: $$
  \begin{align*}
    e^x &= 1+x+\frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \dotsb \\
    &= \sum_{k=0}^\infty \frac{x^k}{k!},
  \end{align*}
  $$

  where $$k! = k(k-1)(k-2)\dotsb 3 \cdot 2 \cdot 1, $$ and $$0! = 1$$.
{: .mathterm .definition }

One can now plug values for $$x$$ into the above sum to compute $$e^x$$. When $$x=0$$, for instance, one finds that $$e^0 = 1$$, (since all the terms with $$x$$ disappear) as expected. By plugging in $$x=1$$, the true value of $$e$$ is found to be $$e = 1 + 1 + \frac{1}{2!} + \frac{1}{3!} + \dotsb$$.


## A long polynomial

There are technical concerns when trying to add up an infinite number of things. These issues will be dealt with later in the modules on [Series]({{ site.baseurl }}{% link _lectures/50-series.md %}). For now, treat the infinite sum above as a long polynomial (the actual term is the *Taylor series about* $$x=0$$, which will be more formally dealt with in [the next module]({{ site.baseurl }}{% link _lectures/03-taylor-series.md %})). Polynomials are nice because they are easy to integrate and differentiate. Recall the power rule for differentiating and integrating a monomial $$x^k$$, where $$k$$ is a constant:

$$
\begin{align*}
  \frac{d}{dx} x^k &= kx^{k-1} \\
  \int x^k \, dx &= \frac{1}{k+1} x^{k+1} + C \quad (k \neq -1)
\end{align*} 
$$

## Properties of $$e^x$$

Recall the following properties of the exponential function:

1.  $$e^{x+y} = e^xe^y$$&#8203;
2.  $$e^{x\cdot y} = (e^x)^y = (e^y)^x$$&#8203;
3.  $$\frac{d}{dx}e^x = e^x$$&#8203;
4.  $$\int e^x dx = e^x + C$$.

Consider the last two properties in terms of the long polynomial.Taking the derivative of the long polynomial for $$e^x$$ gives

$$
\begin{align*}
  \frac{d}{dx}(1+x+\frac{x^2}{2!}+\frac{x^3}{3!} + \frac{x^4}{4!} + \dotsb)
  &= 0 + 1 + \frac{2x}{2!} + \frac{3x^2}{3!} + \frac{4 x^3}{4!} + \dotsb \\
  &= 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dotsb,
\end{align*}
$$

which is the original long polynomial. Integrating also gives (up to the constant of integration) the original long polynomial. This agrees with facts about the derivative and integral of $$e^x$$. Thus, the long polynomial for $$e^x$$ captures two of the key features of $$e^x$$; namely, $$e^x$$ is its own derivative and its own integral.

## Euler's formula

Recall that the imaginary number $$i$$ is defined by $$i = \sqrt{-1}$$. So $$i^2=-1$$, $$i^3 = -i$$, $$i^4 = 1$$, and this continues cyclically (for a review of complex/imaginary numbers, see [wikipedia](http://en.wikipedia.org/wiki/Complex_number)). Assume the following fact, known as Euler's formula, mentioned in the last module.

Euler's Formula
: $$\begin{equation*} e^{ix}=\cos x+i\sin x \end{equation*}$$
{: .mathterm .theorem }

Consider what happens when $$ix$$ is plugged into the long polynomial for $$e^x$$. By simplifying the powers of $$i$$, and grouping the result into its real and imaginary parts, one finds

$$
\begin{align*}
e^{ix}
  &= 1+ix+\frac{(ix)^2}{2!}+\frac{(ix)^3}{3!} + \dotsb \\
  &= 1 + ix + \frac{i^2 x^2}{2!} + \frac{i^3 x^3}{3!} + \dotsb \\
  &= 1 + ix - \frac{x^2}{2!} - i\frac{x^3}{3!} + \frac{x^4}{4!} + i \frac{x^5}{5!} + \dotsb \\ 
  &= \left(1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dotsb\right) + i \left(x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dotsb \right).
\end{align*}
$$

If this is supposed to equal $$\cos x + i \sin x$$, then the real part must be $$\cos x$$, and the imaginary part must be $$\sin x$$. It follows that

$$
\begin{align*}
\cos x &= 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \dotsb = \sum_{k=0}^\infty (-1)^k \frac{x^{2k}}{(2k)!} \\
\sin x &= x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \dotsb = \sum_{k=0}^\infty (-1)^k \frac{x^{2k+1}}{(2k+1)!}.
\end{align*}
$$

These formulas should be memorized, both in their long polynomial form and their more concise summation notation form.

**Example**

Use Euler's formula to show that $$e^{i \pi} = -1$$. <button class="toggle" data-box="#box1">Answer</button>

Setting $$x=\pi$$ in Euler's formula gives $$e^{i \pi} = \cos \pi + i \sin \pi = -1$$.
{: id="box1" class="answer-hidden"}

**Example**

Compute $$1-\frac{\pi^2}{2!}+\frac{\pi^4}{4!}-\dotsb$$. <button class="toggle" data-box="#box2">Answer</button>

Note that this is the long polynomial for $$\cos x$$, evaluated at $$x=\pi$$. So the value is $$\cos \pi = -1$$.
{: id="box2" class="answer-hidden"}

**Example**

Check that taking the derivative of the long polynomial for $$\sin x$$ gives the long polynomial for $$\cos x$$ (hence, verify that $$\frac{d}{dx} \sin x = \cos x$$). <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden">
Computing the derivative term by term gives

$$
\begin{align*}
\frac{d}{dx} \sin(x)
  &= \frac{d}{dx} \left(x - \frac{x^3}{3!} + \frac{x^5}{5!} - \ldots \right) \\
  &= 1 - 3 \frac{x^2}{3!} + 5 \frac{x^4}{5!} - \ldots \\
  &= 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \ldots,
\end{align*} 
$$

which is the long polynomial for $$\cos x$$, as desired.
</div>

**Example**

Show that the long polynomial for $$e^x$$ satisfies the first property above, namely $$e^{x+y} = e^x e^y$$. Hint: start with the long polynomials for $$e^x$$ and $$e^y$$ and multiply these together, and carefully collect like terms to show it equals the long polynomial for $$e^{x+y}$$. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden">
Beginning with $$e^x \cdot e^y$$, we find

$$
\begin{align*}
e^x \cdot e^y
  &= \left(1+ x + \frac{x^2}{2!} + \dotsb \right) \left(1 + y + \frac{y^2}{2!} + \dotsb \right) \\
  &= 1 + (x+y) + \left( \frac{x^2}{2!} + xy + \frac{y^2}{2!} \right) + \dotsb \\
  &= 1 + (x+y) + \frac{x^2 + 2xy + y^2}{2!} + \dotsb \\
  &= 1 + (x+y) + \frac{(x+y)^2}{2!} + \dotsb,
\end{align*}
$$

which is the long polynomial for $$e^{x+y}$$, as desired.
</div>

## More on the long polynomial

The idea of a long polynomial is reasonable, because it actually comes from taking a sequence of polynomials with higher and higher degree:

$$
\begin{align*}
f_0(x) &= 1 \\
f_1(x) &= 1+x \\
f_2(x) &= 1+x+\frac{x^2}{2} \\
f_3(x) &= 1+ x+ \frac{x^2}{2} + \frac{x^3}{6} \\
&\vdots.
\end{align*}
$$

Each polynomial in the sequence is, in a sense, the best approximation possible of that degree. Put another way, taking the first several terms of the long polynomial gives a good polynomial approximation of the function. The more terms included, the better the approximation. This is how calculators compute the exponential function (without having to add up infinitely many things).

![Exponential Approximants]({{ site.baseurl }}/assets/images/ExponentialApproximants.png)
{: .mathimg }


## EXERCISES

- So, how good of an approximation is a polynomial truncation of $$e^x$$? Use a calculator to compare how close $$e$$ is to the linear, quadratic, cubic, quartic, and quintic approximations. How many digits of accuracy do you seem to be gaining with each additional term in the series?
- Now, do the same thing with $$1/e$$ by plugging in $$x=-1$$ into the series. Do you have the same results? Are you surprised?
- Use the first three terms of the series for $$e^x$$ to approximate $$\sqrt[10]{e}$$ and $$e^{10}$$. How accurate do you think these approximations are?
- Calculate the following sum using what you know:
  
  $$\sum_{n=0}^\infty (-1)^n\frac{(\ln 3)^n}{n!}$$
  
- Write out the first four terms of the following series
  
  $$\sum_{n=0}^\infty (-1)^n\frac{\pi^{2n}}{2^n n!}$$
  
- Write out the following series using summation notation:
  
  $$1 - \frac{2}{3!} + \frac{4}{5!} - \frac{8}{7!} + \cdots$$

- Estimate $$\sin(1/2)$$ to three digits of accuracy. How many terms in the series did this take?
- We've seen that $$i = e^{i\pi/2}$$ via Euler's formula. Using this and some algebra, tell me what is $$i^i$$. Isn't that nice? Now, tell me, what is $$(i^i)^i$$? Are you surprised? That's like, unreal!
- Practice your summation notation by rewriting the sum 
  
  $$\sum_{n=2}^\infty (-1)^n\frac{x^{n-2}}{n^3}$$
  
  as a sum over an index that goes from zero to infinity.
- Use the first two nonzero terms of the Taylor series for $$\cos(x)$$ to approximate $$\cos(\frac{1}{10}) $$.
- Use Euler's formula to derive the double angle formulas $$\cos(2 \theta) = \cos^2 (\theta) - \sin^2 (\theta)$$ and $$ \sin (2 \theta) = 2 \sin (\theta) \cos (\theta) $$.