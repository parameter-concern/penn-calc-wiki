---
title: Volumes
description: Using the volume element to compute volume
lecture_number: 32
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
Finding the volume element

Just as area was computed by finding the area element and integrating, volume is computed by determining the volume element (i.e. the volume of a slice) and then integrating:

$$
V = \int dV.
$$

The difficulty is in finding a suitable volume element $$dV$$. Once that is chosen, the rest is a matter of evaluating the integral.

**Example**

Compute the volume of a cylinder of radius $$R$$ and height $$H$$ using several different volume elements $$dV$$:

<button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


First, consider making a slice perpendicular to the base of the cylinder:

This gives a rectangular slice whose height is $$H$$, the same as the cylinder. The width of the rectangle can be determined by looking at an overhead view of the cylinder. Let $$x$$ be the distance of the slice from the center of the cylinder (so $$x$$ ranges from $$-R$$ to $$R$$ as the slice sweeps across the cylinder):

Doing a little algebra, we find that the width of the rectangle is $$2 \sqrt{R^2-x^2}$$. Finally, the thickness of the slice is $$dx$$, and so the volume element in this case is

$$
dV = 2 H \sqrt{R^2 - x^2} \, dx.
$$

Integrating this requires the trigonometric substitution $$x = R \sin \theta$$. There are easier volume elements we could choose, as we shall see.

Another way to slice is to make cuts parallel to the base of the cylinder. Let $$y$$ denote the distance of the slice from the base of the cylinder:

Then each slice is a circle of radius $$R$$ and thickness $$dy$$. Thus

$$
dV = \pi R^2 \, dy,
$$

and $$y$$ ranges from 0 to $$H$$, so the volume is

$$
\begin{align*}
V &= \int dV
&= \int_{y = 0}^H \pi R^2 \, dy
&= \pi R^2 y \bigg\vert_{y=0}^H
&= \pi R^2 H.
\end{align*}
$$

Another possible choice is a wedge shaped volume element. Let $$\theta$$ be the angle that the wedge forms with a fixed axis (so $$\theta$$ ranges from 0 to $$2\pi$$):

Here, the area of the sector of the circle is $$\frac{1}{2}R^2 \, d\theta$$. Thus the volume of the wedge is

$$
dV = \frac{1}{2}R^2 H \, d\theta.
$$

Thus the volume is

$$
\begin{align*}
V&= \int dV
&= \int_{\theta = 0}^{2\pi} \frac{1}{2}R^2 H \, d \theta
&= \frac{1}{2}R^2 H \theta \bigg\vert_{\theta=0}^{2\pi}
&= \pi R^2 H.
\end{align*}
$$

One final option is to use cylindrical shells. Let $$t$$ be the radius of the shell, so that $$t$$ ranges from 0 to $$R$$ as the shells sweep through the cylinder.

The height of the cylindrical shell is $$H$$ and the thickness of the shell is $$dt$$. Recalling that the lateral surface area of a cylinder is $$2\pi RH$$, we have

$$
dV = 2 \pi t H \, dt.
$$

Integrating gives that the volumes is

$$
\begin{align*}
V &= \int dV
&= \int_{t = 0}^R 2 \pi t H \, dt
&= 2\pi H \frac{t^2}{2} \bigg\vert_{t=0}^R
&= \pi R^2 H.
\end{align*}
$$

**Example**

Find the volume of a sphere of radius $$R$$. First, by using discs as the volume element (shown on left below). Then use cylindrical shells as the volume element (shown on the right below). Finally, use a spherical shell for the volume element, as shown in the third diagram.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Let $$x$$ be the distance from the center of the disc to the center of the sphere (so $$x$$ ranges from $$-R$$ to $$R$$ as the discs sweep across the sphere). Then drawing a right triangle shows that the radius of the disc is $$\sqrt{R^2-x^2}$$ (since the radius of the sphere is $$R$$). See the diagram below:

The thickness of the disc is $$dx$$, and so the volume of the disc is $$\pi (\sqrt{R^2-x^2})^2 dx$$ (the area of the disc times its thickness), and so the volume of the sphere is

