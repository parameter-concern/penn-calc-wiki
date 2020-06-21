---
title: Moments and gyrations
description: Moment of inertia and radius of gyration
lecture_number: 41
topic_number: 4
layout: lecture
mathjax: true
---
This module deals with the moment of inertia and the radius of gyration, which are two properties of an object with physical interpretations.
Moment of inertia

The moment of inertia of an object, usually denoted ($I$), measures the object's resistance to rotation about an axis. To get an intuitive understanding of moment of inertia consider swinging a hammer by its handle (higher moment of inertia, harder to swing) versus swinging a hammer by its head (lower moment of inertia, easier to swing). So moment of inertia depends on both the object being rotated and the axis about which it is being rotated.

(:toggle show show="Show graphic" hide="Hide graphic" boxhammer:)

Consider first a particle of mass. The bigger the mass, the more resistant it will be to rotation about an axis. Similarly, the further the particle is from the axis, the more resistant it will be to rotation. For a point mass, the moment of inertia is given by

(:latex:) \[ I = r^2 \, M, \] (:latexend:)

where ($r$) is the distance of the particle from the axis of rotation, and ($M$) is the mass of the particle:

(:toggle show show="Show graphic" hide="Hide graphic" boxparticle:)

The next question is how to calculate the moment of inertia when all the mass is not at a single point. As in previous modules, the method will be to break the object into slices of mass, and consider the contribution of each slice to the moment of inertia:

Each slice can be thought of as an individual particle of mass which contributes to the moment of inertia. The contribution of the slice becomes the moment of inertia element ($dI$):

(:latex:) \[ dI = r^2 \, dM. \] (:latexend:)

Example

Consider a solid disc of radius ($R$) and constant density ($\rho$) rotated about its central vertical axis:

(:toggle show show="Show graphic" hide="Hide graphic" boxdisc:)

Compute its moment of inertia.

(:toggle hide show="Answer" box1:)

Because the distance to the axis is part of the inertia element, a good area element to use is a vertical rectangle, where every point has the same distance to the center axis. Let ($x$) be the distance from the central axis to the rectangle (thus, ($r = x$)):

The area of this rectangle, as has been computed several times previously, is ($dA = 2 \sqrt{R^2-x^2} \, dx$). Then the mass element ($dM = \rho \, dA$), and it follows that

(:latex:) \begin{align*} dI &= r^2\, dM
&= 2 x^2 \rho \sqrt{R^2-x^2} \, dx. \end{align*} (:latexend:)

so integrating the inertia element gives

(:latex:) \begin{align*} I &= \int dI
&= \int_{x=-R}^R 2\rho x^2 \sqrt{R^2-x^2} \, dx
&= 4\rho \int_{x=0}^R x^2 \sqrt{R^2-x^2} \, dx \end{align*} (:latexend:)

(using the fact that the integrand is an even function allows the final step). Now the substitution ($x = R \sin \theta$), and some of the trig integral methods gives the answer ($\frac{\rho \pi}{4}R^4$), which can also be written ($\frac{1}{4}MR^2$), where ($M = \pi R^2 \rho$) is the mass of the disc.

Example

Consider a solid disc of radius ($R$) and constant density ($\rho$) rotated about its center:

(:toggle show show="Show graphic" hide="Hide graphic" boxdisccenter:)

Compute its moment of inertia.

(:toggle hide show="Answer" box2:)

In this example, a good area element to use is a ring (also called an annulus), because every point in a ring has the same distance to the origin, which is the axis of rotation (one can imagine the axis sticking out of the page perpendicular to the center of the disc):

As before, ($dM = \rho \, dA$). In this case, ($dA$) is the area of the ring, which is ($2\pi r \, dr$) (the circumference of the ring times the width of the ring). It follows that

(:latex:) \begin{align*} I &= \int dI
&= \int_{r=0}^R r^2 \rho 2\pi r \, dr
&= 2\pi \rho \int_{r=0}^R r^3 \, dr
&= 2\pi \rho \frac{r^4}{4} \bigg|_{r=0}^R
&= \frac{\pi \rho R^4}{2}. \end{align*} (:latexend:)

This can be expressed as ($\frac{1}{2}MR^2$), where ($M$) is again the mass of the disc. Note that the answer in this example is twice that of the previous example. This can be explained (using the answer from the previous example) by noting that ($r^2 = x^2+y^2$) in this example. Therefore,

(:latex:) \begin{align*} I &= \int r^2 \, dM
&= \int (x^2+y^2) \, dM
&= \int x^2 \, dM + \int y^2 \, dM, \end{align*} (:latexend:)

and these two integrals are, respectively, the moment of inertia about a vertical axis (from the previous example) and the moment of inertia about a horizontal axis. By symmetry, these are equal, which explains why this answer is twice the answer of the previous example.

Example

Consider a rectangle of length ($l$) and height ($h$). Compute the moment of inertia about the vertical axis through its center. Then compute the moment of inertia about the horizontal axis through its center. Hint: use symmetry to find the second answer from the first.

(:toggle hide show="Answer" box3:)

Center the rectangle at the origin. About the vertical axis, it is again best to use vertical rectangles. Let ($r$) denote the distance of this rectangle from the ($y$)-axis:

Then ($r = x$), and ($dM = \rho h \, dx$). Thus

