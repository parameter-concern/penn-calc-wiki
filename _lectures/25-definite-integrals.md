---
title: Definite integrals
description: Definition and interpretation of the definite integral
lecture_number: 25
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
This module moves from the indefinite integral, which is a class of functions, to the definite integral, which is a number. The relationship between these seemingly unrelated topics will be revealed in the next module.

The idea underlying the definite integral is that adding up local increments leads to a global total. Before getting into the details of what this means, consider a simple example.

**Example**

Consider

$$
\sum_{i=1}^n i = 1 + 2 +3 + \dotsb + n.
$$

One can visualize this sum as the area of a triangular stack of $$1\times 1$$ boxes. The first column has 1 box, the second column has 2 boxes, and so on through the nth column with n boxes:

The area of this roughly triangular region can be found by splitting it into two regions: a right triangle of base and height $$n$$, and the half boxes left over:

The total area is therefore $$\frac{1}{2}n(n+1)$$, and so we find that

$$
\sum_{i=1}^n i = \frac{1}{2}n(n+1).
$$

The point of this example is to compare the amount of computation (e.g. the number of additions) required to do the sum using local information (adding up the terms one by one), verses the global information (evaluating the product on the right above). It is much easier to simply evaluate the product.

The definite integral takes this type of idea and generalizes it to more difficult sums. Before we can define it, we need a few definitions.
Partitions and Riemann sums

Given an interval $$\left[a,b\right]$$, a partition $$P$$ of $$\left[a,b\right]$$ is a division of the interval $$\left[a,b\right]$$ into subintervals $$P_i$$. Visually, think of placing hash marks along the interval $$\left[a,b\right]$$ and then labeling the subintervals $$P_1,P_2,\ldots$$ from left to right:

Let $$(\Delta x)_i$$ be the width of the ith subinterval, $$P_i$$.

Choose a sample point $$x_i$$ from the ith subinterval (this can be a point chosen at random from the subinterval or systematically; it does not matter).

Given a function $$f$$, a partition $$P$$ for an interval $$\left[a,b\right]$$, and sample points $$x_i$$, the Riemann sum of $$f$$ on $$P$$ is given by

$$
\begin{equation*} \sum_{i=1}^N f(x_i) (\Delta x)_i. \end{equation*}
$$

The Riemann sum can be interpreted as an approximation of the area under the curve of $$f$$ from $$a$$ to $$b$$ using rectangles. The width and height of the $$i$$th rectangle are $$(\Delta x)_i$$ and $$f(x_i)$$, respectively. Note that in this area interpretation, a rectangle which is below the x-axis has negative area (since $$f(x_i)<0$$ in this case). For an example with $$N = 4$$ rectangles, consider the following figure:
The definite integral

The definite integral

The definite integral of a function $$f$$ from $$a$$ to $$b$$, denoted

$$
\int_{x=a}^b f(x)\,dx,
$$

is defined by

$$
\int_{x=a}^b f(x)\, dx = \lim_{\Delta x \rightarrow 0} \sum_{i=1}^N f(x_i)(\Delta x)_i.
$$

The function $$f$$ being integrated is called the integrand.

In other words, the definite integral is the limit of the Riemann sums as the lengths of the subintervals approach 0. In the area interpretation, the widths of all the rectangles are getting arbitrarily small, which ultimately gives the area under the curve:

Remember that when interpreting the definite integral as the area under the curve, any region which is below the x-axis contributes negative area to the total.

Example Using the definition of the definite integral, compute

$$
\int_{x=0}^1 x\, dx.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Let the partition $$P$$ divide the interval $$\left[0,1\right]$$ into $$N$$ equally sized subintervals. Then the ith subinterval of $$P$$ is given by $$ [(i-1)\frac{1}{N},i\frac{1}{N}] $$, and $$(\Delta x)_i = \frac{1}{N}$$. Choose the right endpoint of each subinterval to be its sample point, i.e. $$x_i= \frac{i}{N}$$. Finally, note that as $$N \rightarrow \infty$$, $$\Delta x \rightarrow 0$$. It follows that

$$
\begin{align*}
\int_0^1 x\,dx &= \lim_{\Delta x \rightarrow 0} \sum_{i=1}^N f(x_i)(\Delta x)_i
&= \lim_{N \rightarrow \infty} \sum_{i=1}^N \frac{i}{N} \cdot \frac{1}{N}
&= \lim_{N \rightarrow \infty} \frac{1}{N^2} \sum_{i=1}^N i
&= \lim_{N \rightarrow \infty} \frac{1}{N^2} \frac{N(N+1)}{2}
&= \lim_{N \rightarrow \infty} \frac{N^2+N}{2N^2}
&= \frac{1}{2}.
\end{align*}
$$

