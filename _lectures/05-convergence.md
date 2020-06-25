---
title: Convergence
description: Problems with some Taylor series
lecture_number: 5
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
{::options parse_block_html="true" /}
A Taylor series can be thought of as an infinite polynomial. Up until now, we have not worried about the issues that come up when adding up infinitely many things. This module deals with two main issues:

1.  A function may not have a Taylor series at all;
2.  A function's Taylor series may not converge everywhere, even within the function's domain.

## Functions without a Taylor series

The first problem is that some functions cannot be expressed in the form

$$
f(x) = \sum_{k=0}^\infty c_k x^k = c_0 + c_1 x + c_2 x^2 + \dotsb
$$

Examples include $$\tan$$, which has vertical asymptotes, and $$\ln$$, which is not defined for $$x \leq 0$$. Polynomials are not able to capture these sorts of discontinuities and asymptotes.


### The geometric series

The geometric series is an example of a Taylor series which is well behaved for some values of $$x$$ and nonsensical for other values of $$x$$. The claim is that

$$
\begin{equation*} 1+x+x^2+x^3+x^4+\dotsb = \frac{1}{1-x}, \end{equation*}
$$

for $$\vert x \vert < 1$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden">
**Note** This is not a formal proof, which would require a few tools and definitions we have not yet learned.

Let $$y = 1+x+x^2+x^3+\dotsb $$. Multiplying both sides by $$x$$ gives

$$
\begin{align*}
y &= 1 + x + x^2 + x^3 + \dotsb \\
xy &= x + x^2 + x^3+x^4 + \dotsb
\end{align*}
$$

Now, subtracting the second equation from the first, all the terms other than 1 cancel on the right, leaving us with

$$
y(1-x) = 1.
$$

Dividing by $$1-x$$ gives $$y = \frac{1}{1-x}$$.
</div>

**Example** Compute the Taylor series for $$f(x) = \frac{1}{1-x}$$ directly from the definition.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden">
$$
\begin{align*}
f(x) &= \frac{1}{1-x} & f(0) &= 1 \\
f'(x) &= \frac{1}{(1-x)^2} & f'(0) &= 1 \\
f(x) &= \frac{2}{(1-x)^3} & f(0) &= 2 \\
f(x) &= \frac{6}{(1-x)^4} & f(0) &=6.
\end{align*}
$$

Notice the pattern that

$$
\begin{equation*}
f^{\left(k\right)}(x) = \frac{k!}{(1-x)^{k+1}},
\end{equation*}
$$

at least for the first few $$k$$. To see that the pattern continues, assume it holds for some $$k$$, and show that it holds for $$k+1$$ (this is a proof technique known as mathematical induction). If $$f^{\left(k\right)}(x) = \frac{k!}{(1-x)^{k+1}}$$, then

$$
\begin{equation*}
f^{\left(k+1\right)}(x) = \frac{(k+1)k!}{(1-x)^{k+2}} = \frac{(k+1)!}{(1-x)^{k+2}},
\end{equation*}
$$

as desired. Then $$f^{\left(k\right)}(0) = k!$$, so according to the definition of Taylor series, it follows that

$$
\begin{align*}
\frac{1}{1-x} &= 0! + 1!x+ \frac{2!}{2!}x^2+ \frac{3!}{3!}x^3+\dotsb \\
&= 1+x+x^2+x^3+\dotsb,
\end{align*}
$$

which agrees with the above.
</div>

**Note** The geometric series only holds when $$\vert x \vert < 1$$. This makes sense, because if $$\vert x \vert > 1$$, the powers of $$x$$ are getting bigger and bigger and so the series should not converge. If $$x=1$$, then the series is adding 1 infinitely many times, which diverges. If $$x=-1$$, then the series oscillates between 1 and 0, and hence does not converge.

The takeaway is that every Taylor series has a convergence domain where the series is well-behaved, and outside that domain the series will not converge. For many functions, the domain is the whole real number line (e.g. the series for $$e^x$$, $$\sin$$, $$\cos$$, $$\cosh$$, and $$\sinh$$ all converge everywhere), but be aware that there are functions whose Taylor series do not converge everywhere. This will be covered more formally in [Series]({{ site.baseurl }}{% link _lectures/50-series.md %}).

