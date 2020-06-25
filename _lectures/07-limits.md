---
title: Limits
description: Definition of limit and continuity
lecture_number: 7
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
{::options parse_block_html="true" /}
Having concluded our study of Taylor series, we now move on to limits. Some of the major topics of calculus (continuity, differentiation, and integration) can all be expressed using limits.

## Definition of the limit

The limit formalizes the behavior of a function as its input approaches some value. The formal definition of the limit is

Limit
: $$\displaystyle \lim_{x \rightarrow a} f(x) = L$$ if and only if for every $$\epsilon>0$$ there exists $$\delta > 0$$ such that $$\vert f(x)  -L \vert < \epsilon$$ whenever $$0 < \vert x - a \vert < \delta$$. If there is no such $$L$$, then the limit does not exist.
{: .mathterm .definition }

In words, this says that the limit of a function exists if, when the input to $$f$$ is very close to $$a$$ (but not equal to $$a$$), the output from $$f$$ is very close to $$L$$. This can also be thought of in terms of tolerances: given a certain $$\epsilon$$ tolerance for the output (seen as the band around $$L$$ in the graph below), one can find a tolerance $$\delta$$ on the input (the band around $$a$$$ so that for inputs within the tolerance, the corresponding outputs stays within $$\epsilon$$ of the desired output:

![Limit]({{ site.baseurl }}/assets/images/Limit.png)
{: .mathimg }

No matter how small $$\epsilon$$ is made, there must be some $$\delta$$, which must depend on $$\epsilon$$, generally. Actually finding $$\delta$$ often requires a little bit of work.

**Example** Using the definition of the limit, show that $$ \displaystyle \lim_{x \rightarrow 3} x^2 = 9$$. <button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden">
**Note** This is rather technical, and is only a demonstration of the process required to prove a limit exists from the definition. This course deals almost exclusively with continuous functions, where such proofs are not necessary.

We must show that for any given $$\epsilon>0$$, there exists $$\delta$$ (which depends on $$\epsilon$$) such that $$0<\vert x-3\vert <\delta$$ implies $$\vert x^2-9 \vert <\epsilon$$.

Let $$\epsilon>0$$ be given. A little bit of algebra shows that

$$
\vert x^2-9 \vert = \vert x-3 \vert \cdot \vert x+3 \vert.
$$

We get to control $$\vert x-3 \vert $$ with $$\delta$$. We also have (by using the triangle inequality) that

$$
\vert x+3 \vert = \vert x-3+6 \vert \leq \vert x-3\vert +6 < \delta + 6.
$$

Thus,

$$
\vert x^2-9\vert = \vert x-3\vert\cdot \vert x+3\vert < \delta \cdot (\delta + 6).
$$

Now, if we pick $$\delta$$ to be the minimum of $$1$$ and $$\frac{\epsilon}{7}$$, then we simultaneously guarantee that $$\delta \leq \frac{\epsilon}{7}$$ and $$\delta + 6 \leq 7$$, and so we find

$$
\vert x^2-9\vert < \delta \cdot (\delta + 6) \leq \frac{\epsilon}{7} \cdot 7 = \epsilon,
$$

as desired.
</div>

## When limits may not exist

There are a few ways a limit might not exist:

- A *discontinuity*, or jump, in the graph of the function. In this case, the limit does not exist because the limit from the left and the limit from the right are not equal.
- A *blow-up*, when the function has a vertical asymptote.
- An *oscillation*, where the graph of the function oscillates infinitely up and down as the input approaches a certain value.

![LimitFails]({{ site.baseurl }}/assets/images/LimitFails.png)
{: .mathimg }

Most functions in this course will be well-behaved and will not have the above problems. The formal term for a well-behaved function is *continuous*.

## Continuous functions

A function is *continuous at* the point $$a$$ if the limit $$\lim_{x \rightarrow a} f(x)$$ exists and $$\lim_{x \rightarrow a} f(x) = f(a)$$. Intuitively, this says that there are no holes or jumps in the graph of $$f$$ at $$a$$.

Finally, a function is *continuous* if it is continuous at every point in its domain.

## Rules for limits

There are rules for adding, multiplying, dividing, and composing limits. Suppose that $$\displaystyle \lim_{x \rightarrow a} f(x)$$ and $$\displaystyle \lim_{x \rightarrow a} g(x)$$ exist. Then

1.  (Sum) $$\displaystyle \lim_{x \rightarrow a} (f+g)(x) = \lim_{x \rightarrow a} f(x) + \lim_{x \rightarrow a} g(x)$$.
2.  (Product) $$\displaystyle \lim_{x \rightarrow a} (f \cdot g)(x) = \left(\lim_{x \rightarrow a}f(x)\right)\left(\lim_{x \rightarrow a} g(x)\right)$$.
3.  (Quotient) $$\displaystyle \lim_{x \rightarrow a} \left(\frac{f}{g}\right)(x) = \frac{\lim_{x \rightarrow a} f(x)}{\lim_{x \rightarrow a} g(x)}$$, provided that $$\displaystyle \lim_{x \rightarrow a} g(x) \neq 0$$.
4.  (Chain) $$\displaystyle \lim_{x \rightarrow a} (f \circ g)(x) = f\left(\lim_{x \rightarrow a} g(x)\right)$$, if $$f$$ is continuous.

Almost all the functions encountered in this course are continuous, and so limits in most cases can be evaluated by simply plugging in the limiting input value into the function. The one case that sometimes gets complicated is the Quotient rule above when the limit of the denominator is 0.

**Example** Show that $$\displaystyle \lim_{x\rightarrow 0}\frac{\sin(x)}{x} = 1$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden">
There are several proofs of this limit (e.g. memorization, l'Hospital's rule), but the simplest method is to use the Taylor series. Because $$x$$ is near 0, the Taylor series expansion for $$\sin x$$ applies, and so

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{\sin(x)}{x} &= \lim_{x\rightarrow 0} \frac{x-\frac{x^3}{3!}+\dotsb}{x} \\
&= \lim_{x\rightarrow 0} \frac{x \left(1-\frac{x^2}{3!}+\dotsb\right)}{x} \\
&= \lim_{x\rightarrow 0} 1-\frac{x^2}{3!} +\dotsb \\
&= 1.
\end{align*}
$$

This works because all the terms involving $$x$$ go to 0 as $$x$$ goes to 0.
</div>

**Example** Find $$\displaystyle \lim_{x\rightarrow 0} \frac{1-\cos x}{x}$$. <button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden">
Replacing $$\cos$$ with its Taylor series (again, since $$x$$ is near 0), we find

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{1-\cos x}{x} &= \lim_{x \rightarrow 0} \frac{1-\left(1-\frac{1}{2!}x^2 + \frac{1}{4!}x^4 - \dotsb \right)}{x} \\
&= \lim_{x \rightarrow 0} \frac{\frac{1}{2!}x^2 - \frac{1}{4!}x^4 + \dotsb}{x} \\
&= \lim_{x \rightarrow 0} \frac{1}{2!}x - \frac{1}{4!}x^3 + \dotsb \\
&= 0.
\end{align*}
$$

</div>

**Example** Compute $$\displaystyle \lim_{x\rightarrow 0} \frac{\cos(x)-\sin(x)-1}{e^x-1}$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden">
Again, use the Taylor series (about $$x=0$$) for each function:

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{\cos(x)-\sin(x)-1}{e^x-1}
&= \lim_{x \rightarrow 0} \frac{(1-\frac{x^2}{2!}+\dotsb)-(x-\frac{x^3}{3!}+\dotsb)-1}{(1+x+\frac{x^2}{2!}+\dotsb)-1} \\
&= \lim_{x\rightarrow 0}\frac{-x-\frac{x^2}{2!}+\dotsb}{x+\dotsb} \\
&= \lim_{x \rightarrow 0} \frac{x(-1-\dotsb)}{x(1+\dotsb)} \\
&= \lim_{x \rightarrow 0} \frac{-1-\dotsb}{1+\dotsb} \\
&= -1.
\end{align*}
$$

</div>

**Example** Compute $$\displaystyle \lim_{x \rightarrow 0} \frac{\sqrt[3]{1+4x} - 1}{\sqrt[5]{1+3x} - 1}$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden">
Here, we use the binomial series with $$\alpha = \frac{1}{3}$$ in the numerator, and $$\alpha = \frac{1}{5}$$ in the denominator. We find

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{(1+4x)^{1/3}- 1}{(1+3x)^{1/5} - 1} &= \lim_{x \rightarrow 0} \frac{\left(1+\frac{1}{3}(4x) + \hbox{ HOT}\right)-1}{\left(1+\frac{1}{5}(3x) + \hbox{ HOT}\right) - 1} \\
&= \lim_{x \rightarrow 0} \frac{\frac{4}{3}x + \hbox{ HOT}}{\frac{3}{5}x + \hbox{ HOT}} \\
&= \lim_{x \rightarrow 0} \frac{\frac{4}{3} + \hbox{ HOT}}{\frac{3}{5} + \hbox{ HOT}} \\
&= \frac{\frac{4}{3}}{\frac{3}{5}} \\
& = \frac{20}{9}
\end{align*}
$$

</div>

There are other methods for computing these types of limits, including memorization, algebraic tricks, and l'Hopital's rule (more on that in the next module). However, in many cases, these different methods can all be replaced by a simple application of Taylor series.

## Exercises

Compute the following limits:

$$
\begin{multline}
\shoveleft
\begin{aligned}
1. \quad & \lim_{q \to 1} \frac{q^2 + q + 1}{q+3} \\ \\
2. \quad & \lim_{x \to -2} \frac {x^2-4}{x+2} \\ \\
3. \quad & \lim_{x \to 0} \frac{\sec x\tan x}{\sin x} \\ \\
4. \quad & \lim_{x \to +\infty} \frac{6x^2 -3x+1}{3x^2+4} \\ \\
5. \quad & \lim_{x \rightarrow +\infty} \frac {x^2+x+1}{x^4-3x^2+2} \\ \\
6. \quad & \lim_{y \to 0} \frac{\ln(1+2y)\sin y}{y^2\cos 2y} \\ \\
7. \quad & \lim_{x\to 1} \frac{\ln x}{x^2} \\ \\
8. \quad & \lim_{t\to 0} (3t^2+4t)\cot(t) \\ \\
9. \quad & \lim_{z\to 0} \frac{z\cos(\sin(z))}{\sin(2z)} \\ \\
10. \quad & \lim_{x \to 0} \frac{\ln (x+1)\arctan x}{x^2} \\ \\
11. \quad & \lim_{x \to 0} \frac{\ln^2(\cos x)}{2x^4-x^5} \\ \\
12. \quad & \lim_{s \to 0} \frac{e^s s \sin s}{1 - \cos 2s} \\ \\
13. \quad & \lim_{x \to 0^+} \frac{\sin(\arctan(\sin x))}{\sqrt{x} \sin 3x +x^2+ \arctan 5x} \\ \\
14. \quad & \lim_{x \to 0} \frac{\sin x -\cos x -1}{6x e^{2x}} \\ \\
15. \quad & \lim_{x \to 0} \frac{\arctan x-3 \sin x +2x}{3x^3} \\ \\
16. \quad & \lim_{p \to 0} \frac{1-p- \cos 3p}{p^3} \\ \\
17. \quad & \lim_{x \to \infty} x^{1/x} \\ \\
\end{aligned}
\end{multline}
$$
