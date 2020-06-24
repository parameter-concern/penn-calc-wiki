---
title: Centroids and centers of mass
description: Finding centroid and center of mass with integration
lecture_number: 40
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
The motivation for this module are the questions:

- what is the average of several locations (e.g. cities on a map)?
- what is the average of an entire region? 

The centroid and center of mass give answers to these questions. The formulas for the centroid and the center of mass of a region in the plane seem somewhat mysterious for their apparent lack of symmetry. So before giving the formulas, a brief aside is helpful.
The area element revisited

In future courses, the area element of a region will not be a strip of area but a small rectangle with width $$dx$$ and height $$dy$$:

The area of the region, then, is the limit of the sum of the areas of all these small rectangles as the rectangles get infinitely small. The notation used to express this is called a double integral, written

$$
\begin{equation*} \hbox{Area } = \iint_R dx\,dy. \end{equation*}
$$

Think of the double integral as a nested integral: $$\iint dx\,dy = \int (\int dx)\, dy$$. The inner integral is performed first, with respect to $$x$$ (since the $$dx$$ is left of the $$dy$$). Then the result is integrated with respect to $$y$$. Conceptually, the inner integral is adding up the contribution of a row of boxes, and then the outer integral is adding up the rows:

Double integrals can be computed in the other order too: $$\iint dy\,dx$$. First the inner integral is performed with respect to $$y$$, which adds up the contribution of a column of boxes. Then the outer integral adds up the contribution of the columns:

**Example**

Express the area of the region bounded by the curves $$y=x^2-4x+5$$ and $$y = x+1$$ as a double integral and evaluate the integral. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


The easier order of integration is $$dy\,dx$$ because every vertical strip is bounded on top by $$y=x+1$$ and bounded below by $$y = x^2-4x+5$$; whereas a horizontal strip would sometimes be bounded on the left by $$y=x+1$$, and other times be bounded by $$y=x^2-4x+5$$.

Setting the curves equal gives the intersections at $$x=1$$ and $$x=4$$. So the area can be found by computing

$$
\begin{align*}
\int_{x=1}^{x=4} \int_{y=x^2-4x+5}^{y=x+1} \,dy\,dx &= \int_{x=1}^{x=4} \left(y \bigg\vert^{x+1}_{x^2-4x+5} \right) \,dx
&= \int_{x=1}^{x=4} (x+1-(x^2-4x+5)) \,dx
&= \int_{x=1}^{x=4} (-x^2+5x-4)\,dx
&= -\frac{x^3}{3} + \frac{5}{2}x^2 - 4x \bigg\vert^4_1
&= \frac{9}{2}.
\end{align*}
$$

Centroid

The centroid of a region $$R$$ in the plane is defined to be the point $$(\overline{x},\overline{y})$$, where $$\overline x$$ is the average $$x$$-coordinate of $$R$$ and $$\overline y$$ is the average $$y$$-coordinate of $$R$$. One interpretation is that if the region were cut out of a sheet of uniform density metal and a pin were placed at its centroid, the region would balance on the pin.

The centroid is best expressed mathematically using double integrals:

$$
\begin{align*}
\overline x &= \displaystyle \frac{ \iint_R x \, dx\,dy}{\iint_R \, dx\,dy}
\overline y &= \displaystyle \frac{ \iint_R y \, dx\,dy}{\iint_R \, dx\,dy}.
\end{align*}
$$

Suppose the region $$R$$ is bounded above by the curve $$y = f(x)$$ and below by the curve $$y = g(x)$$, and the intersection points are at $$x=a$$ and $$x=b$$. Then integration is easier in the $$dy\,dx$$ order, and the centroid can be written more explicitly as

Centroid of a region

The centroid of the region bounded above by $$y = f(x)$$ and below by $$y = g(x)$$ is given by

$$
\begin{align*}
\overline x &= \frac{ \int_a^b \int_{g(x)}^{f(x)} x dydx}{\int_a^b \int_{g(x)}^{f(x)} dydx}
&= \frac{ \int_a^b x(f(x)-g(x))dx}{\int_a^b (f(x)-g(x))dx}.
\end{align*}
$$

Similarly,

$$
\begin{align*}
\overline y &= \frac{\int_a^b \int_{g(x)}^{f(x)} y \,dy\,dx}{\int_a^b \int_{g(x)}^{f(x)} \,dy\,dx}
&= \frac{ \int_a^b \frac{1}{2}(f(x)^2-g(x)^2)\,dx}{\int_a^b(f(x)-g(x))\,dx}.
\end{align*}
$$

Note that the denominator in each case is the area of the region.

