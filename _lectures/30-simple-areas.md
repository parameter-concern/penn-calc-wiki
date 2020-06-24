---
title: Simple Areas
description: Finding the area of regions in the plane
lecture_number: 30
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
We know the basic standard formulae for the area of basic shapes, but why are they true? From the point of view of calculus, area $$A$$ is the integral of $$dA$$, the area element.

In this chapter, we will use the following procedure to determine a quantity $$U$$:
1. Determine the differential element $$dU$$.
2. Integrate to compute $$U=\int dU$$.
Length of an interval

Before getting to areas, first consider how this method works for computing the length $$L$$ of the interval from $$a$$ to $$b$$. If the length is denoted $$L$$, then the length element will be denoted $$dL$$, and $$L = \int dL$$. In this context, the appropriate length element would be $$dx$$ if we're working along the $$x$$-axis.

So, we want to integrate $$dx$$ as $$x$$ goes from $$a$$ to $$b$$.
The length,

$$
\begin{align*}
L &= \int dL
&= \int_{x=a}^b dx
&= x \bigg\vert^b_{x=a}
&= b - a
\end{align*}
$$

Parallelogram

The formula for the area of a parallelogram is base $$\times$$ height $$(bh)$$. Consider the following rearrangement into differential elements, where we carve the parallelogram into parallel horizontal strips of width $$b$$ and height $$dy$$, where $$y$$ is the $$y$$-axis.

In this case, the area element, $$dA = b \:dy$$, is the area of this infinitesimal rectangle. The limits on $$y$$ should go from $$0$$ to the height, $$h$$ of the parallelogram.
The area,

$$
\begin{align*}
A &= \int dA
&= \int_{y=0}^h b \, dy
&= by \bigg\vert^h_{y=0}
&= bh
\end{align*}
$$

We have our familiar answer $$bh$$. This means that we've done a rearrangement in terms of infinitesimal strips. Shearing that parallelogram preserves the area element and hence, the area. That is why a parallelogram has the same area as the corresponding rectangle.
Triangle

The formula for the area of a triangle is $$\frac{1}{2} \times$$ base $$\times$$ height $$(\frac{1}{2}bh)$$. Let's think in terms of a differential area element. Given the fact that we can shear and preserve the area element, and thus the area, let's present our triangle as having a hypotenuse modeled by the line $$y = \frac{h}{b}x$$.

To compute the area element, let's use a vertical strip.

$$
\begin{equation*} dA = \frac{h}{b}x\:dx \end{equation*}
$$

where the height of that vertical strip is $$\frac{h}{b}x$$ and the width is the length element $$dx$$.
The area,

$$
\begin{align*}
A &= \int dA
&= \int_{x=0}^b \frac{h}{b}x \, dx
&= \frac{h}{b} \frac{x^{2}}{2} \bigg\vert^b_{x=0}
&= \frac{hb^{2}}{2b}
&= \frac{1}{2}bh
\end{align*}
$$

Disc

We will use three ways to find the area of a circular disc of radius $$r$$:
1. Using an angular area element.
2. Using a radial variable.
3. Using a lateral, or a vertical rectangular strip.

- Angular 

In this case, we'll use an angular area element. We will take a wedge with angle $$d\theta$$. If we look at that close up, it's modeled fairly well as a triangle. It's not a perfect triangle, there's a bit of curvature at the end. This is a triangle with two sides of length $$r$$ whose included angle is $$d\theta$$. Such a triangle has area $$\frac{1}{2}r^2\sin(d\theta) \approx \frac{1}{2}r^2 d\theta$$, since $$d\theta$$ is very small. If we model that as a triangle with height $$r$$, and width $$r\:d\theta$$, we can ignore the higher order terms in the Taylor expansion of that area. We obtain an area element $$dA=\frac{1}{2}r(r\:d\theta)$$.

Integrating to get the area, $$\theta$$ has to spin all the way around the circle from $$0$$ to $$2\pi$$.
The area,