**Example** A beam of light of intensity $$L$$ hits a pane of glass. Half of the light is reflected, and a third of the light is transmitted; the rest is absorbed. When a beam of light of intensity $$L$$ hits two parallel panes with an air gap between them, how much light is transmitted through both panes? (The following figure shows how the light gets reflected and rereflected. The first transmitted and reflected beams of light are labeled with their respective intensities. The question asks for the total of the beams of light emerging on the right side of the right pane of glass).

![LightGlass]({{ site.baseurl }}/assets/images/LightGlass.png)
{: .mathimg }

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden">
By labeling more of the transmitted and reflected beams of light, a pattern emerges among the beams of light on the right side of the right pane:

![LightGlassSolved]({{ site.baseurl }}/assets/images/LightGlassSolved.png)
{: .mathimg }

$$\frac{1}{9},\frac{1}{36},\frac{1}{144},\ldots$$. Note that each beam is $$\frac{1}{4}$$ the previous beam. Thus, the total light emerging on the right side of the right pane of glass is

$$
\begin{align*}
\frac{L}{9} + \frac{L}{36} + \frac{L}{144}+\dotsb &= \frac{L}{9} \left(1 + \frac{1}{4}+\frac{1}{16}+\dotsb\right) \\
&= \frac{L}{9} \left(\frac{1}{1-1/4}\right) \\
&= \frac{L}{9}\,\frac{4}{3} \\
&= \frac{4L}{27}, \\
\end{align*}
$$

by using the formula for the geometric series.
</div>

**Example** Use the Taylor series of $$\frac{1}{1-x}$$ to derive the Taylor series of $$\ln(1+x)$$. Hint: recall that $$\ln(1+x) = \int \frac{1}{1+x}dx$$. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden">
Note that

$$
\begin{align*}
\frac{1}{1+x} &= \frac{1}{1-(-x)} \\
&= 1-x+x^2-x^3+x^4-\dotsb.
\end{align*}
$$

Now, integrating gives $$\int \frac{dx}{1+x} = \ln(1+x) + C$$ on the one hand, and

$$
\begin{align*}
\int (1-x+x^2-x^3+x^4-\dotsb) dx &= x - \frac{x^2}{2} +\frac{x^3}{3} -\dotsb \\
&= \sum_{k=1}^\infty (-1)^{k-1}\frac{x^k}{k},
\end{align*}
$$

on the other hand. Plugging in $$x=0$$ shows that $$C=0$$, and so

$$
\begin{align*}
\ln(1+x) &= x - \frac{x^2}{2} +\frac{x^3}{3} -\dotsb \\
&= \sum_{k=1}^\infty (-1)^{k+1}\frac{x^k}{k}. & (\vert x \vert < 1)
\end{align*}
$$

Note that because this relied on the geometric series, which only holds for $$\vert x \vert < 1$$, the same restriction holds for the Taylor series for $$\ln(1+x)$$.
</div>

**Example** Use the fact that

$$
\arctan x = \int \frac{1}{1+x^2}\, dx
$$

to find the Taylor series for $$\arctan x$$. <button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden">
Using the fact, and the geometric series, we find that

$$
\begin{align*}
\arctan(x) &= \int \frac{1}{1+x^2} \, dx \\
&= \int \frac{1}{1-\left(-x^2\right)} \, dx \\
&= \int \left(1-x^2+x^4-x^6+\dotsb \right) \, dx & (\vert x \vert < 1) \\
&= x - \frac{x^3}{3} + \frac{x^5}{5} - \frac{x^7}{7} + \dotsb + C.
\end{align*}
$$

Plugging in $$x=0$$ gives that $$C = 0$$, since $$\arctan 0 = 0$$. Thus,

$$
\begin{align*}
\arctan(x) &= x - \frac{x^3}{3}+\frac{x^5}{5}-\dotsb \\
&= \sum_{k=0}^\infty (-1)^k \frac{x^{2k+1}}{2k+1} & (\vert x \vert < 1).
\end{align*}
$$

