---
title: Computing Taylor series
description: Using composition to compute Taylor series
lecture_number: 4
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
The previous module gave the definition of the Taylor series for an arbitrary function. It turns out that this is not always the easiest way to compute a function's Taylor series. Just as functions can be added, subtracted, multiplied, and composed, so can their corresponding Taylor series.

Recall that the Taylor series for a function $$f$$ is given by

$$
 f(x) = \sum_{k=0}^\infty \frac{f^{\left(k\right)}(0)}{k!} x^k = f(0) + f'(0)x + \frac{f''(0)}{2!} x^2 + \dotsb. $$

Using the definition of the Taylor series involves taking a lot of derivatives, which could be a lot of work, especially if the function involves compositions and products of functions, e.g. $$f(x) = \sin(x^2)e^{x^3}$$. This module will show how to compute the Taylor series of such functions more easily by using the Taylor series for functions we already know.
Substitution

Our first method, substitution, allows us to plug one function into the Taylor series of another. Consider the function $$
 f(x) = \frac{1}{x} \sin (x^2). $$

Computing the Taylor series for $$f$$ from the definition would involve the quotient rule, chain rule, and a lot of algebra. But by taking the series for $$\sin x$$ and substituting $$x^2$$ into this series, and then distributing the $$\frac{1}{x}$$, one finds

$$
\begin{align*}
\frac{1}{x} \sin(x^2) &= \frac{1}{x} \left((x^2) - \frac{1}{3!}(x^2)^3 + \frac{1}{5!}(x^2)^5 - \dotsb \right)
&= \frac{1}{x} \left(x^2 - \frac{1}{3!}x^6 + \frac{1}{5!}x^{10} - \dotsb \right)
&= x - \frac{1}{3!}x^5 + \frac{1}{5!}x^9 - \dotsb.
\end{align*}
$$

Note that getting this many terms using the definition would involve taking nine derivatives of the original function, which would be a lot of work! To get a more complete description of the Taylor series, one can use the summation notation, and again substitute to find

$$
\begin{align*}
\frac{1}{x} \sin(x^2) &= \frac{1}{x} \sum_{k=0}^\infty (-1)^k \frac{(x^2)^{2k+1}}{(2k+1)!}
&= \frac{1}{x} \sum_{k=0}^\infty (-1)^k \frac{x^{4k+2}}{(2k+1)!}
&= \sum_{k=0}^\infty (-1)^k \frac{x^{4k+1}}{(2k+1)!}
\end{align*}
$$

Example Find the Taylor series for $$e^{x^3}$$ by substitution. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Recall the series for $$e^x$$ is

$$
 e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dotsb = \sum_{k=0}^\infty \frac{x^k}{k!} $$

Substituting $$x^3$$ into the series for $$e^x$$ gives

$$
\begin{align*}
e^{x^3} &= 1 + x^3 + \frac{(x^3)^2}{2!} + \frac{(x^3)^3}{3!} + \dotsb
&= 1 + x^3 + \frac{x^6}{2!} + \frac{x^9}{3!} + \dotsb
&= \sum_{k=0}^\infty \frac{(x^3)^k}{k!}
&= \sum_{k=0}^\infty \frac{x^{3k}}{k!}
\end{align*}
$$
Combining like terms

Another way to use previous knowledge of one Taylor series to find another is by combining like terms. This requires some careful algebra, but it is no more difficult than multiplying two polynomials together. For example, consider the function

$$
 f(x) = \cos^2(x) = \cos(x) \cdot \cos(x). $$

Finding the series for a function multiplied by another function is the same as taking the series for each function and multiplying them together, and then collecting like terms. This is where some algebra is required.

$$
\begin{align*}
\cos(x) \cdot \cos(x) &= \left(1 - \frac{1}{2!}x^2 + \frac{1}{4!}x^4 - \dotsb \right)\left(1 - \frac{1}{2!}x^2 + \frac{1}{4!}x^4 - \dotsb \right)
&= 1 + \left(-\frac{1}{2!} -\frac{1}{2!} \right)x^2 + \left(\frac{1}{4!} + \frac{1}{2!}\frac{1}{2!} + \frac{1}{4!}\right) x^4 + \dotsb
&= 1 - x^2 + \frac{1}{3}x^4 + \dotsb.
\end{align*}
$$

