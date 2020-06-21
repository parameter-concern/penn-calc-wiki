---
title: Functions
description: Definition and examples of functions
lecture_number: 1
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
{::options parse_block_html="true" /}
A *function* can be visualized as a machine that takes in an input $$x$$ and returns an output $$f(x)$$. The collection of all possible inputs is called the *domain*, and the collection of all possible outputs is called the *range*.

This course deals with functions whose domains and ranges are $$\mathbb{R}$$ or subsets of $$\mathbb{R}$$ (this is the notation for the real numbers).

## Examples

- Polynomials, e.g. $$f(x) = x^3-5x^2+x+9$$. Give the domain and range of $$f$$. <button class="toggle" data-box="#box1">Answer</button>

The domain is $$\mathbb{R}$$, because we can plug in any real number into a polynomial. The range is $$\mathbb{R}$$, which we see by noting that this is a cubic function, so as $$x \rightarrow -\infty$$, $$f(x) \rightarrow -\infty$$, and as $$x \rightarrow \infty$$, $$f(x) \rightarrow \infty$$.
{: id="box1" class="answer-hidden"}

- Trigonometric functions, e.g. $$\sin$$, $$\cos$$, $$\tan$$. Give the domain and range for each of these. <button  class="toggle" data-box="#box2">Answer</button>

For $$\sin$$ and $$\cos$$: domain is $$\mathbb{R}$$; range is $$\left[-1,1\right]$$.  
For $$\tan$$, the domain is $$\lbrace x \in \mathbb{R}: x \neq \frac{\pi}{2}+k\pi\rbrace$$; range is $$\mathbb{R}$$.
{: id="box2" class="answer-hidden"}

- The exponential function, $$e^x$$. Give the domain and range for the exponential. <button  class="toggle" data-box="#box3">Answer</button>

Domain is $$\mathbb{R}$$; range is $$(0,\infty)$$.
{: id="box3" class="answer-hidden"}

- The natural logarithm function, $$\ln x$$. Recall that this is the inverse of the exponential function. Give the domain and range for $$\ln x$$. <button  class="toggle" data-box="#box4">Answer</button>

Domain is $$(0,\infty)$$; range is $$\mathbb{R}$$. Notice how the domain and range of the exponential relate to the domain and range of the natural logarithm.
{: id="box4" class="answer-hidden"}

- Is $$\sin^{-1}$$ a function? If so, why? If not, is there a way to make it into a function? <button  class="toggle" data-box="#box5">Answer</button>

$$\sin^{-1}$$ is not a function, because one input has many outputs. For example, $$\sin^{-1}(0) = 0,\pi,2\pi,\ldots$$. By restricting the range of $$\sin^{-1}$$ to $$\displaystyle\left[-\frac{\pi}{2},\frac{\pi}{2}\right]$$, one gets the function $$\arcsin$$.
{: id="box5" class="answer-hidden"}

## Operations on Functions

### Composition

The *composition* of two functions, $$f$$ and $$g$$, is defined to be the function that takes as its input $$x$$ and returns as its output $$g(x)$$ fed into $$f$$.

$$
\begin{equation*} f\circ g(x)=f(g(x)) \end{equation*}
$$

**Example**

$$ \begin{equation*} \sqrt{1-x^{2}} \end{equation*} $$ can be thought of as the composition of two functions, $$f$$ and $$g$$. If $$g=1-x^{2}$$, $$f$$ would be the function that takes an input $$g(x)$$ and returns its square root.

**Example**

Compute the composition $$f \circ f$$, i.e. the composition of $$f$$ with itself, where $$\displaystyle f(x) = \frac{1}{x+1}$$. <button class="toggle" data-box="#box5b">Answer</button>

<div id="box5b" class="answer-hidden">
We find that

$$
\begin{align*}
f \circ f(x) &= f(f(x)) \\
&= f \left(\frac{1}{x+1}\right) \\
&= \frac{1}{1/\left(x+1\right) +1} \\
&= \frac{x+1}{1 + x+1} \\
&= \frac{x+1}{x+2}.
\end{align*}
$$

</div>



### Inverse

The *inverse* is the function that undoes $$f$$. If you plug $$f(x)$$ into $$f^{-1}$$, you will get $$x$$. Notice that this function works both ways. If you plug $$f^{-1}(x)$$ into $$f(x)$$, you will get back $$x$$ again.

$$
\begin{equation*} f^{-1}(f(x))=x \end{equation*}
$$

$$
\begin{equation*} f(f^{-1}(x))=x \end{equation*}
$$