(:latex:) \begin{align*} I &= \int dI
&= \rho h \int_{x=-l/2}^{l/2} x^2 \, dx
&= \rho h \frac{x^3}{3} \bigg|_{x=-l/2}^{l/2}
&= \frac{1}{12} \rho h l^3
&= \frac{1}{12} M l^2, \end{align*} (:latexend:)

where ($M = \rho l h$) is the mass of the rectangle. By symmetry, the moment of inertia about a horizontal axis through the center is ($\frac{1}{12}M h^2$).
Radius of gyration

Another property of an object, radius of gyration, denoted ($R_g$), can be expressed in terms of the moment of inertia. Imagine replacing the object being rotated about an axis by a single point mass being rotated about that same axis. The radius of gyration is the radius at which the point mass has the same moment of inertia as the object. More specifically, ($I = MR_g^2$), and solving for ($R_g$) gives

(:latex:) \[ R_g = \sqrt{\frac{I}{M}}. \] (:latexend:)

Note that because

(:latex:) \[ I = \int r^2 \, dM \] (:latexend:)

we can write

(:latex:) \begin{align*} R_g &=\displaystyle \sqrt{ \frac{ \int r^2 \, dM }{\int dM} }
&= \sqrt{ \overline{r^2} }
&= r_{RMS} \end{align*} (:latexend:)

So the radius of gyration is really the root mean square of the radius.
Higher mass moments

In the centroid module, we computed ($\int x \, dM$) as part of computing the ($x$)-coordinate of the center of mass, ($\overline x$).The moment of inertia ($I$) from this module is given by ($\int x^2 \, dM$). These are respectively known as the first mass moment and the second mass moment (first and second referring to the powers of ($x$)).

There are higher mass moments: ($\int x^n \, dM$), for ($n \geq 3$), as well as the lower mass moment ($\int x^0 dM$), which is just mass. These moments each give more information about how the mass of the object is distributed.

This is similar, in a sense, to how knowledge of the derivative of a function at a point leads to an approximation of the function using the Taylor series. The more derivatives one knows, the better the approximation. A logical question, then, is if one knows all the mass moments of an object, can one perfectly describe the distribution of mass?
Additivity of moments

One nice feature of moments is that, being integrals, they are additive. This means that a complex region can be split into simpler regions for which we already know the moment of inertia, and these moments can be added to find the moment of inertia for the entire region.

Example

Compute the moment of inertia for each of the following figures about a horizontal axis through their centers.

Which has the greater moment of inertia, the I-shaped figure or the H-shaped figure?

(:toggle hide show="Answer" box4:)

For the first figure, we can divide it into two rectangles (in light blue) and a square which are all being rotated about their horizontal center axis:

From the above example, we know that the moment of inertia for a rectangle about its horizontal axis is

(:latex:) \[ \frac{1}{12}M h^2 = \frac{1}{12} l h^3, \] (:latexend:)

where ($l$) is the length and ($h$) is the height of the rectangle. So for each of the tall rectangles we have ($I = \frac{1}{12} a^3 \frac{a-b}{2}$) and for the square in the middle we have ($I = \frac{1}{12}b^4$). Putting it together, we have the moment of inertia for the entire region is

(:latex:) \begin{align*} I &= 2 \cdot \frac{1}{12}a^3 \frac{a-b}{2} + \frac{1}{12}b^3 b
&= \frac{1}{12}(a^4-a^3b) + \frac{1}{12}b^4
&= \frac{1}{12}\left(a^4 + b^4 - a^3 b \right). \end{align*} (:latexend:)

For the other region, we cannot divide it up into rectangles in the same exact way, because we do not know the moment of inertia for a rectangle rotated about an axis other than one through its center. Instead, we can take the entire square of side length ($a$), and compute its moment of inertia. Then we can subtract off the inertia for the small rectangles we do not want to include, shown in red:

Again, using the fact from the previous example, the moment for the whole square is ($\frac{1}{12}a^4$), and the moment for each of the smaller rectangles (which we will subtract) is ($\frac{1}{12}\cdot \frac{a-b}{2} \cdot b^3$), so the moment of inertia for the whole region is

(:latex:) \begin{align*} I &= \frac{1}{12}a^4 - 2 \cdot \frac{1}{12} \cdot \frac{a-b}{2} \cdot b^3
&= \frac{1}{12} a^4 - \frac{1}{12} (ab^3 - b^4)
&= \frac{1}{12} (a^4 + b^4 - ab^3). \end{align*} (:latexend:)

So the I-shaped figure has the greater moment of inertia.

This is important when considering whether to use an H-beam or and I-beam in construction. According to a fact mentioned in higher derivatives, the deflection ($u(x)$) (the amount the beam sags at location ($x$)) satisfies the equation

(:latex:) \[ EI \frac{d^4u}{dx^4} = q(x), \] (:latexend:)

where ($E$) is the elasticity of the material (a constant), and ($q(x)$) is a static load at location ($x$) along the beam. Because the I-beam has the greater moment of inertia, it follows that their deflection will be less, and so I-beams are more common in building construction.
EXERCISES

    Consider a right triangle with vertices at (0,0), (5,0), (0,10). Consider rotating the triangle about the y-axis. The density is given by ($ \rho (x,y)=x $). Compute the moment of inertia. Compute the radius of gyration. 