$$
\begin{align*}
A &= \int dA
&= \int_{\theta = 0}^{2\pi} \frac{1}{2} r^2 \, d\theta
&= \frac{1}{2} r^2 \int_{\theta = 0}^{2\pi} \, d\theta
&= \frac{1}{2} r^2 \theta \bigg\vert_{\theta=0}^{2\pi}
&= \frac{1}{2} r^2 (2\pi)
&= \pi r^2.
\end{align*}
$$

Radial 

Let's consider a radial variable. We can sweep out the area of the circular disk using annuli with a radial coordinate $$t$$. Then, we're looking at an annular strip of width $$dt$$. The corresponding area element is the circumference $$(2 \pi t)$$ $$\times$$ thickness $$(dt)$$.

$$
\begin{align*}
dA = 2\pi t\:dt
\end{align*}
$$

Integrating this from $$0$$ to the radius $$r$$ gives us the area.

$$
\begin{align*}
A &= \int dA
&= \int_{t=0}^r 2\pi t \, dt
&= \pi t^2 \bigg\vert^r_{t=0}
&= \pi r^2.
\end{align*}
$$

Lateral 

We will use a vertical rectangular strip. Again, it is not a perfect rectangle and there's a little bit of curvature at the end. But, these are higher order terms, and we just care about the differential element. So, using a vertical strip with width $$dx$$, and knowing that the formula for the boundary circle is $$x^{2}+y^{2}=r^{2}$$, we solve for $$y$$ along the upper and lower branches.

$$
\begin{align*}
y = \pm \sqrt{r^{2}-x^{2}}
\end{align*}
$$

We then obtain an area element that is the area of this rectangular strip.

$$
\begin{align*}
dA = 2\sqrt{r^2-x^2}\:dx
\end{align*}
$$

In the case of strips, assume the circle is centered at the origin, and let $$x$$ keep track of where the strip intersects the $$x$$-axis. Thus, $$x$$ ranges from $$-r$$ to $$r$$. Integrating, and using a trigonometric substitution $$x = r\sin u$$ gives

$$
\begin{align*}
A &= \int dA
&= \int_{-r}^r 2\sqrt{r^2-x^2} \:dx
&= 2 \int_{-\pi/2}^{\pi/2} \sqrt{r^2(1-\sin^2u)} \:r \cos u \:du
&= 2r^2 \int_{-\pi/2}^{\pi/2} \cos^2u\: du
&= 2r^2 \int_{-\pi/2}^{\pi/2} \frac{1}{2}(1+\cos(2u))du
&= r^2 (u + \frac{1}{2}\sin\:2u)\bigg\vert^{\pi/2}_{-\pi/2}
&= \pi r^2
\end{align*}
$$

The area between two curves

Let's say the $$f$$ is on top and the $$g$$ is below. Then as we sweep a vertical strip from left to right, we obtain the area. In this case, the area element is a vertical rectangle of width $$dx$$ and of height $$f(x) - g(x)$$, the length of the interval between the two.

$$
\begin{align*}
dA &= (f(x) - g(x)) dx
\end{align*}
$$

The general formula for the area between two curves $$f(x)$$ and $$g(x)$$,

$$
\begin{align*}
A &= \int dA
&= \int_{x=a}^b (f(x) - g(x)) dx
\end{align*}
$$

**Example**
Find the area of the region bounded above by $$f(x) = 4+x-x^2$$ and below by $$g(x) = 1-x$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


The logical choice for area element is a vertical strip:

The height of this strip is $$f(x)-g(x) = 3+2x-x^2$$, and the width of the strip is $$dx$$. So the area element is $$dA = (3+2x-x^2)dx$$. To find the intersection points, set the curves equal, which gives $$1-x=4+x-x^2$$. This implies $$x^2-2x-3=0$$, which factors to $$(x+1)(x-3) = 0$$. Thus, the intersections are $$x=-1$$ and $$x=3$$. It follows that

