---
title: Volumes of revolution
description: Volumes from revolving a region about an axis
lecture_number: 33
topic_number: 4
layout: lecture
mathjax: true
---
Volume element for solid of revolution

Consider a region ($R$) in the plane and a line ($L$). The solid of revolution of ($R$) about the axis ($L$) is the solid which results from taking the region ($R$) and revolving it around the line ($L$):

The result is typically something doughnut shaped. The question of this module is to find the volume of the solid:

The method is the same as the previous modules: find the volume element (the contribution of a small slice of the region to the total volume) and integrate. Just as area can be computed using vertical or horizontal slices, volume can be computed using corresponding methods: shells or washers, respectively.

The basic outline of finding the volume element for a solid of revolution is

    Find a convenient area element for the region ($R$) in the plane
    Determine the volume as that area element gets revolved around the axis ($L$). 

Cylindrical shells

When the area element is parallel to the axis of rotation, the volume element is a cylindrical shell. Here, the region is bounded by two parabolas. The natural area element for such a region is a vertical rectangle (shown in red). As the region is revolved about the ($y$)-axis, the volume element traces out a cylindrical shell, whose volume becomes the volume element of the solid of revolution.

Recall that a cylinder has lateral surface area ($2\pi r h$). The thickness of the cylindrical shell is ($dx$) (if the axis of rotation is a vertical line) or ($dy$) (if the axis of rotation is a horizontal line). Here ($r$) and ($h$) will generally be functions of ($x$) or ($y$) (again, depending on whether the axis of rotation is vertical or horizontal).

If a horizontal rectangle is the natural area element (for instance, the region between two horizontal parabolas), and the axis of revolution is the ($x$)-axis, then cylindrical shells again arise naturally as the volume element:

Example

Suppose the region bounded by ($y = 3x-x^2$) and ($y = x$) is revolved about the ($y$)-axis. What is the volume of the resulting solid? (:toggle hide show="Answer" box1:)

The first step in such a calculation is to draw a decent picture of the region. Then determine whether a vertical or horizontal rectangle would make the best area element. In this case, a vertical rectangle is the best choice.

Since a vertical rectangle is being revolved about a vertical axis, the result is a cylindrical shell:

The radius of the shell is ($x$) (the distance from the ($y$)-axis), and the height of the shell is the distance from the top curve to the bottom curve: ($h = (3x-x^2)-x = 2x-x^2$). The thickness of the shell is ($dx$). Recalling that the surface area of a cylinder is ($2\pi r h$), it follows that the volume element is just the surface area multiplied by the thickness ($dx$):

(:latex:) \begin{align*} dV &= 2\pi r h \, dx
&= 2 \pi x (2x-x^2) \, dx. \end{align*} (:latexend:)

A little algebra shows that the intersections occur at ($x=0$) and ($x=2$), so the volume is

(:latex:) \begin{align*} V &= \int dV
&= \int_{x=0}^2 2 \pi x(2x-x^2) \, dx
&= 2 \pi \int_{x=0}^2 (2x^2 - x^3) \, dx
&= 2 \pi \left(\frac{2}{3}x^3 - \frac{1}{4}x^4 \right) \bigg|_{x=0}^2
&= \frac{8}{3} \pi. \end{align*} (:latexend:)
Washers

When the area element is perpendicular to the axis of rotation, the volume element is a washer. So when the area element is a horizontal rectangle (as in a region bounded by horizontal parabolas) and the axis of revolution is vertical, the region traced out by the rectangle is a washer:

A washer is just an annulus (a circle with a circle cut out of it) which has been thickened. The volume of the washer is the area of the annulus times the thickness of the washer. The area of the annulus is ($\pi R^2 - \pi r^2$), where ($R$) is the radius of the outer circle and ($r$) is the radius of the inner circle. The thickness of the washer is ($dx$) or ($dy$) (depending on the orientation of the washer. Thus, the volume element when using washers is

(:latex:) \[ dV = \pi(R^2-r^2) \, \hbox{$dx$ or $dy$}. \] (:latexend:)

Example

Given the region bounded by ($y = 3x-x^2$) and ($y = x$), find the volume of the solid resulting from revolving the region about the ($x$)-axis. (:toggle hide show="Answer" box2:)

As in the previous example, the optimal area element is a vertical rectangle. A vertical rectangle revolved about a horizontal axis results in a washer:

The outer radius ($R$) is the upper curve: ($R = 3x-x^2$), and the inner radius ($r$) is the inner curve: ($r = x$). The thickness of the washer is ($dx$), and so

(:latex:) \begin{align*} dV &= \pi(R^2-r^2) \, dx
&= \pi((3x-x^2)^2-x^2)\, dx. \end{align*} (:latexend:)

As in the last example, the intersections are at ($x=0$) and ($x=2$), so

(:latex:) \begin{align*} V &= \int dV
&= \int_{x=0}^2 \pi(9x^2 - 6x^3+x^4 - x^2) \,dx
&= \pi \left( \frac{8}{3} x^3 - \frac{3}{2}x^4 + \frac{1}{5}x^5 \right) \bigg|_{x=0}^2
&= \frac{56}{15}\pi. \end{align*} (:latexend:)
Additional Examples

Example

Find the volume of a doughnut formed by rotating a disc of radius ($a$) about the y-axis. Let the radius of the doughnut be ($R$), as shown in this cutaway:

Use a vertical area element (which leads to a cylindrical shell).

(:toggle hide show="Answer" box3:)

First, suppose we use a vertical area element. Since we are rotating about a vertical axis, the area element and axis of rotation are parallel, and so the resulting volume element is a cylindrical shell. Let ($x$) be the distance of the area element (the rectangle) from the y-axis. This also happens to be the radius of the cylindrical shell:

The equation of the circle is

(:latex:) \[ (x-R)^2 + y^2 = a^2, \] (:latexend:)

and solving for ($y$) gives

(:latex:) \[ y = \pm \sqrt{a^2-(x-R)^2}. \] (:latexend:)

Therefore, the height of the area element (and hence the height of the cylindrical shell) is

(:latex:) \[ 2 \sqrt{a^2-(x-R)^2}. \] (:latexend:)

Now, the volume of the cylindrical shell (our volume element) is

(:latex:) \begin{align*} dV &= 2 \pi r h \, dx
&= 2 \pi x (2 \sqrt{a^2-(x-R)^2}) \, dx
&= 4 \pi x \sqrt{a^2 - (x-R)^2} \, dx. \end{align*} (:latexend:)

Note that ($x$) ranges from ($R-a$) to ($R+a$) as it sweeps across the circle. Therefore the volume is

(:latex:) \begin{align*} V &= \int dV
&= \int_{x = R-a}^{R+a} 4 \pi x \sqrt{a^2 - (x-R)^2} \, dx. \end{align*} (:latexend:)

This is a bit messy, but with a substitution of

(:latex:) \begin{align*} u &= x-R
du &= dx, \end{align*} (:latexend:)

we find

(:latex:) \begin{align*} \int_{x = R-a}^{R+a} 4 \pi x \sqrt{a^2 - (x-R)^2} \, dx &= \int_{u = -a}^a 4 \pi (u+R)\sqrt{a^2 - u^2} \, du
&= \int_{u=-a}^a 4 \pi u \sqrt{a^2-u^2} \, du + \int_{u=-a}^a 4 \pi R \sqrt{a^2-u^2} \, du. \end{align*} (:latexend:)

Here, we have used linearity to split the integral into two integrals. Notice that the first integrand is an odd function of ($u$), and since it is integrated over a symmetric interval, the first integral is 0:

(:latex:) \[ \int_{u=-a}^a 4 \pi u \sqrt{a^2-u^2} \, du = 0. \] (:latexend:)

The second integral can be found by noting that

(:latex:) \[ \int_{u=-a}^a 2 \sqrt{a^2-u^2} \, du \] (:latexend:)

gives the area of a disc of radius ($a$) (this was an integral done in the simple areas module). Therefore, the volume is

(:latex:) \begin{align*} \int_{u=-a}^a 4 \pi R \sqrt{a^2-u^2} \, du &= 2 \pi R \int_{u=-a}^a 2 \sqrt{a^2-u^2} \, du
&= 2\pi R (\pi a^2)
&= 2 \pi^2 R a^2. \end{align*} (:latexend:)

Example

Compute the volume of the doughnut again, this time using a horizontal area element (which leads to a washer).

(:toggle hide show="Answer" box4:)

Carefully drawing and labeling the outer and inner radii of the washer gives the following diagram:

The outer and inner radii can be found by solving the equation of the circle for ($x$):

(:latex:) \[ (x-R)^2 + y^2 = a^2 \quad \Rightarrow \quad x = R \pm \sqrt{a^2-y^2}. \] (:latexend:)

Thus, the volume element is the area of the washer times its thickness, ($dy$). Computing this and doing a little algebra gives

(:latex:) \begin{align*} dV &= \left[ \pi(R+\sqrt{a^2-y^2})^2 - \pi (R-\sqrt{a^2-y^2})^2 \right] \, dy
&= 4 \pi R \sqrt{a^2-y^2} \, dy. \end{align*} (:latexend:)

Note that ($y$) ranges from ($-a$) to ($a$), and so the volume integral is the same one arrived at above:

(:latex:) \begin{align*} V &= \int dV
&= \int_{y=-a}^a 4 \pi R \sqrt{a^2-y^2} \, dy
&= 2\pi R (\pi a^2)
&= 2 \pi^2 R a^2. \end{align*} (:latexend:)
EXERCISES

    Let ($D$) be the region bounded by the curve ($y = x^3$), the x-axis, the line ($x = 0$) and the line ($x = 2$). Find the volume of the region obtained by revolving ($D$) about the x-axis.
    Let ($D$) be the same region as above. What is the volume of the region formed by rotating this ($D$) about the line ($x = 3$)?
    Let ($D$) be the region between the curve ($y = -(x-2)^2+1$) and the x-axis. Find the volume of the region obtained by revolving ($D$) about the y-axis.
    Find the volume obtained by revolving the region between the curves ($y = x^3$) and ($y = \sqrt[3]{x}$) in the first quadrant about the x-axis.
    Let ($D$) be the region under the curve ($y = \ln \sqrt{x}$) and above the x-axis from ($x = 1$) to ($x = e$). Find the volume of the region obtained by revolving ($D$) about the x-axis.
    Let ($D$) be the region bounded by the graph of ($y = 1-x^4$), the x-axis and the y-axis in the first quadrant. Which of the following integrals can be used to compute the volume of the region obtained by revolving ($D$) around the line ($x=5$)?
    Challenge: compute the volume of the region obtained by rotating the disc ($x^2+y^2\leq\epsilon^2$) about the axis given by ($y=1-x$) for ($\epsilon\leq\frac{1}{2}$).
    Let ($D$) be the region under the curve ($ \sqrt{x-1} $) above the ($x$)-axis from ($x=1$) to ($x=2$). Compute the volume of solid obtained by rotating ($D $) about the ($x$)-axis. Compute the volume twice, using both methods. 