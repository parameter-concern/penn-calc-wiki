---
title: Higher derivatives
description: Definition and interpretation of higher derivatives
lecture_number: 13
topic_number: 2
layout: lecture
mathjax: true
---
The ($n$)th derivative of a function ($f(x)$), denoted ($f^{\left(n\right)}(x)$) or ($\frac{d^n}{dx^n}(f)$), is defined recursively by

(:latex:) \begin{align*} f^{\left(n\right)}(x) &= \frac{d}{dx}f^{\left(n-1\right)}(x). \end{align*} (:latexend:)

In other words, the ($n$)th derivative is what one gets by taking the derivative ($n$) times. Note that in the ($\frac{d}{dx}$) notation, the power ($n$) goes to the right of ($dx$), to emphasize the fact that the ($n$)th derivative of ($f$) is achieved by iterating ($n$) times the operator ($\frac{d}{dx}$). So

(:latex:) \[ \left( \frac{d}{dx}\right)^n f = \frac{d^n}{dx^n} f. \] (:latexend:)
Interpretations

Let ($x(t)$) denote the position of a moving body as a function of time. Then the velocity ($v(t)$) of the body is

(:latex:) \[ v(t) = \frac{dx}{dt}. \] (:latexend:)

The acceleration of an object is the second derivative of its position function (i.e. the derivative of its velocity):

(:latex:) \[ a(t) = \frac{dv}{dt} = \frac{d}{dt}\left(\frac{dx}{dt}\right) = \frac{d^2x}{dt^2}. \] (:latexend:)

The jerk of an object is the third derivative of its position function (i.e. the derivative of its acceleration):

(:latex:) \[ j(t) = \frac{d^3x}{dt^3}. \] (:latexend:)

The snap (or jounce) of an object is the fourth derivative of its position:

(:latex:) \[ s(t) = \frac{d^4x}{dt^4}. \] (:latexend:)
Quadrotors

The maneuverability of nano quadrotors depends on controlling both the jerk and the snap (in addition to velocity and acceleration).
Curvature

In geometry, curvature can (informally) be thought of as how quickly the graph of the function curves. Consider the largest circle that can comfortably sit tangent to the graph of ($f$) at the point ($a$). Intuitively, the larger the radius ($R$) of the circle that fits, the smaller the curvature. Here is a curve with several of these circles (called osculating circles) drawn it at different indicated points.

In fact, the curvature of a curve ($f$), denoted ($\kappa$), is defined by ($\kappa = \frac{1}{R}$), where ($R$) is the radius of the largest circle which fits the curve to second order. With some algebra, one finds the following expression for curvature in terms of the first and second derivatives of ($f$):

Curvature of a function ($f$)