To see where the coefficient of $$x^4$$ comes from, note that every $$x^4$$ term comes from some term from the left series multiplied together with some term from the right series whose powers add up to 4. There are three such pairs: 1 on the left paired with $$\frac{1}{4!}x^4$$ on the right; $$-\frac{1}{2!}x^2$$ on the left paired with $$-\frac{1}{2!}x^2$$ on the right; and $$\frac{1}{4!}x^4$$ on the left paired with 1 on the right. This is the same algebra one would do when multiplying two polynomials together; this is just a way of collecting like terms in a systematic way.

Example Use the trigonometric identity

$$
 \cos^2 x = \frac{1+\cos(2x)}{2} $$

and substitution to find the series for $$\cos^2 x$$. Try to give the series in summation notation (other than the first term). <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


By the above identity,

$$
\begin{align*}
\cos^2x &= \frac{1}{2} \left(1 + \cos(2x)\right)
&= \frac{1}{2} \left(1 + \left(1 - \frac{(2x)^2}{2!} + \frac{(2x)^4}{4!} - \dotsb \right)\right)
&= \frac{1}{2} \left(2 - \frac{4x^2}{2} + \frac{16x^4}{24} - \dotsb \right)
&= 1 - x^2 + \frac{x^4}{3} - \dotsb.
\end{align*}
$$

In summation notation,

$$
\begin{align*}
\cos^2x &= \frac{1}{2} \left(1 + \sum_{k=0}^\infty (-1)^k \frac{(2x)^{2k}}{(2k)!}\right)
&= \frac{1}{2} + \frac{1}{2} \sum_{k=0}^\infty (-1)^k \frac{(2x)^{2k}}{(2k)!}
&= \frac{1}{2} + \sum_{k=0}^\infty (-1)^k \frac{2^{2k-1}x^{2k}}{(2k)!}
&= 1 + \sum_{k=1}^\infty (-1)^k \frac{2^{2k-1}x^{2k}}{(2k)!}.
\end{align*}
$$
Hyperbolic trigonometric functions

The hyperbolic trigonometric functions $$\sinh(x)$$, $$\cosh(x)$$, and $$\tanh(x)$$ are defined by

$$
\begin{align*}
\sinh(x) &= \frac{e^x - e^{-x}}{2}
\cosh(x) &= \frac{e^x+e^{-x}}{2}
\tanh(x) &= \frac{e^x - e^{-x}}{e^x + e^{-x}} = \frac{\sinh(x)}{\cosh(x)}.
\end{align*}
$$

These hyperbolic trig functions, although graphically quite different from their traditional counterparts, have several similar algebraic properties, which is why they are so named. For example, the Pythagorean identity for cosine and sine has a version for hyperbolic cosine and sine:

$$
 \cosh^2(x) - \sinh^2(x) = 1. $$

One can verify this using the definitions and some algebra. But there is a geometric intuition for this relationship. Recall that cosine and sine give the $$x$$ and $$y$$ coordinates, respectively, for a point on the unit circle $$x^2+y^2 = 1$$. The hyperbolic cosine and hyperbolic sine give the $$x$$ and $$y$$ coordinates, respectively, for points on the hyperbola $$x^2 - y^2 = 1$$:

Example Using the Taylor series for $$e^x$$ and substitution, show that the Taylor series for $$\cosh$$ and $$\sinh$$ are

$$
\begin{align*}
\cosh(x) &= 1 + \frac{x^2}{2!} + \frac{x^4}{4!} + \dotsb = \sum_{k=0}^\infty \frac{x^{2k}}{(2k)!}
\sinh(x) &= x + \frac{x^3}{3!} + \frac{x^5}{5!} + \dotsb = \sum_{k=0}^\infty \frac{x^{2k+1}}{(2k+1)!}.
\end{align*}
$$

Note that these are almost the same as the series for cosine and sine, respectively, except they do not alternate. This gives another reason for the names of these functions.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


$$
\begin{align*}
\cosh(x) &= \frac{e^x + e^{-x}}{2}
&= \frac{1}{2}\left[(1+x+\frac{x^2}{2!} + \dotsb)+(1-x+\frac{x^2}{2!}-\dotsb)\right]
&= \frac{1}{2}\left[2 + 2 \frac{x^2}{2!} + 2 \frac{x^4}{4!} +\dotsb \right]
&= 1+\frac{x^2}{2!} + \frac{x^4}{4!}+\dotsb
&= \sum_{k=0}^\infty \frac{x^{2k}}{(2k)!}.
\end{align*}
$$