We used the fact from earlier that

$$
\sum_{i=1}^n i = \frac{1}{2}n(n+1)
$$

Notation

Sums The integral sign $$\int$$ and the summation sign $$\sum$$ are both short for sum. The integral sign $$\int$$ looks like a stylized S, and the summation sign is the Greek sigma, short for sum.

Limits Including the variable in the limits of integration is not strictly necessary, but is a useful habit to develop for future courses where integration will be happening with respect to several variables. It is also fine to suppress the notation and just have $$\int_a^b f(x) \, dx$$:

$$
\int_a^b f(x) \, dx = \int_{x=a}^b f(x) \, dx.
$$

Variables The variable used in the integrand does not matter; it is sometimes referred to as a dummy variable:

$$
\int_{x=a}^b f(x) \, dx = \int_{t=a}^b f(t) \, dt = \int_{z = a}^b f(z) \, dz.
$$

However, if there is a variable used in one of the limits of integration (as will happen from time to time), it is important to avoid using that as the dummy variable too. For example,

$$
\int_a^x f(t) \, dt \quad \hbox{instead of} \quad \int_a^x f(x) \, dx.
$$

Caveat

Note that, although their notation is similar, definite integrals are not the same as indefinite integrals! The indefinite integral of a function is a class of functions, whereas the definite integral of a function over an interval is a number.

That said, it is no accident that they have similar notations, because of their relationship, which is given by the Fundamental Theorem of Integral Calculus in the next module.
Properties of definite integrals
Linearity

The definite integral is linear, i.e.

$$
\begin{align*}
\int_{x=a}^b \left(f(x) + g(x)\right) \, dx &= \int_{x=a}^b f(x) \, dx + \int_{x=a}^b g(x) \, dx.
\int_{x=a}^b c \cdot f(x) \, dx &= c \int_{x=a}^b f(x)\, dx.
\end{align*}
$$

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


The definite integral is defined as the limit of Riemann sums. Note that for any partition $$P$$ of the interval,

$$
\begin{align*}
\sum_{i=1}^N (f+g)(x_i)(\Delta x)_i &= \sum_{i=1}^N \left[f(x_i)+g(x_i)\right](\Delta x)_i
&= \sum_{i=1}^N f(x_i)(\Delta x)_i + g(x_i)(\Delta x)_i
&= \sum_{i=1}^N f(x_i)(\Delta x)_i + \sum_{i=1}^N g(x_i)(\Delta x)_i,
\end{align*}
$$

because of linearity of finite sums. Therefore, as one takes the limit as $$\Delta x \rightarrow 0$$, one finds (by the linearity of limits) that

$$
\int_a^b (f(x) + g(x))\, dx = \int_a^b f(x) \, dx + \int_a^b g(x) \, dx.
$$

The argument for a constant multiple is almost identical: we can pull a constant out from a sum, and pull a constant out from a limit.
Additivity

When integrating the same function over two adjacent intervals, we have additivity:

$$
\int_a^b f(x) \, dx + \int_b^c f(x) \, dx = \int_a^c f(x) \, dx.
$$

In the area interpretation, this can be thought of as taking the area under the curve from $$a$$ to $$b$$ and adding the area under the curve from $$b$$ to $$c$$, which gives the area under the curve from $$a$$ to $$c$$:

Another way of thinking about it is adding the intervals $$\left[a,b\right]$$ and $$\left[b,c\right]$$ together to get $$\left[a,c\right]$$. It is important to note that the orientation of the interval matters, as discussed in the next subsection.
Orientation

The orientation of the interval over which we integrate matters. Integrating from left to right is positive, and integrating from right to left is negative:

$$
\int_a^b f(x) \, dx = -\int_{b}^a f(x) \, dx.
$$

<button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


Consider what happens if one computes

$$
\int_a^b f(x) \, dx + \int_b^a f(x) \, dx.
$$

By the additivity property (where $$c$$ has been replaced by $$a$$), this is

$$
\int_a^a f(x) \, dx.
$$

But this equals 0, which is intuitive in the area interpretation. (More formally, any partition of an interval with 0 width has subintervals of 0 width, so the Riemann sums equal 0). Therefore,

$$
\int_a^b f(x) \, dx + \int_b^a f(x) \, dx = 0,
$$

