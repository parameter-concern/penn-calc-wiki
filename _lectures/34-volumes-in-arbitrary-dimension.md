---
title: Volumes in arbitrary dimension
description: Fourth dimension and beyond
lecture_number: 34
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
The motivation for this module is to find the volume (often referred to as hypervolume) of an object in dimension $$n$$. This has physical meaning for $$n\leq 3$$, but what happens for $$n \geq 4$$?
The cube in dimension $$n$$

Consider the unit cube (i.e. the cube of side length 1) in $$n$$ dimensions, sometimes called the $$n$$-hypercube or just the $$n$$-cube. Formally, this is defined to be the set of $$n$$-tuples (i.e. lists of length $$n$$) $$(x_1,x_2,\ldots,x_n)$$ such that $$0 \leq x_i \leq 1$$ for all $$1 \leq i \leq n$$. For $$n=0,1,2,3$$, these are familiar figures: the point, line segment, square, and cube, respectively.

Now, consider some of the various measurements for each of these cubes.
Volume of the cube

For $$n=0$$, the cube is just a point, and volume is defined to just be the number of points. So a single point has volume 1.

For $$n=1$$, the cube is a line segment. The volume in one dimension is just length, so the one dimension cube has volume 1.

For $$n=2$$, the cube is a square of side length 1. In two dimensions, volume is area, so the cube in two dimensions has volume $$ w \times h = 1 \times 1 = 1$$.

For $$n=3$$, the cube is a (traditional) cube of side length 1, which has (traditional) volume $$ l \times w \times h = 1 \times 1 \times 1 = 1$$.

For higher values of $$n$$, this pattern continues. The intuition is that each additional dimension adds an extra factor of 1, thus the volume of each unit $$n$$-cube is 1.
Surface area of cubes

Consider the surface area of the cube in dimension $$n$$. As with volume, this has physical meaning for $$n=2$$ and $$n=3$$.

For $$n=2$$, the surface area of a square is really its perimeter, which is 4.

For $$n=3$$, the surface area is the total area of the faces which bound the cube. There are 6 faces each with area 1, so the surface area is 6.

In general, the $$n$$ dimension cube will have $$2n$$ boundary faces, and each face is a cube of dimension $$n-1$$, so the surface area (really the hypervolume of the boundary) is $$2n$$.
Other features

The diagonal of the $$n$$-cube can be defined to be the distance from $$(0,0,\ldots,0)$$ to $$(1,1,\ldots,1)$$. Using the distance formula, one finds that the diagonal of the $$n$$-cube is $$\sqrt{n}$$.

The number of corners is fairly easy to count. For $$n=0,1,2,3$$, the number of corners is 1, 2, 4, and 8 respectively. Since the $$n$$-cube can be thought of as two copies of the $$(n-1)$$-cube, one can show by induction that there are $$2^n$$ corners in the $$n$$-cube.
Simplex

A simplex is a generalization of a triangle or a pyramid. In dimension $$n$$, the simplex is defined to be the set of $$n$$-tuples $$(x_1,x_2,\ldots,x_n)$$ such that $$0 \leq x_i \leq 1$$ and $$ \sum x_i \leq 1$$. This can be thought of as the corner of the $$n$$ dimension cube where the sum of the coordinates is less than 1. Here are the simplices of dimension $$n = 0,1,2,3$$:
Volume of spheres in arbitrary dimension

Now, consider a sphere of radius $$r$$ in $$n$$ dimensions. This is the set of points $$(x_1,x_2,\ldots,x_n)$$ such that $$x_1^2+x_2^2+\ldots+x_n^2 \leq r^2$$. Let $$V_n(r)$$ be the volume of the sphere of radius $$r$$ in $$n$$ dimensions (as above, volume means length, area, volume, hypervolume for $$n=1,2,3,\ldots$$, respectively). With some careful integration and induction, one finds that

$$
\begin{equation*} V_n(r) = \begin{cases} \frac{\pi^k}{k!} r^n & \hbox{if $n=2k$} \\ \frac{2^n \pi^k k!}{n!}r^n & \hbox{if $n=2k+1$} \end{cases}. \end{equation*}
$$

Now, note that as $$n \rightarrow \infty$$ (and $$r$$ stays fixed), the volume goes to 0 (since factorial grows faster than exponentials).

## Exercises

- Consider a four-dimensional box (or "rectangular prism") with side-lengths $$1$$, $$1/2$$, $$1/3$$, and $$1/4$$. What is the 4-dimensional volume of this box?
- What is the "diameter" -- i.e., the farthest distance between two points -- in this 4-d box? Hint: think in terms of diagonals.
- High-dimensional objects are everywhere and all about. Let's consider a very simple model of the space of digital images. Assume a planar digital image (such as that captured by a digital camera), where each pixel is given values that encode color and intensity of light. Let's assume that this is done via an RGB (red/green/blue) model. Though there are many RGB model specifications, let us use one well-suited for mathematics: to each pixel on associates three numbers $$(R,G,B)$$, each taking a value in $$ [0,1] $$. 

Since the red/green/blue values are independent, each pixel has associated to it a 3-d cube of possible color values. Consider a (fairly standard) 10-megapixel camera. If I were to consider the "space of all images" that my camera can capture, what does the space look like? How many dimensions does it have? Note: there's no calculus in this problem...just counting!

- Consider an $$n$$-dimensional "hypercube" $$C$$ of all side-lengths equal to $$1$$. Its $$n$$-dimensional volume is, clearly, $$1$$. Now consider what happens when you shrink the hypercube's side-lengths by $$1$$ percent (concentrically, so that the shrunken cube has the same center as the original) and remove it from the original cube. By subtracting the $$n$$-dimensional volume of this slightly smaller hypercube, conclude how much volume remains in the $$1$$-percent outer "shell".
- In the previous question, what happens to the volume of the $$1$$-percent shell as $$n\to\infty$$?
- We have seen that the $$n$$-dimensional volume of a unit radius ball in dimension $$n$$ converges to zero as $$n\to\infty$$. But what about a really large ball? For a ball of radius $$R=10^{10}$$ meters in dimension $$n$$, what is the limit as $$n\to\infty$$ of its volume? (in unit of meters-to-the-$$n^{th}$$)
- For the brave: so, as $$n\to\infty$$, the volume of the $$n$$-ball all concentrates near the surface shell. OK, you've got that. Now answer this: what proportion of the volume is concentrated along the "equatorial plane"? Let's make that specific. Recall, we computed the volume $$V_n$$ as $$I_n\cdot V_{n-1}$$, where 

$$ \displaystyle I_n = \int_{\theta=-\frac{\pi}{2}}^{\frac{\pi}{2}}\cos^n\theta\, d\theta. $$
We can compute the volume of the equatorial slice of thickness $$2\epsilon$$ (for some small but fixed $$\epsilon>0$$) as
$$ \displaystyle V_{n,2\epsilon} = V_{n-1}\int_{-\epsilon}^\epsilon\cos^n\theta\, d\theta . $$
So, here is the (hard!) problem. Compute the limit as $$n\to\infty$$ of the ratio of $$V_{n,2\epsilon}$$ to $$V_n$$:
$$ \displaystyle \lim_{n\to\infty} \frac{V_{n,2\epsilon}}{V_n} = \lim_{n\to\infty} \frac{1}{I_n}\int_{-\epsilon}^\epsilon\cos^n\theta\, d\theta . $$
If you can do this (a very big if...) you will get a surprise... 