$$
\begin{align*}
V &= \int dV
&= \int_{x=-R}^{R} \pi (R^2-x^2)dx
&= \pi \left(R^2 x - \frac{x^3}{3}\right) \bigg\vert^{R}_{x=-R}
&= \pi \left(\left(R^3 - \frac{R^3}{3}\right) - \left(-R^3 + \frac{R^3}{3}\right)\right)
&= \frac{4}{3}\pi R^3.
\end{align*}
$$

For the cylindrical shell, let $$t$$ be the radius of the cylinder (so $$t$$ ranges from 0 to $$R$$ as the cylinders sweep out the sphere). Then by drawing in a right triangle, one finds that the height of the cylinder is $$2 \sqrt{R^2-t^2}$$:

Recall that the lateral surface area of a cylinder with radius $$r$$ and height $$h$$ is $$2\pi r h$$. Thus, the lateral surface area of the cylinder is $$4 \pi t \sqrt{R^2-t^2}$$. The thickness of the shell is $$dt$$, and so the volume element is $$4 \pi t \sqrt{R^2 - t^2}dt$$. It follows (after making the $$u$$-substitution $$u = R^2-t^2$$) that the volume of the sphere is

$$
\begin{align*}
V &= \int dV
&= \int_{t=0}^{R} 4 \pi t \sqrt{R^2-t^2}dt
&= 4 \pi \int_{u=R^2}^{0} \frac{-1}{2} \sqrt{u}du
&= -2 \pi \left(\frac{2}{3}u^{3/2} \bigg\vert_{u=R^2}^0 \right)
&= -2 \pi \left(0 - \frac{2}{3}R^3\right)
&= \frac{4}{3} \pi R^3.
\end{align*}
$$

Finally, for the spherical shell, let $$\rho$$ denote the radius of the spherical shell:

Recall that the surface area of a sphere of radius $$\rho$$ is $$4 \pi \rho^2$$. Therefore, the volume of the spherical shell (i.e. our volume element) is

$$
dV = 4 \pi \rho^2 \, d \rho.
$$

Note that to sweep over the entire sphere, $$\rho$$ must range from 0 to $$R$$. Therefore,

$$
\begin{align*}
V &= \int dV
&= \int_{\rho = 0}^R 4 \pi \rho^2 \, d \rho
&= 4 \pi \frac{1}{3} \rho^3 \bigg\vert_{\rho=0}^R
&= \frac{4}{3} \pi R^3.
\end{align*}
$$

**Example**

Find the volume of a cone of base radius $$R$$ and height $$H$$.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The easiest choice for volume element is a slice parallel to the base of the cone, which gives a disc. Let $$y$$ be the distance from the tip of the cone to the center of the disc (so $$y$$ ranges from 0 to $$H$$ as the disc sweeps across the cone), and $$x$$ be the radius of the disc:

The volume element is the area of the disc, $$\pi x^2$$, times the thickness of the disc, $$dy$$. It remains to find $$x$$ in terms of $$y$$. In the cutaway in the figure on the right above, one sees that by similar triangles, $$\frac{x}{y} = \frac{R}{H}$$, and so $$x = \frac{R}{H}y$$. Thus, the volume element is

$$
\begin{align*}
dV &= \pi x^2 dy
&= \pi \left(\frac{R}{H}y\right)^2 dy.
\end{align*}
$$

Thus, the volume of the cone is

$$
\begin{align*}
V &= \int dV
&= \int_{y=0}^H \pi \frac{R^2}{H^2} y^2 dy
&= \frac{\pi R^2}{H^2} \left(\frac{y^3}{3} \bigg\vert_{y=0}^H \right)
&= \pi \frac{R^2}{H^2} \cdot \frac{H^3}{3}
&= \frac{1}{3} \pi R^2 H.
\end{align*}
$$

**Example**

Find the volume of a square pyramid of base edge $$S$$ and height $$H$$.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Again, use slices parallel to the base. Let $$y$$ be the distance from the tip of the cone to the center of the slice (so $$y$$ ranges from 0 to $$H$$), and let $$x$$ be half of the side length of the slice.