So even though $$\arctan$$ is defined for all $$x$$, its Taylor series only converges for $$\vert x \vert < 1$$.
</div>

**Example** Another important function is the binomial series $$(1+x)^\alpha$$, where $$\alpha$$ is some constant. Show that

$$
\begin{align*}
(1+x)^\alpha &= 1 + \alpha x + \frac{\alpha (\alpha - 1)}{2!} x^2 + \frac{\alpha(\alpha-1)(\alpha-2)}{3!} x^3 + \dotsb \\
&= \sum_{k=0}^\infty {\alpha \choose k} x^k,
\end{align*}
$$

where $${\alpha \choose k} = \frac{\alpha (\alpha-1) (\alpha -2) \dotsb (\alpha - k + 1)}{k!}.$$

This series also only holds for $$\vert x \vert < 1$$.

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden">
For fixed $$\alpha$$ we have $$f(x) = (1+x)^\alpha$$. Then proceeding from the definition of the Taylor series, one computes

$$
\begin{align*}
f(x) &= (1+x)^\alpha & f(0) &= 1 \\
f'(x) &= \alpha(1+x)^{\alpha-1} & f'(0) &= \alpha \\
f(x) &= \alpha(\alpha-1)(1+x)^{\alpha-2} & f(0) &= \alpha(\alpha-1) \\
f(x) &= \alpha(\alpha-1)(\alpha-2)(1+x)^{\alpha-3} & f(0) &= \alpha(\alpha-1)(\alpha-2) \\
& \vdots & \vdots
\end{align*}
$$

One finds that, in general, $$f^{\left(k\right)}(0) = \alpha(\alpha-1)(\alpha-2)\dotsb (\alpha-k+1)$$. Thus, the Taylor expansion for $$(1+x)^\alpha$$ is

$$
\begin{align*}
(1+x)^\alpha &= 1 + \alpha x + \frac{\alpha(\alpha-1)}{2!}x^2 + \frac{\alpha(\alpha-1)(\alpha-2)}{3!}x^3 + \dotsb \\
&= 1 + \binom{\alpha}{1}x + \binom{\alpha}{2}x^2 + \binom{\alpha}{3}x^3 + \dotsb \\
&= \sum_{k=0}^\infty \binom{\alpha}{k} x^k,
\end{align*}
$$

as claimed.
</div>

## Summary

Here are all the series we have found so far. The following hold for all $$x$$:

$$
\begin{align*}
e^x &= \sum_{k=0}^\infty \frac{x^k}{k!} \\
\cos x &= \sum_{k=0}^\infty (-1)^k \frac{x^{2k}}{(2k)!} \\
\sin x &= \sum_{k=0}^\infty (-1)^k \frac{x^{2k+1}}{(2k+1)!} \\
\cosh x &= \sum_{k=0}^\infty \frac{x^{2k}}{(2k)!} \\
\sinh x &= \sum_{k=0}^\infty \frac{x^{2k+1}}{(2k+1)!}.
\end{align*}
$$

The following hold for $$\vert x \vert < 1$$:

$$
\begin{align*}
\frac{1}{1-x} &= \sum_{k=0}^\infty x^k \\
\ln(1+x) &= \sum_{k=1}^\infty (-1)^{k+1} \frac{x^k}{k} \\
\arctan x &= \sum_{k=0}^\infty (-1)^k \frac{x^{2k+1}}{2k+1} \\
(1+x)^\alpha &= \sum_{k=0}^\infty \binom{\alpha}{k} x^k.
\end{align*}
$$

## Electrostatics example

Here we use the geometric series and the binomial series from above in an example from electrostatics. An electric dipole is a pair of equally and oppositely charged particles separated by a short distance. One question of interest in electrostatics is the electrostatic potential, which is the sum of the point charge potentials from each pole.

The point charge potential from a single particle with charge $$q$$, at a distance $$d$$ from the particle, is

$$
V = \frac{kq}{d},
$$

where $$k$$ is a constant called the Coulomb constant. Then a dipole with particles of charge $$q$$ and $$-q$$ has net electrostatic potential

$$
V = \frac{kq}{d_+} - \frac{kq}{d_-},
$$