$$
\begin{align*}
A &= \int dA
&= \int_{-1}^3 (3+2x-x^2)dx
&= \left(3x+x^2-\frac{1}{3}x^3\right) \bigg\vert^3_{-1}
&= (9 + 9 - 9) - \left(-3+1+\frac{1}{3}\right)
&= \frac{32}{3}.
\end{align*}
$$

Gini Index (An application of area formula)

In economics, this ratio is used to quantify income inequality in a population.

Let $$f(x)$$ = Fraction of total income earned by the lowest $$x$$ fraction of the populace, $$0<x<1$$.
The Gini index quantifies how far $$f$$ is from a "flat" distribution. This means that f(0) = 0, f(1) = 1.
$$
\begin{equation*} f \end{equation*}
$$

is probably going to be below the flat distribution where $$y = x$$, the lowest $$x$$ fraction earns the lowest $$x$$ fraction.

The Gini index, $$G(f)$$ is measuring the difference between these two distributions, in terms of area. It's the ratio of the area between the flat distribution $$y = x$$ and the given population's income distribution $$y = f(x)$$. One normalizes that by the area between the flat distribution $$y = x$$ and $$y = 0$$, namely the area of that triangle, or $$\frac{1}{2}$$.

$$
\begin{align*}
G(f) &= \frac{\text{Area between the $y = x$ and $y = f(x)$}}{\text{Area between $y = x$ and $y = 0$}}
&= 2 \int_{x=0}^1 (x - f(x))\,dx.
\end{align*}
$$

**Example**
Compute $$G$$ for a power law distribution $$f(x) = x^n$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


$$
\begin{align*}
G(f) &= 2 \int_{x=0}^1(x - f(x))\:dx
&= 2 \int_{x=0}^1(x - x^n)\:dx
&= 2(\frac{x^2}{2} - \frac{x^{n+1}}{n+1})\bigg\vert^1_{x=0}
&= 1 - \frac{2}{n+1}
&= \frac{n-1}{n+1}
\end{align*}
$$

The Gini Index doesn't tell you the income distribution, but we could approximate it in the assumption of a power law. For example, in the year 2010, in the state of New York in USA, the Gini Index was very close to $$\frac{1}{2}$$. If we assume that it went by a power law distribution, that would imply a cubic distribution of income.

## Exercises

- What is the area between the curve $$f(x) = \sin^3 x$$ and the $$x$$-axis from $$x=0$$ to $$\displaystyle x=\frac{\pi}{3}$$ ?
- Find the area of the bounded region enclosed by the curves $$y = \sqrt{x}$$ and $$y = x^2$$.
- What is the area between the curve $$y = \sin x$$ and the $$x$$-axis for $$0\le x\le \pi$$ ?
- Calculate the Gini index of a country where the fraction of total income earned by the lowest $$x$$ fraction of the populace is given by 

$$ \displaystyle f(x) = \frac{2}{5} x^2 + \frac{3}{5} x^3 $$.

- Compute the area between the curves $$f(x) = e^x \sec^2 x$$ and $$g(x) = e^x \tan^2 x$$ for $$0\le x\le \pi$$.
- Consider a cone of height $$h$$ with base a circular disc of radius $$r$$. Let's compute the "surface area" -- the area of the "outside" of the cone, not including the bottom. Following how we computed the area of a circular disc (which is, indeed, such a cone with $$h=0$$ ), we can decompose its area into infinitesimal triangles with base $$r d\theta$$ and height the slant length $$L=\sqrt{h^2+r^2}$$. The area element $$dA$$ is then the area of this infinitesimal triangle. Integrating $$dA$$ from $$\theta = 0$$ to $$\theta = 2\pi$$ gives the "surface area" of the cone. What is its value?
- Compute the area between the curves $$\sin(x) $$ and $$ \cos(x) $$ from $$ x=0 $$ to $$ x= \pi/2 $$.
- Compute the area of a triangle with vertices at (0,0), (2,1), (3,6) 