As shown in the above cutaway, one finds by similar triangles that $$\frac{x}{y} = \frac{S/2}{H}$$, and so $$x = \frac{S}{2H}y$$. Therefore, the area of a slice is $$(2x)^2 = \frac{S^2}{H^2}y^2$$, and the thickness of a slice is $$dy$$, so the volume element is

$$
\begin{align*}
dV &= \frac{S^2}{H^2}y^2dy.
\end{align*}
$$

And so the volume of the pyramid is

$$
\begin{align*}
V &= \int dV
&= \int_{y=0}^H \frac{S^2}{H^2}y^2 dy
&= \frac{S^2}{H^2} \left(\frac{y^3}{3} \bigg\vert_{y=0}^H \right)
&= \frac{S^2}{H^2} \cdot \frac{H^3}{3}
&= \frac{S^2 H}{3}.
\end{align*}
$$

**Example**

Show that the volume of a generalized cone of base area $$B$$ and height $$H$$ is $$\frac{1}{3}BH$$. Explain the reason for the factor of $$\frac{1}{3}$$.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Let $$y$$ be the distance from the tip of the cone to the slice.

Because the linear dimensions of the slice grow proportionally with $$y$$ (e.g. the length of the slice is $$\frac{y}{H}$$ times the length of the base), the area of the slice will grow proportionally with the square of $$y$$. This means that

$$
\begin{equation*} \hbox{Area of the slice }= \left(\frac{y}{H}\right)^2 B \end{equation*}
$$

Thus, the volume element is $$dV=B \frac{y^2}{H^2} dy$$, and it follows that the volume of the cone is

$$
\begin{align*}
V &= \int dV
&= \int_{y=0}^H B \frac{y^2}{H^2} dy
&= \frac{B}{H^2} \left(\frac{y^3}{3} \bigg\vert^H_{y=0}\right)
&= \frac{B}{H^2} \cdot \frac{H^3}{3}
&= \frac{1}{3}BH.
\end{align*}
$$

The factor of $$\frac{1}{3}$$ comes from the fact that the volume element is proportional to the square of $$y$$, hence the integral has a $$y^2$$, which produces a factor of $$\frac{1}{3}$$ by the power rule.

## Exercises

- Find the volume of the following solid: for $$1 \leq x < \infty$$, the intersection of the this solid with the plane perpendicular to the x-axis is a circular disc of radius $$e^{-x}$$.
- The base of a solid is given by the region lying between the y-axis, the parabola $$y=x^2$$, and the line $$y=16$$ in the first quadrant. Its cross-sections perpendicular to the y-axis are equilateral triangles. Find the volume of this solid.
- The base of a solid is given by the region lying between the y-axis, the parabola $$y=x^2$$, and the line $$y=4$$. Its cross-sections perpendicular to the y-axis are squares. Find the volume of this solid.
- Find the volume of the solid whose base is the region enclosed by the curve $$y=\sin x$$ and the x-axis from $$x=0$$ to $$x=\pi$$ and whose cross-sections perpendicular to the x-axis are semicircles.
- Consider a cone of height $$h$$ over a circular base of radius $$r$$. We computed the volume by slicing parallel to the base. What happens if instead we slice orthogonal to the base? What is the volume element obtained by taking a wedge at angle $$\theta$$ of thickness $$d\theta$$ ?
- Consider the following solid, defined in terms of polar coordinates: $$0\leq r\leq R$$; $$0\leq\theta\leq 2\pi$$; $$0\leq z\leq r$$. Can you describe this shape? Compute its volume.
- Consider the following solid, defined in terms of polar coordinates: $$0\leq r\leq R$$; $$0\leq\theta\leq 2\pi$$; $$0\leq z\leq \theta$$. Can you describe this shape? Compute its volume.
- Challenge: compute the volume intersection of the (infinite) cylinders of radius $$R$$ centered along the x and y axes in 3-d. That is, compute the volume of intersection of 

$$
\begin{align*}
x^2 + z^2 &\leq R^2
x^2 + z^2 &\leq R^2
\end{align*}
$$

in the 3-dimensional $$(x,y,z)$$ space. 