and rearranging gives

$$
\int_a^b f(x) \, dx = -\int_b^a f(x) \, dx,
$$

as desired.
Dominance

This is another intuitive property. If $$f(x) \geq 0$$ for all $$x$$ in the interval $$\left[a,b\right]$$, then

$$
\int_a^b f(x) \, dx \geq 0.
$$

Also, if $$f(x) \geq g(x)$$ for all $$x$$ in the interval, then

$$
\int_a^b f(x) \, dx \geq \int_a^b g(x) \, dx
$$

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


For the first part, note that regardless of the partition of $$\left[a,b\right]$$, the Riemann sum

$$
\sum_{i=1}^N f(x_i) (\Delta x)_i \geq 0,
$$

because $$f(x_i) \geq 0$$ by the above assumption. Since each Riemann sum is non-negative, the limit is non-negative.

For the second part, note that

$$
f(x) \geq g(x) \Longrightarrow f(x)-g(x) \geq 0.
$$

So applying the first part, we have

$$
\int_a^b \left( f(x)-g(x) \right) \, dx \geq 0.
$$

Then by linearity of the definite integral (above),

$$
\int_a^b f(x) \, dx - \int_a^b g(x) \, dx \geq 0,
$$

and rearranging gives

$$
\int_a^b f(x) \, dx \geq \int_a^b g(x) \, dx.
$$

More examples

There are a few definite integrals that we can compute directly from the definition. But for most functions, it is not easy to work directly with the definition.

**Example**

Compute

$$
\int_a^b c \, dx
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


If we use the partition of $$\left[a,b\right]$$ into $$n$$ equal intervals, then

$$
\left(\Delta x\right)_i = \frac{b-a}{n}
$$

Also, note that $$f(x_i) = c$$ for all $$i$$. So

$$
\begin{align*}
\int_a^b c \, dx &= \lim_{\Delta x \rightarrow 0} \sum_{i=1}^n c \frac{b-a}{n}
&= \lim_{\Delta x \rightarrow 0} c \cdot n \cdot \frac{b-a}{n}
&= c \cdot (b-a).
\end{align*}
$$

We could also see this by interpreting this definite integral as the area under the curve $$y=c$$ between $$x=a$$ and $$x=b$$, which is simply a rectangle of base $$b-a$$ and height $$c$$.

**Example**

Compute

$$
\int_a^b x \, dx
$$

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Again using a partition into $$n$$ equal sized subintervals, we have that $$(\Delta x)_i = \frac{b-a}{n}$$. If we take our sample point to be the right endpoint of each subinterval, then we have $$x_i = a + \frac{b-a}{n}i$$. So

$$
\begin{align*}
\int_{x=a}^b x \, dx &= \lim_{n \rightarrow \infty} \sum_{i=1}^n \left(a+\frac{b-a}{n}i\right)\frac{b-a}{n}
&= \lim_{n \rightarrow \infty} \sum_{i=1}^n a \frac{b-a}{n} + \sum_{i=1}^n i \left(\frac{b-a}{n}\right)^2
&= \lim_{n \rightarrow \infty} n \cdot a \frac{b-a}{n} + \left(\frac{b-a}{n}\right)^2 \frac{n(n+1)}{2}
&= a(b-a) + \frac{(b-a)^2}{2}
&= \frac{2ab - 2a^2 + b^2-2ab+a^2}{2}
&= \frac{1}{2}(b^2-a^2).
\end{align*}
$$

This can also be found by interpreting the definite integral as the area under the curve $$y=x$$, which can be broken into a rectangle with base $$b-a$$ and height $$a$$ and a triangle with base and height $$b-a$$:
Odd and even functions

There are a few final cases where certain definite integrals can be simplified by using properties of the integrand.

Odd and even functions

A function $$f(x)$$ is called odd if

$$
f(-x) = -f(x).
$$

A function $$g(x)$$ is called even if

$$
g(-x) = g(x).
$$

The reason for the terminology comes from Taylor series. A function is odd if and only if every term in its Taylor series has odd power. Similarly, a function is even if and only if every term in its Taylor series has even power.

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


If $$f$$ only has odd powers in its Taylor series, then

$$
f(x) = a_1x + a_3x^3 + a_5x^5 + \dotsb
$$

for some constants $$a_1,a_3,\dotsb$$. So evaluating $$f(-x)$$ and doing a little algebra, we find

