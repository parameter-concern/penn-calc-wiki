---
title: Numerical integration
description: Using sequences to solve definite integrals
lecture_number: 49
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
The topic of this module is the discretization of the definite integral. How does one approximate the definite integral of a function which does not have an easily computable anti-derivative? The answer is with finite sums, which is the discrete analog of the definite integral.

Recall that one interpretation for the definite integral is area under the curve. The goal is to find a finite sum which approximates the area under the curve. There are three common techniques for making this approximation: Riemann sums, trapezoid rule, and Simpson's rule. Each gives an approximation of the integral $$\int_a^b f(x)dx$$.

Another way to think about this problem (and the practical applications) is to consider some sporadic sample points, thought of as a sequence

$$
x = (x_n) = (x_0,x_1,\ldots,x_n).
$$

Corresponding to these sample points is the sequence of function values

$$
f = (f_n) = (f_0,f_1,\ldots,f_n),
$$

where $$f_i = f(x_i)$$. The goal is to approximate the definite integral of the underlying function $$f$$ using these function values. Of course, in real world applications the function may not be continuous, let alone a familiar function with an easily computed anti-derivative. The method of numerical integration gives an approximation of the definite integral in this situation with imperfect information.

**Example**

Consider the problem of estimating the number of people who pass through a certain busy subway station each day. One could sit in the station for the entire day and count every person, or one could get an estimate by going in periodically and counting the number of people who come in over a short time.

This gives a sampling of the rate of passengers entering the station at different times:

The definite integral of the rate of passenger arrival gives the total number of passengers using the station that day:
Riemann Sums

The most rudimentary approximation is given by Riemann sums, which should be familiar from the definition of the definite integral.

The left Riemann sum uses the left endpoint of the $$i$$th subinterval as the sample point to compute the height of the the $$i$$th rectangle:

Thus, the area of the $$n$$th rectangle is. So the left Riemann sum is given by

$$
\begin{align*}
\int_a^b f(x)dx &\approx \sum_{n=0}^{N-1} f_n \cdot (x_{n+1}-x_n)
\end{align*}
$$

The right Riemann sum uses the right endpoint of the $$i$$th subinterval to compute the height of the $$i$$th rectangle:

In this case, the area of the $$n$$th rectangle is $$f_n \cdot (\nabla x)_n$$. So the right Riemann sum is given by

$$
\begin{align*}
\int_a^b f(x)dx &\approx \sum_{n=1}^N f_n \cdot (x_n-x_{n-1})
\end{align*}
$$

An improvement on the left and right Riemann sums, called the trapezoid rule, is given in the next section.
Trapezoid rule

The trapezoid rule uses trapezoids instead of rectangles to approximate the area above each subinterval:

Recall that the area of a trapezoid with bases (parallel segments) of length $$p$$ and $$q$$, with height $$h$$ has area $$\frac{1}{2}h(p+q)$$. The area of the $$n$$th trapezoid, then, is $$\frac{1}{2}(\Delta x)_n (f_n + f_{n+1})$$. Thus, the trapezoid rule gives the approximation:

$$
\begin{align*}
\int_a^b f(x) dx & \approx \sum_{n=0}^{N-1} \frac{1}{2}(\Delta x)_n (f_n + f_{n+1})
&\approx \sum_{n=0}^{N-1} \frac{1}{2} (f_n+f_{n+1}) (x_{n+1}-x_n).
\end{align*}
$$

If the sample points are evenly spaced uniformly, then the formula for the trapezoid rule simply becomes

$$
\begin{align*}
\int_a^b f(x) dx & \approx h \left(\frac{1}{2}(f_0+f_N)+\sum_{n=1}^{N-1} f_n \right),
\end{align*}
$$

where $$h = \frac{b-a}{N}$$ is the width of each trapezoid. Note that the trapezoid rule is the average of the left and right Riemann sums.
Simpson's rule

Think about how the previous approximations interpolate the function $$f$$. The Riemann sum is a piece-wise constant approximation (also called a step function). The trapezoid rule is a piece-wise linear approximation. The logical next step is to use piece-wise quadratic approximations. That is how Simpson's rule works. Another way to think of it is that Simpson's rule will compute the area under a parabola exactly (whereas Riemann sums and trapezoid rule will have errors in general).

One way that Simpson's rule differs from the above rules is that the sample points must be evenly spaced. Let $$h = \frac{b-a}{N}$$ be the distance between sample points. The Simpson's rule approximation is given by

$$
\begin{align*}
\int_a^b f(x)dx &\approx \frac{h}{3} \left(f_0+4f_1+2f_2+4f_3+\ldots + 2f_{N-2} + 4f_{N-1}+f_N \right).
\end{align*}
$$