**Example**

Find the centroid of a triangle with vertices at $$(a,0), (b,0),$$ and $$(0,c)$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The easier order of integration is $$dx\,dy$$ because a horizontal strip is always bounded on the left by $$x = \frac{-b}{c}y+b$$ and on the right by $$x = \frac{-a}{c}y+a$$ (see the diagram below). So one finds that

$$
\begin{align*}
\overline x &= \frac{\int_{y=0}^{y=c} \int_{x=\frac{-b}{c}y+b}^{x = \frac{-a}{c}y+a} x \,dx\,dy}{\int_{y=0}^{y=c} \int_{x=\frac{-b}{c}y+b}^{x = \frac{-a}{c}y+a}\,dx\,dy}
&= \frac{\int_{y=0}^{y=c} \int_{x=\frac{-b}{c}y+b}^{x = \frac{-a}{c}y+a} x\,dx\,dy}{\hbox{Area}}
\end{align*}
$$

Noting that the area of the triangle is $$\frac{1}{2}(a-b)c$$, one finds

$$
\begin{align*}
\overline x &= \frac{2}{(a-b)c} \int_{y=0}^{y=c} \int_{x=\frac{-b}{c}y+b}^{x = \frac{-a}{c}y+a} x\,dx\,dy
&= \frac{2}{(a-b)c} \int_{y=0}^{y=c} \frac{1}{2}\left((\frac{-a}{c}y+a)^2-(\frac{-b}{c}y+b)^2\right)\,dy
&= \frac{1}{(a-b)c} \cdot \frac{1}{3}\left((\frac{-a}{c}y+a)^3 \frac{-c}{a}-(\frac{-b}{c}y+b)^3 \frac{-c}{b}\right) \bigg\vert^c_0
&= \frac{1}{3(a-b)c} (a^2 c - b^2 c)
&= \frac{1}{3(a-b)c} c(a+b)(a-b)
&= \frac{1}{3}(a+b).
\end{align*}
$$

A similar computation gives that $$\overline y = \frac{c}{3}$$.

More generally, the centroid of a triangle with coordinates $$(x_0,y_0)$$, $$(x_1,y_1)$$, and $$(x_2,y_2)$$ is

$$
(\overline x, \overline y) = \left(\frac{x_0+x_1+x_2}{3}, \frac{y_0+y_1+y_2}{3}\right).
$$

In other words, the centroid of a triangle is the average of the x coordinates and the average of the y coordinates.

**Example**

Compute the centroid of the upper half circle of radius $$R$$.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


By the symmetry about the $$y$$-axis, the $$x$$-coordinate of the centroid is 0.

To find the $$y$$-coordinate, note that the equation of the curve is $$y = \sqrt{R^2-x^2}$$. Also, note that the area of the region is $$\frac{1}{2} \pi R^2$$. Thus,

$$
\begin{align*}
\overline{y} &= \frac{2}{\pi R^2} \int_{x=-R}^R \frac{1}{2}(\sqrt{R^2-x^2})^2 \, dx
&= \frac{1}{\pi R^2} \left( R^2 x - \frac{1}{3}x^3\right) \bigg\vert_{x=-R}^R
&= \frac{1}{\pi R^2} \cdot \frac{4 R^3}{3}
&= \frac{4R}{3\pi}.
\end{align*}
$$

**Example**

Compute the centroid of the quarter circle of radius $$R$$:

<button class="toggle" data-box="#box4a">Answer</button>

<div id="box4a" class="answer-hidden"></div>
{: id="box4a" class="answer-hidden"}


We know that the area of the region is $$\frac{1}{4}\pi R^2$$. So we have that

$$
\begin{align*}
\overline{x} &= \frac{1}{A} \int x(f(x)-g(x)) \, dx
&= \frac{4}{\pi R^2} \int_{x=0}^R x(\sqrt{R^2-x^2} - 0) \, dx.
\end{align*}
$$

Making a substitution of

$$
\begin{align*}
u &= R^2 - x^2
du &= -2x \, dx
\end{align*}
$$

gives

$$
\begin{align*}
\frac{4}{\pi R^2} \int_{x=0}^R x \sqrt{R^2-x^2} \, dx &= \frac{4}{\pi R^2} \int_{u=R^2}^0 -\frac{1}{2} \sqrt{u} \, du
&= \frac{-2}{\pi R^2} \frac{2}{3} u^{3/2} \bigg\vert_{u=R^2}^0
&= \frac{2}{\pi R^2} \cdot \frac{2}{3} R^3
&= \frac{4 R}{3 \pi}.
\end{align*}
$$