$$
\begin{align*}
f(-x) &= a_1(-x) + a_3(-x)^3 + a_5(-x)^5 + \dotsb
&= -a_1x -a_3x^3 - a_5x^5 - \dotsb
&= -\left(a_1 x +a_3x^3+ a_5x^5+\dotsb \right)
&= -f(x),
\end{align*}
$$

as desired. Similarly, if $$g(x)$$ has even powers, then

$$
g(x) = a_0 + a_2x^2 + a_4x^4 + \dotsb
$$

and it follows that

$$
\begin{align*}
g(-x) &= a_0 + a_2(-x)^2 + a_4(-x)^4 + \dotsb
&= a_0 + a_2 x^2 + a_4x^4 + \dotsb
&= g(x),
\end{align*}
$$

as desired.

**Example**

Sine and hyperbolic sine are both odd functions because they only have odd powers in their Taylor series.

Cosine and hyperbolic cosine are both even functions because they only have even powers in their Taylor series.
Odd function over a symmetric domain

If an odd function $$f$$ is integrated over a domain that is symmetric about the origin (i.e., an interval of the form $$\left[-L,L\right]$$, then

$$
\int_{x=-L}^L f(x) \, dx = 0.
$$

Formally, any subinterval's on the left half of the interval will make a contribution to the Riemann sum which is equal and opposite to the contribution of the corresponding subinterval on the right half of the interval. These equal and opposite sums cancel, and so the definite integral over the entire interval is 0.

In terms of the area interpretation, the net area under the curve over the left half of the interval will be equal and opposite in sign to the net area under the curve over the right half of the interval. Therefore, the total area will be 0:
Even function over a symmetric domain.

If an even function $$g$$ is integrated over a domain that is symmetric about the origin (i.e., an interval of the form $$\left[-L,L\right]$$), then

$$
\int_{x=-L}^L g(x) \, dx = 2 \int_{x=0}^L g(x) \, dx.
$$

Formally, each subinterval on the left half of the interval has a corresponding subinterval on the right with an equal contribution to the Riemann sum. So one can just take the Riemann sum on the right and double it.

Using the area interpretation, one can see that the region under the curve on the left will be the mirror image of the region under the curve on the right, so the total area is just twice the area on the right:

## Exercises

- One particular choice of partition and sampling that can be used to numerically evaluate definite integrals is the following. With $$n$$ fixed, divide the interval (a, b$$ into $$n$$ subintervals $$P_i$$ of common length $$ (\Delta x)_i = (b-a)/n $$. For the sampling, choose the right endpoint of each $$P_i$$; this gives you the formula: 

$$ \displaystyle x_i = a + i \frac{b-a}{n} $$
With these choices of partition and sampling, compute the Riemann sums for the integral
$$ \displaystyle \int_{x=1}^2 \frac{dx}{x} $$
for $$n=1, 2, 3$$ subdivisions. Note: in the next Lecture we will learn that
$$ \displaystyle \int_{x=1}^2 \frac{dx}{x} = \ln 2 \simeq 0.693 $$

How does this compare to the values you obtained from the Riemann sums?

- With the same choices of partition and sampling as in the previous problem, evaluate the Riemann sum for the integral 

$$ \displaystyle \int_{x=0}^3 x^2 \, dx $$
for an arbitrary number $$n$$ of subdivisions. You may need to use the following:
$$ \displaystyle \sum_{i=1}^n i = \frac{n(n+1)}{2}, \quad \sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6}, \quad \sum_{i=1}^n i^3 = \frac{n^2(n+1)^2}{4} $$

- The line $$y=x$$, the $$x$$-axis and the vertical line $$x=2$$ bound a triangle of area $$2$$. Thus, 

$$ \displaystyle I = \int_{x=0}^2 x \, dx = 2 $$
Evaluating the Riemann sum for $$n$$ subdivisions for the above integral with the same choices of partition and sampling as in the previous problem yields an approximation $$RS(n)$$ for its value $$I$$. The error $$E(n)$$ we commit by using this approximation is defined to be the difference
$$ E(n) = RS(n) - I $$
Show that $$ E(n) $$ is in $$O(n^{-k})$$ for some $$k>0$$. What's the best value of $$k$$?

- What is the following integral? Think! 

$$ \displaystyle \int_{x=-\pi/4}^{\pi/4} \left( x^2 + \ln\vert\cos x\vert\right) \sin \frac{x}{2} \, dx $$

- Using the definition of definite integrals, compute $$\displaystyle x^3 \, dx $$. Use a uniform partition and the fact that $$ \sum_{i=1}^n i^3 = \frac{n^2(n+1)^2}{4} $$. 