where $$d_+$$ is the distance to the positively charged particle, and $$d_-$$ is the distance to the negatively charged particle:

![Dipole]({{ site.baseurl }}/assets/images/Dipole.png)
{: .mathimg }

We will calculate the first order term for the electrostatic potential at two different locations: $$p_1$$ and $$p_2$$:

![DipolePositions]({{ site.baseurl }}/assets/images/DipolePositions.png)
{: .mathimg }

First consider $$p_1$$, located directly above and distance $$d$$ from the positive particle. Let $$r$$ be the distance between the charged particles. Then $$d_+ = d$$, and by the Pythagorean theorem, $$d_- = \sqrt{d^2+r^2}$$. It follows that the electrostatic potential is

$$
\begin{align*}
V &= \frac{kq}{d_+} - \frac{kq}{d_-} \\
&= \frac{kq}{d} - \frac{kq}{\sqrt{d^2+r^2}}.
\end{align*}
$$

Now, factoring out $$\frac{kq}{d}$$, and applying the binomial series with $$\alpha = -\frac{1}{2}$$, we find

$$
\begin{align*}
V &= \frac{kq}{d} \left[1 - \frac{1}{\sqrt{1+(r/d)^2}}\right] \\
&= \frac{kq}{d} \left[1 - \left(1+(r/d)^2\right)^{-1/2}\right] \\
&= \frac{kq}{d} \left[1 - \left(1 -\frac{1}{2} (r/d)^2 + \hbox{ HOT}\right)\right] \\
&= \frac{1}{2}\frac{kq r^2}{d^3} + \hbox{ HOT}.
\end{align*}
$$

At position $$p_2$$, which is directly left of and distance $$d$$ from the positive particle, we have $$d_+ = d$$, and $$d_- = d+r$$, so we find that the electrostatic potential at $$p_2$$ is

$$
\begin{align*}
V &= \frac{kq}{d_+} - \frac{kq}{d_-} \\
&= \frac{kq}{d} - \frac{kq}{d+r}.
\end{align*}
$$

Again, factoring out $$\frac{kq}{d}$$ and expanding using the geometric series gives

$$
\begin{align*}
V &= \frac{kq}{d} \left(1 - \frac{1}{1+\frac{r}{d}}\right) \\
&= \frac{kq}{d} \left(1 - \left(1 - \frac{r}{d} + \hbox{ HOT}\right)\right) \\
&= \frac{kqr}{d^2} + \hbox{ HOT}.
\end{align*}
$$

## Exercises

- Consider a snowman built from solid snowballs of radius $$2^{-n}$$, for $$n=0,1,2,\ldots $$, all stacked on top of one another. How many units tall is the snowman? How many cubic units of snow was required to build it?
- Compute the Taylor series about zero of
  
  $$
  \ln\frac{1+3x}{1-3x}
  $$
  
- Compute the Taylor series about zero of
  
  $$
  \frac{1}{\sqrt{1-x^2}}
  $$
  
- Using your answer to the previous problem, compute the Taylor series about zero of $$\arcsin x$$, using termwise integration and the fact that
  
  $$
  \arcsin x = \int \frac{dx}{\sqrt{1-x^2}}
  $$
  
- For which values $$z$$ is the Taylor series of $$\sqrt[4]{3-2z^2}$$ guaranteed to converge?
- Use the binomial series to give the Taylor expansion of $$(1+x)^3$$. Now, do it with your head: easier, right? Recall, we have said that the binomial series only converges when $$\vert x \vert < 1$$, but, clearly, that cannot be a *sharp* constraint, since $$(1+x)^3$$ is good for all $$x$$, right? Well, Horatio, there are more things... By the end of this course, we will learn when and how to bend some of these restrictions.
- Build a cylinder with radius 1 and height 3. Build a second cylinder with radius 1/2 and height 9, a third cylinder with radius 1/4, height 27, a fourth cylinder with radius 1/8 and height 81, and so on. What is the total volume of the cylinders?
- For which values of $$x$$ does the Taylor series of $$(\frac{1}{4}-3x^2)^{1/4}$$ converge?