NOTE: $$f^{-1}$$ denotes the inverse, not the reciprocal. $$f^{-1}(x)\neq\frac{1}{f(x)}$$.

**Example**

Let’s consider $$f(x)=x^{3}$$. Its inverse is $$f^{-1}(x)=x^{\frac{1}{3}}$$.

$$
\begin{equation*} f^{-1}(f(x))=(x^{3})^{\frac{1}{3}}=x \end{equation*}
$$

$$
\begin{equation*} f(f^{-1}(x))=(x^{\frac{1}{3}})^{3}=x \end{equation*}
$$

Notice that the graphs of $$f$$ and $$f^{-1}$$ are always going to be symmetric about the line $$y=x$$. That is the line where the input and the output are the same:


## Classes of Functions


### Polynomials

A polynomial $$P(x)$$ is a function of the form

$$
\begin{equation*} P(x)=c_{0}+c_{1}x+c_{2}x^{2}+\dots+c_{n}x^{n} \end{equation*}
$$

The top power $$n$$ is called the degree of the polynomial. We can also write a polynomial using a summation notation.

$$
\begin{equation*} P(x)=\sum_{k=0}^{n}c_{k}x^{k} \end{equation*}
$$

### Rational functions

Rational functions are functions of the form $$\displaystyle\frac{P(x)}{Q(x)}$$ where each is a polynomial.

**Example**

$$ \begin{equation*} \displaystyle\frac{3x-1}{x^{2}+x-6} \end{equation*} $$ is a rational function. You have to be careful of the denominator. When the denominator takes a value of zero, the function may not be well-defined.

### Powers

*Power functions* are functions of the form $$cx^{n}$$, where $$c$$ and $$n$$ are constant real numbers.

Other powers besides those of positive integers are useful.

**Example**

What is $$x^{0}$$ ? <button class="toggle" data-box="#box6">Answer</button>


$$x^{0}=1$$&nbsp;
{: id="box6" class="answer-hidden"}

What is $$x^{-\frac{1}{2}}$$ ? <button class="toggle" data-box="#box7">Answer</button>

Recall a fractional power denotes root. For example, $$x^{\frac{1}{2}}=\sqrt{x}$$. The negative sign in the exponent means that we take the reciprocal. So, $$x^{-\frac{1}{2}}=\frac{1}{\sqrt{x}}$$.
{: id="box7" class="answer-hidden"}

What is $$x^\frac{22}{7}$$ ? <button class="toggle" data-box="#box8">Answer</button>

One can rewrite this as $$\left(x^{22}\right)^{1/7}$$. That means we take $$x$$ to the 22nd power and then take the 7th root of the result.
$$x^\frac{22}{7}=\sqrt[7]{x^{22}}$$
{: id="box8" class="answer-hidden"}

What is $$x^{\pi}$$ ? We are not yet equipped to handle this, but we will come back to it later.

### Trigonometrics

You should be familiar with the basic trigonometric functions $$\sin$$, $$\cos$$. One fact to keep in mind is $$\cos^{2} \theta +\sin^{2} \theta=1$$ for any $$\theta$$. This is known as a *Pythagorean identity*, which is so named because of one of the ways to prove it:

![Pythagorean identity visual proof](/assets/images/Pythagorean.png)
{: style="text-align: center;"}

By looking at a right triangle with hypotenuse 1 and angle $$\theta$$, and labeling the adjacent and opposite sides accordingly, one finds by using Pythagoras' Theorem that $$\cos^2 \theta + \sin^2 \theta = 1$$.

Another way to think about it is to embed the above triangle into a diagram for the unit circle where we see that $$\cos\theta$$ and $$\sin\theta$$ returns the x and y coordinates, respectively, of a point on the unit circle with angle $$\theta$$ to the $$x$$-axis:

![Unit Circle](/assets/images/UnitCircle.png)
{: style="text-align: center;"}

That explains the nature of the formula $$\cos^{2} \theta+\sin^{2} \theta=1$$. It comes from the equation of the unit circle $$x^2 + y^2 = 1$$.

Others trigonometric functions:

$$\begin{equation*} \tan=\displaystyle\frac{\sin}{\cos} \end{equation*} $$&nbsp;

$$\begin{equation*} \cot=\displaystyle\frac{\cos}{\sin} \end{equation*} $$, the reciprocal of $$\tan$$

$$\begin{equation*} \sec=\displaystyle\frac{1}{\cos} \end{equation*} $$, the reciprocal of the $$\cos$$