$$
\begin{align*}
\sinh(x) &= \frac{e^x - e^{-x}}{2}
&= \frac{1}{2}\left[(1+x+\frac{x^2}{2!} + \dotsb)-(1-x+\frac{x^2}{2!}-\dotsb)\right]
&= \frac{1}{2}\left[2x + 2 \frac{x^3}{3!} + 2 \frac{x^5}{5!} +\dotsb \right]
&= x+\frac{x^3}{3!} + \frac{x^5}{5!}+\dotsb
&= \sum_{k=0}^\infty \frac{x^{2k+1}}{(2k+1)!}.
\end{align*}
$$
Manipulating Taylor series

Another way of using one Taylor series to find another is through differentiation and integration. For instance, to find the Taylor series for the derivative of $$f$$, one can differentiate the Taylor series for $$f$$ term by term.

Example By differentiating the Taylor series for $$\sinh$$ and $$\cosh$$, show that

$$
\begin{align*}
\frac{d}{dx} \sinh x &= \cosh x
\frac{d}{dx} \cosh x &= \sinh x.
\end{align*}
$$

This is yet another relationship which is similar (though not identical) to the relationship between sine and cosine. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Differentiating hyperbolic sine gives

$$
\begin{align*}
\frac{d}{dx} \sinh x &= \frac{d}{dx} \sum_{k=0}^\infty \frac{x^{2k+1}}{(2k+1)!}
&= \sum_{k=0}^\infty (2k+1) \frac{x^{2k}}{(2k+1)!}
&= \sum_{k=0}^\infty \frac{x^{2k}}{(2k)!}
&= \cosh x,
\end{align*}
$$

as desired. Similarly, differentiating hyperbolic cosine gives

 $$
\begin{align*}
\frac{d}{dx} \cosh x &= \frac{d}{dx} \sum_{k=0}^\infty \frac{x^{2k}}{(2k)!}
&= \sum_{k=0}^\infty (2k) \frac{x^{2k-1}}{(2k)!}
&= \sum_{k=1}^\infty \frac{x^{2k-1}}{(2k-1)!}
&= \sum_{k=0}^\infty \frac{x^{2k+1}}{(2k+1)!}.
\end{align*}
$$

There was a little bit of reindexing there, but by writing out a few terms of each series, one can see that all of the above equalities are true.
Higher Order Terms in Taylor Series

In some situations, it will be convenient only to write the first few terms of a Taylor series. This is particularly true when combining or composing more than one Taylor series. Up until now, an ellipsis has been used to indicate that there are more terms in the series that are being omitted.

There is another way, sometimes used in this course, of notating the omitted terms in a Taylor series. That is by referring to them as Higher Order Terms (or H.O.T. for short). Having the extra HOT in a series means that all the remaining terms in the series have a higher degree than the previous terms.

Example The function $$e^x$$ can be written as

$$
 e^x = 1+x + \frac{1}{2!}x^2 + \hbox{ HOT}, $$

or it could also be written as

$$
 e^x = 1+x + \hbox{ HOT}. $$

The point at which the higher order terms are cut-off is somewhat arbitrary and depends on the situation. There is a more formal way of keeping track of the higher order terms, called Big-O notation, which is presented in orders of growth.

Example Find the first two non-zero terms of the Taylor series for

$$
 f(x) = 1-2xe^{\sin x^2}. $$

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Beginning with the innermost function, in this case $$\sin x^2$$, we find that

$$
 \sin x^2 = x^2 - \frac{1}{3!}(x^2)^3 + \hbox{ HOT} = x^2 - \frac{1}{6}x^6 + \hbox{ HOT}. $$

Then plugging this into the series for $$e^x$$ gives $$
\begin{align*}
e^{\sin x^2} &= 1 + \left(x^2 - \frac{1}{6}x^6 + \hbox{ HOT}\right) + \frac{1}{2!} \left(x^2 + \hbox{ HOT}\right)^2 + \frac{1}{3!} \left(x^2 + \hbox{ HOT} \right)^3 + \hbox{ HOT}
&= 1 + x^2 + \frac{1}{2}x^4 + \left(-\frac{1}{6} + \frac{1}{6} \right)x^6 + \hbox{ HOT}
&= 1 + x^2 + \frac{1}{2}x^4 + \hbox{ HOT}
\end{align*}
$$

Then to complete the answer, plug this into the original function to find

$$
\begin{align*}
f(x) &= 1 - 2x \left( 1 + x^2 + \frac{1}{2}x^4 + \hbox{ HOT}\right)
&= 1 - 2x - 2x^3 - x^5 + \hbox{ HOT}.
\end{align*}
$$
Extra examples

**Example**

Compute the Taylor series (at 0) for $$\sin^2 x$$ up to and including terms of order 6. Try to give the full Taylor series in summation notation. <button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


