---
title: Complex Areas
description: Areas of more complex regions in the plane
lecture_number: 31
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
Complex regions

Some regions in the plane are more complicated and cannot be evaluated with a single integral. This happens when the area element is not bounded by the same curves throughout the region. For instance, consider the region bounded by a parabola and two lines:

In this case, the only way to find the area of the region is to divide it into regions which can be integrated separately:
Horizontal strips

Other regions are difficult to integrate using vertical strips as the area element, but work well with horizontal strips as the area element. For example, consider the following region bounded on the left by $$x=g(y)$$ and on the right by $$x=f(y)$$:

In this case, the area of a horizontal strip is a function of $$y$$, namely $$(f(y)-g(y))dy$$, where $$x=f(y)$$ is the curve on the right and $$x =g(y)$$ is the curve on the left.

**Example**

Find the area between the curves

$$
\begin{align*}
y-x &= 0
y^2+x &= 2.
\end{align*}
$$

<button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


Expressing these curves as functions of $$y$$, we find

$$
\begin{align*}
x &= y
x = 2-y^2.
\end{align*}
$$

Graphing these curves, one finds the bounded region:

To find the intersections, set the curves equal to one another. This gives

$$
y = 2-y^2.
$$

A rearranging and factoring gives

$$
y^2+y-2 = (y-1)(y+2) = 0,
$$

and so we find that the intersection points are at $$y=1$$ and $$y=-2$$ (the x-coordinates are the same, since they are on the line $$x=y$$). Note that using a vertical rectangle as the area element here would not be so easy, because the area element depends on the value of $$x$$. Sometimes the strip goes from the parabola below to the line above, as shown in blue, and sometimes the strip goes from parabola to parabola, shown in red:

In particular, the area element for a vertical strip is

$$
dA = \begin{cases} (x + \sqrt{2-x}) \, dx & \hbox{if $-2 \leq x \leq 1$}
2 \sqrt{2-x} \, dx & \hbox{if $1 \leq x \leq 2$} \end{cases}
$$

But using a horizontal strip as the area element works much better because throughout the region the strip is always going from the line on the left to the parabola on the right. So using a horizontal strip gives the area element

$$
dA = ((2-y^2)-y) \, dy.
$$

Integrating this over the range of $$-2 \leq y \leq 1$$ gives the area:

$$
\begin{align*}
A &= \int dA
&= \int_{y=-2}^1 2-y^2 - y \, dy
&= 2y - \frac{y^3}{3} - \frac{y^2}{2} \bigg\vert_{y=-2}^1
&= \left(2 - \frac{1}{3} - \frac{1}{2}\right) - \left(-4 + \frac{8}{3} - 2\right)
&= \frac{9}{2}.
\end{align*}
$$

**Example**

Find the area of the region bounded by $$x = 3y$$ and $$x = y^2-4$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


The region looks roughly as in the following:

By setting $$3y = y^2-4$$, collecting like terms, and factoring, one finds the intersection points at $$y=-1$$ and $$y=4$$, as indicated in the figure. The area element is a horizontal rectangle, which has area $$dA = (3y - (y^2-4))dy$$.

Thus, the area between the curves is

$$
\begin{align*}
A &= \int dA
&= \int_{-1}^4 (3y-y^2+4) dy
&= \frac{3}{2}y^2 - \frac{1}{3}y^3+4y \bigg\vert^4_{-1}
&= \frac{125}{6}
\end{align*}
$$

**Example**

Find the area of the region bounded by $$y = \ln(x)$$ and the lines $$y = 0$$, $$y=1$$, and $$x=0$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The region looks roughly like the following:

Note that using vertical rectangles would not be ideal because this would require two integrals (for $$x$$ from 0 to 1 and from 1 to $$e$$). Instead, one can express the curve $$y = \ln x$$ as $$x=e^y$$. Now, using horizontal rectangles gives an area element of $$dA = e^ydy$$. Thus