Because the region is symmetric about the line $$y=x$$, we predict that $$\overline{y} = \frac{4R}{3\pi}$$ as well. We can verify this by integrating:

$$
\begin{align*}
\overline{y} &= \frac{1}{A} \int \frac{1}{2}(f(x)^2 - g(x)^2) \, dx
&= \frac{2}{\pi R^2} \int_{x=0}^R (R^2 - x^2) \, dx
&= \frac{2}{\pi R^2} \left(R^2 x - \frac{1}{3}x^3\right) \bigg\vert_{x=0}^R
&= \frac{2}{\pi R^2} \left(R^3 - \frac{1}{3}R^3 \right)
&= \frac{2}{\pi R^2} \cdot \frac{2}{3} R^3
&= \frac{4R}{3 \pi},
\end{align*}
$$

as claimed.
Symmetry

It is important to note that centroids respect symmetry. What that means is that if there is an axis of symmetry (i.e. a line where if we reflect the region about the line we get the same region back), then the centroid must lie on the axis of symmetry. If there is more than one axis of symmetry, then the centroid will lie at the intersection of these axes:
Center of mass

Now consider a region $$R$$ of the plane cut from a sheet of metal of variable density $$\rho(x,y)$$. Again, the problem is to find the balancing point $$(\overline x, \overline y)$$, but in this context it is called the center of mass. Again, it is expressed as a double integral:

$$
\begin{align*}
\overline x &= \frac{\iint_R \rho(x,y)x\,dx\,dy}{\iint_R \rho(x,y) \,dx\,dy}
\overline y &= \frac{\iint_R \rho(x,y)y\,dx\,dy}{\iint_R \rho(x,y) \,dx\,dy}.
\end{align*}
$$

The only difference between these and the centroid formulas is that instead of the area element $$dA = dx\,dy$$, the mass element $$dM = \rho(x,y)\,dx\,dy$$ is used (multiplying the area element by the density of that point gives the mass contributed by that small rectangle). Indeed, if the density is constant, then $$\rho(x,y) = \rho$$ factors out of both the numerator and denominator and cancel, leaving the formula for centroid.

Note that the denominator for both $$\overline{x}$$ and $$\overline{y}$$ is the mass of the region.

**Example**

Compute the center of mass of the region bounded above by $$y = 4x-x^2$$ and below by the x-axis, where the density function is given by $$\rho(x,y) = 2x$$:

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Setting $$y=0$$, we find that the curve intersects the x-axis at $$x=0$$ and $$x=4$$. First, we compute the mass of the region, which is the denominator for both $$\overline{x}$$ and $$\overline{y}$$. It is easier to integrate in the $$dy \, dx$$ order, so we will do that here, and in the integrals that follow.

$$
\begin{align*}
M &= \iint_R \rho(x,y) \,dy\,dx
&= \int_{x=0}^4 \int_{y=0}^{4x-x^2} 2x \, dy \, dx
&= \int_{x=0}^4 \left(2xy \bigg\vert_{y=0}^{4x-x^2} \right) \, dx
&= \int_{x=0}^4 2x(4x-x^2) \, dx
&= \int_{x=0}^4 (8x^2 - 2x^3) \, dx
&= \frac{8}{3}x^3 - \frac{1}{2}x^4 \bigg\vert_{x=0}^4
&= \frac{512}{3} - 128 = \frac{128}{3}.
\end{align*}
$$

So to compute $$\overline{x}$$, we find

$$
\begin{align*}
\overline{x} &= \frac{1}{M} \iint_R \rho(x,y)x\,dy\,dx
&= \frac{3}{128} \int_{x=0}^4 \int_{y=0}^{4x-x^2} (2x)x \, dy \, dx
&= \frac{3}{128} \int_{x=0}^4 \left(2x^2 y \bigg\vert_{y=0}^{4x-x^2} \right) \, dx
&= \frac{3}{128} \int_{x=0}^4 2x^2(4x-x^2) \, dx
&= \frac{3}{128} \left(2x^4 - \frac{2}{5}x^5 \right) \bigg\vert_{x=0}^4
&= \frac{3}{128} 512 - \frac{2048}{5}
&= \frac{3}{128} \cdot \frac{512}{5} = \frac{12}{5}.
\end{align*}
$$

Similarly,