$$
\begin{align*}
\sin^2 x &= (x-\frac{x^3}{3!}+\frac{x^5}{5!}-\dotsb)(x-\frac{x^3}{3!}+\frac{x^5}{5!}-\dotsb)
&= x^2 + (-\frac{1}{3!}-\frac{1}{3!})x^4 + (\frac{1}{5!} + \frac{1}{3!\cdot 3!} + \frac{1}{5!})x^6 + \dotsb
&= x^2 - \frac{1}{3} x^4 + \frac{2}{45} x^6 - \dotsb.
\end{align*}
$$

To get the full Taylor series, one can use the identity

$$
 \sin^2 x = \frac{1-\cos(2x)}{2} $$

to find that

$$
\begin{align*}
\sin^2 x &= \frac{1-\cos(2x)}{2}
&= \frac{1}{2} \left(1-\left(1-\frac{(2x)^2}{2!} + \frac{(2x)^4}{4!} - \dotsb \right) \right)
&= \frac{1}{2} \left( \frac{(2x)^2}{2!} - \frac{(2x)^4}{4!} + \frac{(2x)^6}{6!} - \dotsb \right)
&= \frac{1}{2} \sum_{k=1}^\infty (-1)^{k-1} \frac{(2x)^{2k}}{(2k)!}.
\end{align*}
$$

**Example**

Find the first three terms of the Taylor series for $$\sqrt{f(x)}$$, where

$$
 f(x) = a_0 + a_1 x + a_2 x^2 + a_3x^3 + \dotsb. $$ <button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


Let $$g(x) = \sqrt{f(x)}$$, where

$$
 g(x) = b_0 + b_1 x + b_2 x^2 + b_3 x^3 + \dotsb. $$

Then $$g(x)^2 = f(x)$$, and so the same holds for the Taylor series:

$$
 \left( b_0 + b_1 x + b_2 x^2 + b_3 x^3 + \dotsb \right)^2 = a_0 + a_1 x + a_2 x^2 + \dotsb. $$

Multiplying out and collecting like terms gives

$$
 b_0^2 + (b_0b_1 + b_1b_0) x + (b_0b_2 + b_1b_1 + b_2b_0) x^2 + \dotsb = a_0 + a_1 x + a_2 x^2 + \dotsb. $$

Now, equating coefficients of the monomials on the left and right gives the first few equations (of an infinite system of equations)

$$
\begin{align*}
b_0^2 &= a_0
2b_0b_1 &= a_1
2b_0b_2 + b_1^2 &= a_2.
\end{align*}
$$

Solving these equations gives the first three coefficients of $$g$$:

$$
\begin{align*}
b_0 &= \sqrt{a_0}
b_1 &= \frac{a_1}{2 \sqrt{a_0}}
b_2 &= \frac{1}{2 \sqrt{a_0}} \left(a_2 - \frac{a_1^2}{4a_0} \right).
\end{align*}
$$

Thus,

$$
 \sqrt{a_0 + a_1 x + a_2 x^2 + \dotsb} = \sqrt{a_0} + \frac{a_1}{2\sqrt{a_0}} x + \frac{1}{2 \sqrt{a_0}} \left(a_2 - \frac{a_1^2}{4a_0} \right) x^2 + \dotsb. $$

## Exercises

- Compute the Taylor series of $$\cos(2x)\sin(3x)$$ up to and including terms of degree 5. Don't try computing derivatives for this!
- Use a Taylor polynomial to give a cubic approximation to $$2xe^{3x}$$
- Compute the Taylor series of $$e^{1-\cos t}$$ in summation notation.
- Compute the Taylor series of $$\cos(\sin(x))$$ to fourth order.
- Compute the Taylor series of $$\sin(\cos(x))$$ to forth order. What happens that makes this different than the last problem? (Hint: $$\cos(0)=1$$ but $$\sin(0)=0$$...)
- Compute the first three nonvanishing terms in the Taylor series of $$e^{2x}(\sinh 3x)/x$$.
- Compute the Taylor series of $$3x^2 e^{-x^2} \sin 2x^3$$ up to and including terms of order eight (!) Wow, that means a lot of work, right? Think... which terms should you expand first?
- Compute the Taylor series of $$\frac{1}{x} e^{-x^2} \sinh(2x)$$ up to the fourth order term.
- What is the second derivative of the function $$e^{x \cosh(x^2)}$$ at $$x=0$$?
- Compute the following limit $$ \lim_{x \to 0} (1-e^x) \frac{\sin (x^2)}{x^3} $$ 