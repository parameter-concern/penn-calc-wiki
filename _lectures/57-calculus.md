---
title: Calculus
description: What we can and cannot do...for now
lecture_number: 57
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
In this course, we've learned skills in five key areas:

- Limits
- Differentiation
- Integration
- ODEs
- Series 

Some of the things we can do are pretty impressive. However, there are many simple-seeming questions in single-variable calculus that show us just how much we have left to learn.
PROBLEM 1

Why is the standard Gaussian a probability density function? In other words, why is

$$
\begin{equation} \int_{-\infty}^{\infty} e^{-\frac{x^2}{2}} dx = \sqrt{2\pi} \end{equation}
$$

Why is it that with all our methods, we cannot evaluate this integral easily? Let's try...
MORAL

This integral is easy with a little bit of multivariable calculus.
PROBLEM 2

Recall that we began this class with the definition of the exponential function $$ e^x $$ and then, to obtain series for $$ \sin $$ and $$ \cos $$, we invoked Euler's formula:

$$
e^{it} = \cos t + i \sin t
$$

Why is this true? We certainly could substitute in our favorite Taylor series and verify that it is true, but wouldn't it be better to have a principled reason for why this is so? Let's try...

Let $$z = e^{it}$$. Then $$z' = i z$$ by that very familiar differential equation. Now, name the real and imaginary parts of $$z$$ by $$x$$ and $$y$$ respectively. Then $$z= x+iy$$, and $$z' = x' + iy'$$. On the other hand, multiplying by $$i$$ gives

$$
\begin{align*}
z &= x + i y
iz &= ix + i^2 y = -y + ix.
\end{align*}
$$

Therefore, $$z' = iz$$ becomes $$x'+iy' = -y + ix$$, and so by equating the real and imaginary parts in this equation we get the system

$$
\begin{align*}
x' &= -y
y' &= x
\end{align*}
$$

This is a system of differential equations which is easy to solve with some multivariable calculus, but for now we are stuck. We can observe that $$x = \cos t$$ and $$y = \sin t$$ provides a solution, but we cannot say it is the only solution without more tools.
MORAL

This system of ODEs is easy to solve with a little bit of multivariable calculus.
PROBLEM 3

On several occasions, we have referenced the famous series

$$
\sum_{n=1}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}
$$

Why is this true? Could we use discrete calculus to derive it? I don't think so...but here is proof using Taylor series and integration.

Let $$u = \arcsin(x)$$. Consider the integral

$$
\int_{u=0}^{\pi/2} u du = \frac{u^2}{2} \bigg\vert_{u=0}^{\pi/2} = \frac{\pi^2}{8}.
$$

On the other hand, the integral in terms of $$x$$ is

$$
\int_{x=0}^1 \arcsin(x) \frac{1}{\sqrt{1-x^2}} dx
$$

One can show that the Taylor series for $$\arcsin(x)$$ is given by

$$
\arcsin(x) = x + \sum_{n=1}^\infty \frac{1 \cdot 3 \cdot 5 \dotsb (2n-1)}{2 \cdot 4 \cdot 6 \dotsb (2n)} \frac{x^{2n+1}}{2n+1}.
$$

Plugging this in gives

$$
\frac{\pi^2}{8} = \int_{x=0}^1 \left(x + \sum_{n=1}^\infty \frac{1 \cdot 3 \cdot 5 \dotsb (2n-1)}{2 \cdot 4 \cdot 6 \dotsb (2n)} \frac{x^{2n+1}}{2n+1}\right) \frac{1}{\sqrt{1-x^2}} dx.
$$

One can find with careful integration by parts and induction that the inner integral evaluates to

$$
\int_{x=0}^1 \frac{x^{2n+1}}{\sqrt{1-x^2}}dx = \frac{2 \cdot 4 \cdot 6 \dotsb (2n)}{3 \cdot 5 \cdot 7 \dotsb (2n+1)},
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


If we encountered this integral earlier in the course, we would hit it with a trigonometric substitution $$x = \sin \theta$$ (and $$dx = \cos \theta \, d\theta$$, which changes the integral to

$$
\int_{\theta = 0}^{\pi/2} \sin^{2n+1} \theta \, d\theta.
$$

This integral can be found inductively using the following reduction formula:

$$
\int \sin^n \theta \, d\theta = \frac{-\sin^{n-1} \theta \cos \theta}{n} + \frac{n-1}{n} \int \sin^{n-2} \theta \, d\theta.
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Use integration by parts. Let $$u = \sin^{n-1}\theta$$ and $$dv = \sin \theta \, d\theta$$. Then $$du = (n-1)\sin^{n-2}\theta \cos \theta \, d\theta$$ and $$v = -\cos \theta$$. It follows that

$$
\begin{align*}
\int \sin^n \theta \, d\theta &= -\sin^{n-1}\theta \cos \theta + (n-1) \int \sin^{n-2}\theta \cos^2 \theta \, d\theta
&= -\sin^{n-1}\theta \cos \theta + (n-1) \int \sin^{n-2}\theta (1-\sin^2 \theta) \, d\theta
&= -\sin^{n-1} \theta \cos \theta + (n-1) \int \sin^{n-2}\theta \, d\theta - (n-1)\int \sin^n \theta \, d\theta.
\end{align*}
$$

Now, solving for the integral $$\int \sin^n \theta \, d\theta$$ (by adding $$(n-1) \int \sin^n \theta \, d\theta$$ to both sides of the above equation and dividing by $$n$$) gives the desired result.

Applying the reduction formula in the situation at hand gives

$$
\begin{align*}
\int_0^{\pi/2} \sin^{2n+1} \theta \, d\theta &= \frac{-\sin^{2n}\theta \cos \theta}{2n+1} \bigg\vert_0^{\pi/2} + \frac{2n}{2n+1} \int_0^{\pi/2} \sin^{2n-1}\theta \, d\theta
&= \frac{2n}{2n+1} \int_0^{\pi/2} \sin^{2n-1} \theta \, d\theta,
\end{align*}
$$

since the first quantity evaluates to 0. Now, induction gives the result.

Plugging this in cancels almost everything, leaving

$$
\frac{\pi^2}{8} = \sum_{n=1}^\infty \frac{1}{(2n-1)^2}.
$$

This is the sum of the odd reciprocals squared. Giving names to these various sums:

$$
\begin{align*}
S &= \sum_{n=1}^\infty \frac{1}{n^2}
S_o &= \sum_{n=1}^\infty \frac{1}{(2n-1)^2}
S_e &= \sum_{n=1}^\infty \frac{1}{(2n)^2}.
\end{align*}
$$

Note that $$S = S_o + S_e$$ ($$S_o$$ has the odd terms, and $$S_e$$ has the even terms). Further,

$$
\begin{align*}
S_e &= \sum_{n=1}^\infty \frac{1}{(2n)^2}
&= \frac{1}{4} \sum_{n=1}^\infty \frac{1}{n^2}
&= \frac{1}{4} S.
\end{align*}
$$

Substituting, we find that $$S = S_o + S/4$$, and so $$S = \frac{4}{3}S_o$$. Since $$S_o = \frac{\pi^2}{8}$$ as shown above, it follows that $$S = \frac{\pi^2}{6}$$, as desired.
MORAL

This series is easy to evaluate with a little bit of multivariable calculus. Well, actually, no: it's not easy, but it is a bit simpler. In the end, some math problems are hard. 