$$
\begin{align*}
A &= \int dA
&= \int_0^1 e^y dy
&= e^y \bigg\vert^1_0
&= e-1.
\end{align*}
$$

Polar shapes

A polar shape is the graph of a polar function $$r = f(\theta)$$. Here, the input to the function is $$\theta$$, which is the angle formed with the positive $$x$$-axis (known as the pole). The output $$r$$ is the distance from the origin (or radial distance). For example, the following shows the graph of the polar function $$r = 1+ \cos \theta$$, which is known as a cardioid:

The area of such a region is not usually easy to compute by integrating with respect to $$x$$ or $$y$$ (for one thing, the polar equation would need to be expressed in terms of $$x$$ and $$y$$ first!). Instead, the way to integrate over such regions is to use a polar area element, which is a wedge shaped region. Here are several examples of the polar area element for various values of $$\theta$$:

To compute what the polar area element is in terms of $$\theta$$, $$r$$, and $$d\theta$$, note that the region is roughly triangular (the curved portion at the base of the triangle can be ignored since it is a higher order term). The angle at the tip of the triangle is $$d\theta$$, the height of the triangle is $$r$$, and the base of the triangle is $$r \, d\theta$$:

Thus, the polar area element is

$$
dA = \frac{1}{2}(r)(r\, d \theta) = \frac{1}{2} (f(\theta))^2 \, d\theta,
$$

since $$r = f(\theta)$$. Thus, the area of a polar region defined by $$r = f(\theta)$$, where $$a \leq \theta \leq b$$, is

$$
A = \int_{\theta=a}^b \frac{1}{2} (f(\theta))^2 \, d\theta.
$$

**Example**

Compute the area of the cardioid $$r = 1+\cos \theta$$. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


In this case, $$f(\theta) = 1 + \cos \theta$$, and so the area element is

$$
\begin{align*}
dA &= \frac{1}{2}(1+ \cos \theta)^2 \, d\theta
&= \frac{1}{2} (1 + 2 \cos \theta + \cos^2 \theta) \, d\theta
\end{align*}
$$

Because $$\theta$$ ranges from 0 to $$2\pi$$ to trace out the entire cardioid, it follows that the area is

$$
\begin{align*}
A &= \int dA
&= \frac{1}{2} \int_{\theta=0}^{2\pi} (1+ 2 \cos \theta + \cos^2 \theta) \, d\theta
&= \frac{1}{2} \int_{\theta=0}^{2\pi} (1 + 2 \cos \theta + \frac{1}{2}(1+\cos(2\theta))) \, d\theta
&= \frac{1}{2} \left( \theta + 2 \sin \theta + \frac{1}{2} \theta + \frac{1}{4} \sin(2 \theta) \right) \bigg\vert_{\theta=0}^{2\pi}
&= \frac{3\pi}{2}.
\end{align*}
$$

**Example**

Find the area of a single petal of the polar curve $$r = \sin(3\theta)$$:

Hint: To find the bounds on $$\theta$$, compute when $$r=0$$. <button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


The area element is $$dA = \frac{1}{2} \sin^2(3\theta)\, d\theta$$. To find the bounds on $$\theta$$, set $$r = 0$$, which gives $$\sin(3\theta) = 0$$. The smallest values of $$\theta$$ for which this occurs is $$\theta = 0$$ and $$\theta = \frac{\pi}{3}$$:

Thus, the area of a single petal is

$$
\begin{align*}
A &= \int dA
&= \int_{\theta = 0}^{\pi/3} \frac{1}{2} \sin^2 (3\theta) \, d\theta
&= \frac{1}{2} \int_{\theta = 0}^{\pi/3} \frac{1}{2} (1-\cos(6 \theta)) \, d\theta
&= \frac{1}{4} \left( \theta - \frac{1}{6} \sin(6 \theta) \right) \bigg\vert_{\theta=0}^{\pi/3}
&= \frac{\pi}{12}
\end{align*}
$$

**Example**

Find the area inside the circle $$r = 2 \sin \theta$$ and outside the circle $$r = 1$$:

<button class="toggle" data-box="#box5a">Answer</button>

<div id="box5a" class="answer-hidden"></div>
{: id="box5a" class="answer-hidden"}


First, we find the intersections by setting the curves equal, which gives

$$
2\sin \theta = 1 \quad \Rightarrow \quad \sin \theta = \frac{1}{2},
$$

and so the intersections are at $$\frac{\pi}{6}$$ and $$\frac{5\pi}{6}$$. The area element of the region is the polar area element of the circle $$r = 2 \sin \theta$$ minus the polar area element of the circle $$r =1$$:

So we have that

$$
dA = \left(\frac{1}{2}(2 \sin \theta)^2 - \frac{1}{2}(1)^2 \right) \, d \theta.
$$

Thus, the area is

$$
\begin{align*}
A &= \int dA
&= \frac{1}{2} \int_{\theta = \pi/6}^{5\pi/6} (4 \sin^2 \theta - 1) \, d \theta
&= \frac{1}{2} \int_{\theta = \pi/6}^{5\pi/6} 2 (1-\cos(2\theta)) - 1 \, d \theta
&= \frac{1}{2} \left(\theta - \sin(2 \theta) \right) \bigg\vert_{\pi/6}^{5\pi/6}
&= \frac{\pi}{3} + \frac{\sqrt{3}}{2}.
\end{align*}
$$

From the second to the third line above, we used the power reduction formula for sine:

$$
\sin^2 \theta = \frac{1}{2}(1-\cos(2\theta)).
$$


## Exercises

- Find the area enclosed by the curves $$y = 1$$, $$x = 1$$, and $$y = \ln x$$.
- Find the area of the bounded region enclosed by the $$x$$-axis, the lines $$x=1$$ and $$x=2$$ and the hyperbola $$xy = 1$$.
- Compute the area in the bounded (i.e., finite) regions between $$y=x(x-1)(x-2)$$ and the $$x$$-axis.
- Find the area of the sector of a circular disc of radius $$r$$ (centered at the origin) given by $$1 \leq \theta \leq 3$$ (as usual, $$\theta$$ is in radians).
- Use polar coordinates to find an area within $$r = 3 - 2cos(\theta)$$ and outside $$r = 3$$.
- Find the area of the overlap between two circles of radius 2 that pass through each others' centers. You can do so with either cartesian or polar coordinates (though one might be easier than the other!).
- Find the area bound by the curves $$y = \cos^2 x$$ and $$\displaystyle y = \frac{8x^2}{\pi^2}$$.
- Kepler's First Law states that the orbit of every planet is an ellipse with the Sun at one of its two foci. If we think of the Sun as being situated at the origin, we can describe the orbit with the equation: 

$$ \displaystyle r = \frac{p}{1+ \varepsilon\cos\theta} $$
The point at which the planet is closest to the Sun (the perihelion) corresponds to $$\theta = 0$$, while the planet is furthest away from the Sun at $$\theta = \pi$$ (the aphelion). Knowing the distance between the Sun and the planet at these two points would allow you to fix the values of the constants $$p$$ and $$\varepsilon$$. Notice that $$\varepsilon=0$$ describes a perfect circle, so that the "eccentricity" $$\varepsilon$$ measures how far the orbit is from being a circle.
Kepler's Second Law states that the line joining a planet and the Sun sweeps out equal areas during equal intervals of time. Another way of expressing this fact is by saying that the "areal velocity"
$$ \displaystyle v_{A} = \frac{dA}{dt} $$
of that line is constant in time.
Express the area element $$dA$$ in terms of the angle element $$d\theta$$ and use Kepler's Second Law to deduce the differential equation governing the time evolution of $$\theta$$.

- Let $$ C_1 $$ be the circle given by $$ r= \sin(\theta) $$. Let $$ C_2$$ be the circle given by $$ r= \cos(\theta) $$. Find the area of region in $$C_2$$ that is not in $$C_1$$. 