(:latex:) \[ \kappa = \frac{|f''|}{(1+(f')^2)^{3/2}}. \] (:latexend:)

(:toggle hide show="Justification" box1:)

For a given point on the curve, draw its osculating circle, say of radius ($R$) (right now, ($R$) is unknown to us;we will eventually find ($R$)). Then place the coordinate axes so that the origin is at the center of the circle (note that the curvature at a given point only depends on the radius of the osculating circle, which is independent of where the axes are placed):

The equation of the osculating circle is ($x^2+y^2 = R^2$). Solving for ($y$) gives

(:latex:) \[ y = \sqrt{R^2-x^2} = (R^2-x^2)^{1/2}, \] (:latexend:)

whose first and second derivatives should respectively match the first and second derivatives of the function ($f$) at the point (that is what it means for the circle to match the function up to second order). Remember that the first derivative and second derivative of ($f$) at the given point are just constants. We will set the derivative and second derivative of the equation of the circle equal to these constants, respectively, and then solve for ($R$).

The first derivative of the equation of the circle is

(:latex:) \begin{align*} \frac{d}{dx} (R^2-x^2)^{1/2} &= \frac{1}{2}(R^2-x^2)^{-1/2}(-2x)
&= -x(R^2-x^2)^{-1/2}. \end{align*} (:latexend:)

The second derivative of the equation of the circle (using the product rule) is

(:latex:) \begin{align*} \frac{d}{dx} \left(-x(R^2-x^2)^{-1/2} \right) &= -(R^2-x^2)^{-1/2} - x \left(-\frac{1}{2}\right)(R^2-x^2)^{-3/2}(-2x)
&= -(R^2-x^2)^{-1/2} - x^2 (R^2-x^2)^{-3/2}
&= - \frac{1}(R^2-x^2)^{1/2}} - \frac{x^2}{(R^2-x^2)^{3/2}}
&= - \frac{\left(R^2-x^2\right){(R^2-x^2)^{3/2}} - \frac{x^2}{(R^2-x^2)^{3/2}}
&= \frac{-R^2}{(R^2-x^2)^{3/2}}
&= -R^2 (R^2-x^2)^{-3/2}. \end{align*} (:latexend:)

So setting the corresponding derivatives of ($f$) equal to the derivatives of the circle gives

(:latex:) \begin{align*} f' &= -x(R^2 - x^2)^{-1/2}
f'' &= -R^2(R^2-x^2)^{-3/2}. \end{align*} (:latexend:)

Now we do some algebra to solve for ($R$) in terms of ($f'$) and ($f''$). Squaring the first equation gives

(:latex:) \[ (f')^2 = x^2(R^2-x^2)^{-1}. \] (:latexend:)

Solving this equation for ($x^2$) gives

(:latex:) \[ x^2 = \frac{(f')^2 R^2}{1+(f')^2}. \] (:latexend:)

Plugging this into the second equation, and doing some algebra gives

(:latex:) \begin{align*} f'' &= -R^2(R^2-x^2)^{-3/2}
&= -R^2 \left( R^2 - \frac{(f')^2 R^2}{1+(f')^2} \right)^{-3/2}
&= -R^2 \left[ R^2 \left(1-\frac{(f')^2}{1+(f')^2} \right)\right]^{-3/2}
&= \frac{-R^2}{R^3} \left(\frac{1+(f')^2 - (f')^2}{1+(f')^2}\right)^{-3/2}
&= -\frac{1}{R} \left(1+(f')^2 \right)^{3/2}. \end{align*} (:latexend:)

Taking absolute values (since the radius of a circle should not be negative) gives

(:latex:) \[ |f''| = \frac{1}{R} \left(1+(f')^2 \right)^{3/2}. \] (:latexend:)

Now, solving for ($\kappa = \frac{1}{R}$) gives

(:latex:) \begin{align*} \kappa = \frac{1}{R} = \frac{|f''|}{(1+(f')^2)^{3/2}}, \end{align*} (:latexend:)

as desired.

Note that for a straight line, the second derivative ($f''=0$), and so ($\kappa = 0$), which matches intuition. In this case, the osculating circle is infinite. Similarly, ($\kappa=0$) at inflection points of ($f$).
Elasticity

Consider an elastic beam with uniform cross section and static load ($q(x)$), where ($x$) is the location of the load along the beam. Then the deflection ($u(x)$) (the amount the beam sags at location ($x$)) satisfies the equation

(:latex:) \[ EI \frac{d^4u}{dx^4} = q(x), \] (:latexend:)

where ($E$) and ($I$) are constants: ($E$) is the constant of elasticity (depends on the material), and ($I$) is the moment of inertia (depends on the shape of the beam).
Taylor series

As seen in previous modules, information about the derivatives of a function evaluated at a single point gives information about the function for inputs near that point via the Taylor series:

(:latex:) \[ f(x) = f(a) + f'(a)(x-a) + \frac{f(a)}{2!} (x-a)^2 + \frac{f'(a)}{3!}(x-a)^3 + \dotsb \] (:latexend:)

Taking a few terms of this series gives a polynomial which is a good approximation of ($f$) near ($a$). The more derivatives one knows, the more terms one can include in the series, and the better the approximation.
Bonus: another look at Taylor series

Consider the alternative way to express the Taylor series, in terms of the distance ($h$) from the base point ($a$):

(:latex:) \begin{align*} f(a+h) &= f(a) + f'(a)h + \frac{f(a)}{2!}h^2 + \frac{f'(a)}{3!}h^3 + \dotsb
&= \sum_{k=0}^\infty \frac{f^{\left(k\right)}(a)}{k!}h^k
&= \sum_{k=0}^\infty \frac{h^k}{k!} \left(\frac{d}{dx} \bigg|_a \right)^k f
&= \sum_{k=0}^\infty \frac{1}{k!} \left(h \frac{d}{dx} \bigg|_a \right)^k f. \end{align*} (:latexend:)

Note that this resembles the Taylor series for the exponential ($e^x$), where

(:latex:) \[ x = h \frac{d}{dx} \bigg|_a. \] (:latexend:)

This may seem a little unusual. But the idea of exponentiating an operator to get another operator is a useful tool, which comes up in other areas of mathematics. In this notation, we can write

(:latex:) \[ f(a+h) = e^{\left(h\left.\frac{d}{dx}\right|_a\right)} f. \] (:latexend:)

Another way to think of this is that ($e^{h \frac{d}{dx}}$) is the shift operator, which takes in the function ($f(x)$) and gives back the function ($f(x+h)$).
EXERCISES

    You are given the position, velocity and acceleration of a particle at time ($t = 0$). The position is ($p(0) = 2$), the velocity ($v(0) = 4$), and the acceleration ($a(0) = 3$). Using this information, which Taylor series should they use to approximate ($p(t)$), and what is the estimated value of ($p(4)$) using this approximation?
    If a particle moves according to the position function ($s(t) = t^3-6t$), what are its position, velocity and acceleration at ($t=3$) ?
    If the position of a car at time ($t$) is given by the formula ($p(t) = t^4 - 24t^2$), for which times ($t$) is its velocity decreasing?
    What is a formula for the second derivative of ($f(t) = t^2\sin 2t$)? Use this formula to compute ($f''(\pi/2)$).
    Use a Taylor series expansion to compute the third derivative of ($f(x) = \sin^3 \left(\ln(1+x) \right)$) at zero.
    What is the curvature of the graph of the function ($f(x) = -2\sin(x^2)$) at the point ($(0,0)$)? 