$$\begin{equation*} \csc=\displaystyle\frac{1}{\sin} \end{equation*} $$, the reciprocal of the $$\sin$$

All four of these have vertical asymptotes at the points where the denominator goes to zero.


### Inverse Trigonometrics

We often write $$\sin^{-1}$$ to denote the inverse, but this can cause confusion. Be careful that $$\sin^{-1}\neq\displaystyle\frac{1}{\sin}$$. To avoid the confusion, the terminology $$\arcsin$$ is recommended for the inverse of the $$\sin$$ function.

The $$\arcsin$$ function takes on values $$\left[-\displaystyle\frac{\pi}{2},\frac{\pi}{2}\right]$$ and has a restricted domain $$\left[-1,1\right]$$.

The $$\arccos$$ function likewise has a restricted domain $$\left[-1,1\right]$$, but it takes values $$\left[0,\pi\right]$$.

The $$\arctan$$ function has an unbounded domain, it is well defined for all inputs. But it has a restricted range $$\displaystyle\left ( -\frac{\pi}{2},\frac{\pi}{2} \right )$$.

### Exponentials

Exponential functions are of the form $$c^x$$, where $$c$$ is some positive constant. The most common such function, referred to as the exponential, is $$e^x$$. This is the most common because of its nice integral and differential properties (below).

Algebraic properties of the exponential function:

$$
\begin{equation*} \displaystyle e^{x}e^{y}=e^{x+y} \end{equation*}
$$

$$
\begin{equation*} \displaystyle (e^{x})^{y}=e^{xy} \end{equation*}
$$

Differential/integral properties:

$$
\begin{equation*} \displaystyle\frac{d}{dx} e^{x}=e^{x} \end{equation*}
$$

$$
\begin{equation*} \displaystyle\int e^{x}dx=e^{x}+C \end{equation*}
$$

Recall the graph of $$e^x$$, plotted here alongside its inverse, $$\ln x$$:

![Pythagorean identity visual proof](/assets/images/ExpLn.png)
{: style="text-align: center;"}

Note that the graphs are symmetric about the line $$y = x$$ (as is true of the graphs of a function and its inverse).

Before continuing, one might ask, what is $$e$$? There are several ways to define $$e$$, which will be revealed soon. For now, it is an irrational number which is approximately 2.718281828.


## Euler’s Formula

To close this lesson, we give a wonderful formula, which for now we will just take as a fact:

Euler's Formula
: $$
  \begin{equation*} e^{ix}=\cos x+i\sin x \end{equation*}
  $$
{: .theorem }

The $$i$$ in the exponent is the imaginary number $$\sqrt{-1}$$. It has the properties $$i^{2}=-1$$. $$i$$ is not a real number. That doesn't mean that it doesn't exist. It just means it is not on a real number line.

Euler's formula concerns the exponentiation of an imaginary variable. What exactly does that mean? How is this related to trigonometric functions? This will be covered in our next lesson.

## Additional Examples

**Example**

Find the domain of

$$
f(x) = \frac{1}{\sqrt{x^2 -3x+2}}.
$$

<button class="toggle" data-box="#boxe1">Answer</button>

<div id="boxe1" class="answer-hidden">
Note that the square root is only defined when its input is non-negative. Also, the denominator in a rational function cannot be 0. So we find that this function is well-defined if and only if $$x^2-3x+2 > 0$$. Factoring gives

$$
(x-2)(x-1) > 0.
$$

By plotting the points $$x=1$$ and $$x=2$$ (where the denominator equals 0) and testing points between them, one finds that $$x^2 - 3x+2>0$$ when $$x<1$$ or $$x>2$$:

![Line of testing points](/assets/images/PointChecking.png)
{: style="text-align: center;"}

So the domain of $$f$$ is $$x<1$$ or $$2<x$$. In interval notation, this is $$\left(-\infty,1\right) \cup \left(2, \infty \right)$$.
</div>

**Example**

Find the domain of

$$
f(x) = \ln(x^3-6x^2+8x).
$$
{: style="display: block;"}

<button class="toggle" data-box="#boxe2">Answer</button>

<div id="boxe2" class="answer-hidden">
Since $$\ln$$ is only defined on the positive real numbers, we must have $$x^3-6x^2+8x>0$$. Factoring gives

$$
x(x^2-6x+8) = x(x-2)(x-4)>0
$$

As in the above example, plotting the points where this equals 0 and then testing points, we find that the domain is $$0<x<2$$ and $$4<x$$. In interval notation, this is $$\left(0,2 \right) \cup \left(4,\infty\right)$$.
</div>

