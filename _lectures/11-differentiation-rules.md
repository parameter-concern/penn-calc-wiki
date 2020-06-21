---
title: Differentiation rules
description: Rules for differentiating combinations of functions
lecture_number: 11
topic_number: 2
layout: lecture
mathjax: true
---
Recall from the previous module the third definition given of the derivative, that

(:latex:) \[ f(x+h) = f(x) + \frac{df}{dx}h + O(h^2). \] (:latexend:)

The derivative can be thought of as a multiplier: a change of ($h$) to the input gets amplified by a factor of ($\frac{df}{dx}$) to become a change of ($\frac{df}{dx}h$) to the output. This interpretation helps make sense of the following rules.
Differentiation rules

Suppose ($u$) and ($v$) are differentiable functions of ($x$). Then the following rules (written using the shorthand differential notation) hold:
Linearity

(:latex:) \[ d(u+v) = du + dv \quad \hbox{ and } \quad d(c\cdot u) = c \cdot du, \] (:latexend:) where ($c$) is a constant.
Product

(:latex:) \[ d(u \cdot v) = u \cdot dv + v \cdot du. \] (:latexend:)
Chain

(:latex:) \[ d(u\circ v) = du \cdot dv. \] (:latexend:)

(:toggle hide show="Proof" box0:)
Linearity

Using the third definition of the derivative from the last module, we find

(:latex:) \begin{align*} (u+v)(x+h) &= u(x+h) + v(x+h)
&= u(x) + \frac{du}{dx}h + O(h^2) + v(x) + \frac{dv}{dx}h + O(h^2)
&= (u+v)(x) + \left(\frac{du}{dx}+\frac{dv}{dx}\right)h + O(h^2), \end{align*} (:latexend:)

as desired. Similarly,

(:latex:) \begin{align*} (c \cdot u)(x+h) &= c \cdot u(x+h)
&= c \left(u(x) + \frac{du}{dx}h + O(h^2)\right)
&= (c\cdot u)(x) + \left( c \frac{du}{dx}\right) h + O(h^2). \end{align*} (:latexend:)
Product

Again using the third definition of the derivative, we find

(:latex:) \begin{align*} (u\cdot v)(x+h) &= u(x+h)\cdot v(x+h)
&= \left(u(x) + \frac{du}{dx}h + O(h^2)\right)\cdot \left(v(x) + \frac{dv}{dx}h + O(h^2) \right)
&= u(x)v(x) + u(x)\frac{dv}{dx}h + v(x)\frac{du}{dx}h + O(h^2)
&= (u \cdot v)(x) + \left(u(x) \frac{dv}{dx} + v(x) \frac{du}{dx}\right)h + O(h^2), \end{align*} (:latexend:)

as desired.
Chain

The chain rule is justified similarly, with a little bit more algebra:

(:latex:) \begin{align*} (u \circ v)(x+h) &= u(v(x+h))
&= u\left(v + \frac{dv}{dx}h + O(h^2)\right). \end{align*} (:latexend:)

To simplify the notation temporarily, let ($\tilde h = \frac{dv}{dx}h + O(h^2)$). Then

(:latex:) \begin{align*} u(v+\tilde h) &= u(v) + \frac{du}{dv}\tilde h + O(\tilde h^2)
&= u(v) + \frac{du}{dv}\left(\frac{dv}{dx}h + O(h^2)\right) + O((\frac{dv}{dx}h + O(h^2))^2)
&= u(v) + \frac{du}{dv} \cdot \frac{dv}{dx} h + O(h^2), \end{align*} (:latexend:)

as desired.

Another common way to express the Chain rule, using the more traditional derivative notation, is

(:latex:) \begin{equation*} \frac{du}{dx} = \frac{du}{dv}\cdot \frac{dv}{dx}. \end{equation*} (:latexend:)
Caveat

Note that in the chain rule, the output of ($v$) is being plugged in as an input to ($u$). Therefore, in the above, if the derivative ($d(u \circ v)$) is being evaluated at ($x=a$), then ($du$) is evaluated at ($x=v(a)$) and ($dv$) is evaluated at ($x=a$). More explicitly,

(:latex:) \[ d(u \circ v) \bigg|_{x=a} = du \bigg|_{x=v(a)} \cdot dv \bigg|_{x=a}. \] (:latexend:)

Example Compute ($ \frac{d}{dx}\left(e^{\sin x}\right)$). (:toggle hide show="Answer" box2:)

In the above notation, ($u(x) = e^x$) and ($v(x) = \sin x$), and the question asks for the derivative ($d(u \circ v)$). Again, remembering to evaluate ($du$) at ($v(x)$), one finds that

(:latex:) \begin{align*} d\left(e^{\sin x}\right) &= d(e^x) \bigg|_{\sin(x)} d(\sin x)\bigg|_{x}
&= e^{\sin x} \cos x. \end{align*} (:latexend:)
Other rules