$$
\begin{align*}
\overline{y} &= \frac{1}{M} \iint_R \rho(x,y)y \, dy\,dx
&= \frac{3}{128} \int_{x=0}^4 \int_{y=0}^{4x-x^2} (2x)y \, dy \, dx
&= \frac{3}{128} \int_{x=0}^4 xy^2 \bigg\vert_{y=0}^{4x-x^2} \, dx
&= \frac{3}{128} \int_{x=0}^4 x(4x-x^2)^2 \, dx
&= \frac{3}{128} \int_{x=0}^4 (16x^3 - 8x^4 + x^5) \, dx
&= \frac{3}{128} \left(4x^4 - \frac{8}{5} x^5 + \frac{1}{6} x^6\right) \bigg\vert_{x=0}^4
&= \frac{3}{128} \cdot 1024 \left(1 - \frac{8}{5} + \frac{2}{3}\right) = \frac{8}{5}.
\end{align*}
$$

Centroids using point masses

Given a complex region which consists of the union of simpler regions, there is a method for finding the centroid:

- Find the centroid of each simple region.
- Replace each region with a point mass at its centroid, where the mass is the area of the region.
- Find the centroid of these point masses (this is done by taking a weighted average of their x and y coordinates). 

This is easiest to see with an example:

**Example**

Find the centroid of a region consisting of a rectangle of width $$2R$$ and height $$H$$ which has a semicircle of radius $$R$$ on one end:

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


From an earlier example, the centroid of the semicircle is $$(0,\frac{4R}{3\pi})$$, and the weight (the area of the semicircle) is $$\frac{1}{2}\pi R^2$$.

The rectangle is symmetric, so its centroid (as it is drawn in the coordinate plane) is $$(0,-\frac{H}{2})$$, and its weight is $$2RH$$:

By symmetry,

$$
\overline{x} = 0.
$$

Taking the weighted average of the y-coordinates of the points gives

$$
\begin{align*}
\overline{y} &= \frac{\frac{1}{2}\pi R^2 \cdot \frac{4R}{3\pi} + 2RH \cdot \left(-\frac{H}{2}\right)}{\frac{1}{2}\pi R^2 + 2RH}
&= \frac{\frac{2}{3}R^3 - H^2R}{\frac{1}{2}\pi R^2 + 2RH}
&= \frac{4R^2 - 6H^2}{3 \pi R + 12H}.
\end{align*}
$$

We can check that this is reasonable by noting that if $$H=0$$ we get the y-coordinate of the centroid of the semicircle, and when $$R=0$$ we get the y-coordinate of the centroid of the line segment from $$(0,0)$$ to $$(0,-H)$$.
Application: Pappus' theorem

One application of the centroid is known as Pappus' theorem, after the Greek mathematician Pappus of Alexandria. It uses the centroid to find the volume and surface area of a solid of revolution.

Pappus' theorem

Consider the solid which results from rotating the plane region $$R$$ about the axis $$L$$.

The volume of this solid is equal to the area of $$R$$ times the distance the centroid travels (as it gets revolved around the axis).

The surface area of the solid is equal to the perimeter of $$R$$ times the distance the centroid travels.

**Example**

Find the volume and surface area of a torus (i.e. a doughnut) with cross sectional radius $$r$$ and main radius $$R$$:

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Here, the region being rotated is a circle, which is easy to work with because a circle's centroid is just its center. For convenience, center the circle at $$(R,0)$$ and revolve around the $$y$$-axis. Then the distance which the centroid travels is $$2\pi R$$ (the path of the centroid is just a circle of radius $$R$$).

Therefore the surface area of the torus is

$$
\begin{align*}
\hbox{Surface area } &= \hbox{Perimeter } \cdot \hbox{ Centroid travel distance }
&= (2 \pi r) \cdot (2\pi R)
&= 4 \pi^2 r \cdot R.
\end{align*}
$$

And the volume of the torus is

$$
\begin{align*}
\hbox{Volume } &= \hbox{Area } \cdot \hbox{ Centroid travel distance }
&= (\pi r^2) \cdot (2 \pi R)
&= 2 \pi^2 r^2 R.
\end{align*}
$$


## Exercises

- Compute the area of region bounded by curves $$x=(y-2)^2+2$$ and $$y=x-2$$ using double integrals.
- Consider the region under the graph $$y=x^2$$, above the x-axis, from $$x=0$$ to $$x=1$$. Let $$S$$ be the solid obtained by revolving this region about the y-axis. Compute the average height (average y-coordinate) of $$S$$.
- Let $$R1$$ denote the region inside the triangle with vertices at (0,1), (-2,0), (0,-1). Given a unit circle centered at the origin, let $$R2$$ denote the region inside the semicircle for $$x \geq 0$$. Let $$R$$ denote the union $$R1$$ and $$R2$$. compute the centroid of $$R$$. 