Here, $$N$$ must be even.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}

Note

This derivation is a little bit different from the one in lecture, and perhaps more elementary.

The idea of Simpson's rule is to fit a parabola to the first three points $$(x_0,f_0)$$, $$(x_1, f_1)$$, $$(x_2, f_2)$$, and then find the area under that parabola. Then, fit a parabola to the next three points (overlapping the endpoints) $$(x_2,f_2)$$, $$(x_3,f_3)$$, $$(x_4,f_4)$$, find the area under that parabola, and so on.

Consider the parabola $$g(x) = ax^2+bx+c$$ determined by the points $$(-h,f_{n-1}),(0,f_n),(h,f_{n+1})$$. Solving the resulting system of equations

$$
\begin{align*}
f_{n-1} &= ah^2-bh+c
f_n &= c
f_{n+1} &= ah^2+bh+c,
\end{align*}
$$

gives the parabola which fits these points. One finds that

$$
\begin{align*}
a &= \frac{1}{h^2}\left(\frac{f_{n-1}}{2}-f_n + \frac{f_{n+1}}{2}\right) \\ b &= \frac{f_{n+1}-f_{n-1}}{2h}
c &= f_n.
\end{align*}
$$

And so the area

$$
\begin{align*}
\int_{x=-h}^h g(x)dx &= \int_{x=-h}^h ax^2+bx+c dx
&= a \frac{x^3}{3} + b \frac{x^2}{2} + cx \bigg\vert_{x=-h}^h
&= 2a \frac{h^3}{3} + 2ch,
\end{align*}
$$

by using symmetry. Plugging in the earlier values for $$a$$ and $$c$$ and simplifying gives

$$
\int_{x=-h}^h g(x)dx = \frac{h}{3} \left(f_{n-1} + 4f_n + f_{n+1} \right).
$$

Carrying this out for all each triplet of points gives the approximation

$$
\begin{align*}
\int_{x=a}^b f(x)dx &\approx \frac{h}{3} \left(f_0 + 4f_1+f_2 + f_2 + 4f_3+f_4+\dotsb + f_N\right)
&\approx \frac{h}{3} \left(f_0 + 4f_1 + 2f_2 + 4f_3+\dotsb + f_N\right),
\end{align*}
$$

as desired.
**Example**

Approximate the definite integral $$\int_0^2 x^3 dx$$ with $$N=4$$ using (uniformly spaced) right and left Riemann sums; trapezoid rule; and Simpson's rule. Here is a table of pertinent values to make the computation easier:
$$n$$	$$x_n$$	$$f_n$$
0	0	0
1	$$.5$$	$$.125$$
2	1	1
3	$$1.5$$	$$3.375$$
4	2	8

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Let $$L$$, $$R$$, $$T$$, and $$S$$ be the respective approximations. Then

$$
\begin{align*}
L &= \frac{1}{2} \left( 0 + .125 + 1 + 3.375 \right) = 2.25
R &= \frac{1}{2} \left( .125 + 1 + 3.375 + 8 \right) = 6.25
T &= \frac{1}{2} \left( 0 + .125 + 1 +3.375 + 4 \right) = 4.25
S &= \frac{1}{6} \left( 0 + .5 + 2 + 13.5 + 8 \right) = 4.
\end{align*}
$$

Note that the true value is

$$
\int_{x=0}^2 x^3 \, dx = \frac{1}{4} x^4 \bigg\vert_{x=0}^2 = 4,
$$

so Simpson's rule gets the answer exactly and the trapezoid rule is the next closest.
Errors bounds

With any approximation, it is good to get some idea of how far off the approximation is from the true value. Let $$E_T$$ be the error using the trapezoidal rule, and $$E_S$$ be the error from using Simpson's rule.

Using advanced calculus beyond the scope of this course, one can bound these errors as follows.

$$
\begin{equation*} E_T \leq \frac{M(b-a)^3}{12N^2} \end{equation*}
$$

where $$M$$ is the maximum value of $$\vertf''(x)\vert$$ on the interval $$\left[a,b\right]$$.

$$
\begin{equation*} E_S \leq \frac{M(b-a)^5}{180N^4} \end{equation*}
$$

where $$M$$ is the maximum value of $$\vertf^{\left(4\right)}(x)\vert$$ on the interval $$\left[a,b\right]$$.

## Exercises

- Using the fact that $$\sum_{n=0}^j n^2 = \frac{j (j+1)(2j+1)}{6} $$, approximate $$ \int_0^2 x^2 dx $$ using the right Riemann sum with $$N$$ number of intervals. 