There are a few other differentiation rules commonly taught in a first year calculus class, which can all be proven using the rules from above.
Reciprocal

(:latex:) \[ d \left(\frac{1}{v}\right) = - \frac{1}{v^2} dv. \] (:latexend:)
Quotient

(:latex:) \[ d \left(\frac{u}{v}\right) = \frac{vdu - udv}{v^2}. \] (:latexend:)
Inverse

(:latex:) \[ d (u^{-1} ) = \frac{1}{du} \bigg|_{u^{-1}} \] (:latexend:)

Note: ($u^{-1}$) is the inverse of ($u$), not the reciprocal (which was covered above).

(:toggle hide show="Proof" box0a:)
Reciprocal

One can think of this as an application of the chain rule, by writing

(:latex:) \[ \frac{1}{v} = u \circ v \] (:latexend:)

where ($u(x) = \frac{1}{x}$). Or one can see it as a special case of the quotient rule.
Quotient

Let ($w = \frac{u}{v}$), so that ($u = w \cdot v$). By the product rule,

(:latex:) \[ du = w \cdot dv + v \cdot dw. \] (:latexend:)

Solving for ($dw$), replacing ($w$) with ($\frac{u}{v}$), and clearing fractions gives

(:latex:) \begin{align*} dw &= \frac{du - w \cdot dv}{v}
&= \frac{du - \frac{u}{v} dv}{v}
&= \frac{v \cdot du - u \cdot dv}{v^2}, \end{align*} (:latexend:)

as desired.
Inverse

Note that ($x = u \circ u^{-1}$) by the definition of the inverse of a function. Differentiating both sides of this equation, using the chain rule on the right, gives

(:latex:) \[ 1 = du \bigg|_{u^{-1}} d(u^{-1}) \bigg|_{x} \] (:latexend:)

Then solving for ($d(u^{-1})$) gives

(:latex:) \[ d(u^{-1}) = \frac{1}{du} \bigg|_{u^{-1}} \] (:latexend:)

as desired.

Example Show that

(:latex:) \[ \frac{d}{dx} \sec x = \sec x \tan x, \] (:latexend:)

using the reciprocal rule. (:toggle hide show="Answer" box1a:)

We find that

(:latex:) \begin{align*} \frac{d}{dx} \sec x &= \frac{d}{dx}\left(\frac{1}{\cos x}\right)
&= -\frac{1}{\cos^2x} (-\sin x)
&= \frac{1}{\cos x} \cdot \frac{\sin x}{\cos x}
&= \sec x \tan x. \end{align*} (:latexend:)

Example Show that

(:latex:) \[ \frac{d}{dx} \tan x = \sec^2 x, \] (:latexend:)

using the quotient rule. (:toggle hide show="Answer" box1b:)

We find that

(:latex:) \begin{align*} \frac{d}{dx}\tan x &= \frac{d}{dx} \frac{\sin x}{\cos x}
&= \frac{d(\sin x)\cos x - d(\cos x)\sin x}{\cos^2 x}
&= \frac{\sin^2x + \cos^2x}{\cos^2x}
&= \frac{1}{\cos^2x}
&= \sec^2 x. \end{align*} (:latexend:)

Example Show that

(:latex:) \[ \frac{d}{dx} \ln x = \frac{1}{x}, \] (:latexend:)

using the inverse derivative rule. (:toggle hide show="Answer" box1c:)

The inverse of the logarithm is the exponential, so ($u = e^x$) in the inverse rule. Thus,

(:latex:) \begin{align*} \frac{d}{dx} \ln x &= \frac{1}{d(e^x)} \bigg|_{\ln x}
&= \frac{1}{e^x} \bigg|_{\ln x}
&= \frac{1}{x}, \end{align*} (:latexend:)

as desired.
Bonus

There are operators in other areas of mathematics which act similarly to the derivative. Finding such similarities in disparate fields is useful, because theorems from one field can often be carried over to the other and proved using similar techniques. These connections give a deeper understanding of both fields.
Boundary of spaces

Consider the boundary of a space. Loosely speaking, the boundary of a space is its outline, border, or edge. Think of the boundary as an operator, denoted ($\partial$):

It turns out the the boundary operator ($\partial$) acts similarly to a derivative. In particular, there is a product rule for ($\partial$). But first, we need a notion of product for spaces.

The Cartesian product of two spaces ($X$) and ($Y$), denoted ($X \times Y$), is the set of ordered pairs ($(x,y)$) where ($x \in X$) and ($y \in Y$). This can be visualized by taking the first space and extruding it along the second space (easiest to visualize if the second space is a line segment), as in the following examples:

So the Cartesian product of two line segments is a filled in rectangle, and the Cartesian product of a disc and a line segment is a solid cylinder.

Now, consider the boundaries of these regions. The boundary of the filled in rectangle is its border, which can be thought of as the two vertical edges and the horizontal top and bottom edges. Note that this can be expressed as the boundary of the first segment times the second segment union the first segment times the boundary of the second segment:

Similarly, for the solid cylinder, the boundary is the union of the lateral area and the end caps. The lateral area is the Cartesian product of the circle with the line segment, which is the boundary of the disc times the line segment. The other piece (the end caps) is the disc times two points, which is the disc times the boundary of the line segment:

These examples suggest the (true) fact that for two spaces ($A$) and ($B$), one has

(:latex:) \[ \partial(A \times B) = \partial(A) \times B \cup A \times \partial(B). \] (:latexend:)

Thinking of the boundary operator ($\partial$) as the derivative, ($\times$) as multiplication, and ($\cup$) as addition, this is exactly like the product rule for functions given above. If you like this strange example, you may wish to take a course in Topology some day...
Lists

Consider a list of five distinct objects, all labeled with ($x$). We might symbolize this by ($x^5$). Now, consider the deletion operator ($D$) which deletes an object from the list. There are five different lists that might result (depending on which object was deleted), and this would logically be symbolized by ($5x^4$), under the convention that a plus ($+$) stands for "logical OR":

There is an entire calculus for lists and other grammatical constructs in Computer Science. As one simple example, how would we algebraicize the empty list? It has zero elements, so logically it should be expressed as ($x^0 = 1$). Now, let ($\mathcal{L}$) denote the collection of all finite lists. The trivial observation that any list is either empty or has a first element can be translated into an algebraic equation:

(:latex:) \[ \mathcal{L} = 1 + x \mathcal{L}. \] (:latexend:)

Here's the cool part...solve for ($\mathcal{L}$) and you get:

(:latex:) \[ \mathcal{L} = \frac{1}{1-x} = 1 + x + x^2 + x^3 + x^4 + \dotsb, \] (:latexend:)

the geometric series! Remember that plus mean "OR", so that this equation says any list is either the empty list, or the list of length 1, or the list of length 2, etc. If you find this sort of thing fun, you may wish to learn some Computer Science and some Analytic Combinatorics.
EXERCISES

    Find the derivative of ($f(x)= \sqrt{x}(2x^2-4x)$).
    Find the derivative of ($\displaystyle f(x) = 6x^4 -\frac{3}{x^2}-2\pi$).
    Find the derivative of ($f(x) = 7(x^3+4x)^5 \cos x$).
    Find the derivative of ($f(x) = (e^x + \ln x)\sin x$).
    Find the derivative of ($\displaystyle f(x) = \frac{\sqrt{x+3}}{x^2}$)
    Find the derivative of ($\displaystyle f(x) = \frac{\ln x}{\cos x}$).
    Find the derivative of ($\displaystyle f(x) = \frac{ \sqrt[3]{x} - 4}{x^3}$).
    Find the derivative of ($f(x)=\sin^3 (x^3)$).
    Find the derivative of ($f(x) = e^{-1/x^2}$).
    Use the information about functions ($f$) and ($g$) from the following table to compute the value of ($\displaystyle \left. \frac{d}{dx} \right|_{x=1}g(f(x))$). 

(:latex:)

			\[
			\begin{array}{|c|c|c|c|c|}\hline
			x& f(x) & f'(x) & g(x) & g'(x) \\ \hline
			-1 & 1 & 1 & 0 & 3 \\ \hline
			0 & 0 & 2 & 0 &  0\\ \hline
			1 & 2 & 3 & 2 &  0 \\ \hline
			2 & 3 & -1 & -1 & 2 \\ \hline
			3 & -1 & 0 & 3 & -1 \\ \hline
			\end{array}
			\]

(:latexend:)

    Suppose that a certain quantity ($A$) is a function of another quantity ($B$), which, in turn, depends on a third quantity ($C$). We know that ($B(C) = \sqrt{C}$). If the rate of change of ($A$) with respect to ($B$) is ($B^2$), what is the rate of change of ($A$) with respect to ($C$)?
    This problem concerns the boundary operator ($\partial$) from the bonus material. Denote by ($I$) the closed unit interval (0,1$). Then, as observed, ($\partial I = \{0\} \cup \{1\}$) is the union of two points. Let's get a little "creative". Denote by ($I^n$) the "($n$)-cube", that is, the Cartesian product of ($n$) intervals: ($I^n \, = \, I \times I \times \cdots \times I$). This is a well-defined and perfectly reasonable ($n$)-dimensional cube. (Just because you can't visualize doesn't mean it can't exist!) Note that ($I^1=I$) and ($I^0$) is a single point (a zero-dimensional cube!). As a step towards building a "calculus of spaces", let us write ($\partial I^1 = 2I^0 = 2$) as a way of saying that the boundary of an interval consists of two points and that ($I^0=1$). The boundary of an ($n$)-dimensional cube consists of a certain number of ($(n-1)$)-dimensional cubes (called "faces"). For example, a square ($I^2$) has four faces. Using what you know about derivatives, answer this: how many faces does ($I^n$) have? 