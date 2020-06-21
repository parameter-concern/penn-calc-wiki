---
title: Arclength
description: Finding the length along a curve
lecture_number: 35
topic_number: 4
layout: lecture
mathjax: true
---
Consider the graph of a function ($y = f(x)$) for ($a \leq x \leq b$). The purpose of this module is to find the length of this piece of the curve, known as the arclength of the function ($f$) from ($a$) to ($b$).

As in previous modules, the basic method is to find the arclength element ($dL$) and then integrate it:

(:latex:) \[ L = \int dL. \] (:latexend:)

By zooming in on a portion of the curve, it begins to look like a straight line. Then one can express ($dL$) in terms of the infinitesimal horizontal change ($dx$) and vertical change ($dy$):

Now, by the Pythagorean theorem one finds that ($dL = \sqrt{dx^2+dy^2}$). A little algebra and the chain rule gives that

(:latex:) \begin{align*} dL &= \sqrt{dx^2+dy^2}
&= \sqrt{dx^2+\left(\frac{dy}{dx}dx\right)^2}
&= \sqrt{1 + \left(\frac{dy}{dx}\right)^2}dx
&= \sqrt{1 + (f'(x))^2}dx. \end{align*} (:latexend:)

So the arclength of the function ($f$) from ($a$) to ($b$) is given by

(:latex:) \begin{equation*} L = \int_a^b \sqrt{1+(f'(x))^2}dx. \end{equation*} (:latexend:)

Example

Find the arclength of the curve

(:latex:) \[ y = \ln \sin x; \quad \frac{\pi}{4} \leq x \leq \frac{\pi}{2}. \] (:latexend:)

Hint: recall the facts that

(:latex:) \begin{align*} 1 + \cot^2 x &= \csc^2 x
\int \csc x \, dx &= -\ln|\csc x + \cot x| + C. \end{align*} (:latexend:)

(:toggle hide show="Answer" box1a:)

Computing the arclength element from the above formula gives

(:latex:) \begin{align*} dL &= \sqrt{1+\left(\frac{dy}{dx}\right)^2} \, dx
&= \sqrt{1 + \left(\frac{1}{\sin x} \cos x \right)^2} \, dx
&= \sqrt{1+ \cot^2 x} \, dx
&= \sqrt{\csc^2 x} \, dx
&= \csc x \, dx. \end{align*} (:latexend:)

Therefore, we find that the arclength is

(:latex:) \begin{align*} L &= \int dL
&= \int_{x = \pi/4}^{\pi/2} \csc x \, dx
&= -\ln| \csc x + \cot x| \bigg|_{x=\pi/4}^{\pi/2}
&= -\ln(1 + 0) + \ln(\sqrt{2} + 1)
&= \ln(1+\sqrt{2}). \end{align*} (:latexend:)

Example

Find the arclength of the curve

(:latex:) \[ y = x^2 - \frac{1}{8}\ln(x); \quad 1 \leq x \leq 4. \] (:latexend:)

(:toggle hide show="Answer" box1:)

First, one finds ($\frac{dy}{dx} = 2x - \frac{1}{8x}$). So, with some careful algebra one sees that

(:latex:) \begin{align*} \sqrt{1+\left(\frac{dy}{dx}\right)^2} &= \sqrt{1+\left(2x-\frac{1}{8x}\right)^2}
&= \sqrt{1+(2x)^2 - 2\frac{2x}{8x} + \frac{1}{(8x)^2}}
&= \sqrt{1+(2x)^2-\frac{1}{2}+\frac{1}{(8x)^2}}
&= \sqrt{(2x)^2+\frac{1}{2}+\frac{1}{(8x)^2}} \end{align*} (:latexend:)

Now note that by reversing the cancellation done in an earlier step when simplifying ($-2\frac{2x}{8x} = -\frac{1}{2}$), one finds that ($\frac{1}{2} = 2\frac{2x}{8x}$). And so, continuing the computation, one finds

(:latex:) \begin{align*} \sqrt{1+\left(\frac{dy}{dx}\right)^2} &= \sqrt{(2x)^2 + 2\frac{2x}{8x} + \frac{1}{(8x)^2}}
&= \sqrt{\left(2x+\frac{1}{8x}\right)^2}
&= 2x + \frac{1}{8x}. \end{align*} (:latexend:)

Thus, ($dL = \left(2x+\frac{1}{8x}\right)dx$), and it follows that

(:latex:) \begin{align*} L &= \int dL
&= \int_{x=1}^4 \left(2x+\frac{1}{8x}\right)dx
&= \left(x^2 + \frac{1}{8}\ln(x)\right)\bigg|_{x=1}^4
&= (16 + \frac{1}{8}\ln(4)) - (1+ \frac{1}{8}\ln(1))
&= 15 + \frac{\ln(4)}{8}. \end{align*} (:latexend:)
Parametric curves

If a curve is defined parametrically, i.e. ($x = x(t)$) and ($y = y(t)$) for ($a \leq t \leq b$), then the arclength element can be written as

(:latex:) \begin{align*} dL &= \sqrt{dx^2+dy^2}
&= \sqrt{\left(\frac{dx}{dt}dt\right)^2 + \left(\frac{dy}{dt}dt\right)^2} \\ &= \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} dt
&= \sqrt{x'(t)^2 + y'(t)^2} dt. \end{align*} (:latexend:)

So the arclength of a parametric curve ($(x(t),y(t))$) for ($a \leq t \leq b$) is given by

(:latex:) \begin{equation*} L = \int_a^b \sqrt{x'(t)^2+y'(t)^2}dt. \end{equation*} (:latexend:)

Example

Find the arclength for a circle of radius ($r$).

(:toggle hide show="Answer" box2a:)

A simple parametrization for the circle of radius ($r$) is

(:latex:) \begin{align*} x &= r \cos t
y &= r \sin t. \end{align*} (:latexend:)

Note that ($t$) ranges from 0 to ($2\pi$). Using the above formula, we find that the arclength element is

(:latex:) \begin{align*} dL &= \sqrt{ \left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} \, dt
&= \sqrt{ (-r\sin t)^2 + (r\cos t)^2} \, dt
&= \sqrt{ r^2(\sin^2 t + \cos^2 t)} \, dt
&= \sqrt{ r^2} \, dt
&= r \, dt. \end{align*} (:latexend:)

(we used the Pythagorean identity ($\sin^2t + \cos^2t = 1$) from line three to line four). Therefore,

(:latex:) \begin{align*} L &= \int dL
&= \int_{t = 0}^{2\pi} r \, dt
&= r \cdot t \bigg|_{t=0}^{2\pi}
&= 2 \pi r, \end{align*} (:latexend:)

as desired.

Example

Find the arclength for the spiral ($x(t) = t\cos(t)$), ($y(t) = t\sin(t)$) for ($0 \leq t \leq 2\pi$).

(:toggle hide show="Answer" box2:)

First, compute ($x'(t) = \cos(t) -t\sin(t)$) and ($y'(t) = \sin(t)+t\cos(t)$). Then

(:latex:) \begin{align*} \sqrt{x'(t)^2+y'(t)^2} &= \sqrt{(\cos(t)-t\sin(t))^2 + (\sin(t)+t\cos(t))^2}
&= \sqrt{\cos^2(t) - 2t\cos(t)\sin(t) + t^2\sin^2(t) + \sin^2(t) + 2t\cos(t)\sin(t) + t^2\cos^2(t)}
&= \sqrt{1 + t^2}. \end{align*} (:latexend:)

Thus, ($dL = \sqrt{1+t^2}dt$). So one finds that

(:latex:) \begin{align*} L &= \int_0^{2\pi} \sqrt{1+t^2}dt. \end{align*} (:latexend:)

This integral was computed in the Trigonometric Substitution module. The answer becomes

(:latex:) \begin{align*} L &= \left(\frac{1}{2} \sinh^{-1}(t) + \frac{1}{2}t\sqrt{1+t^2}\right) \bigg|_0^{2\pi}
&= \frac{1}{2}\sinh^{-1}(2\pi) + \pi \sqrt{1+4\pi^2}. \end{align*} (:latexend:)
Additional Examples

Example

Compute the arclength of the curve

(:latex:) \[ y = \frac{2}{3}x^{3/2}; \quad 0 \leq x \leq 3 \] (:latexend:)

(:toggle hide show="Answer" box3a0:)

Computing the arclength element, we find

(:latex:) \begin{align*} dL &= \sqrt{1+ \left(\frac{dy}{dx}\right)^2} \, dx
&= \sqrt{1+ \sqrt{x}^2} \, dx
&= \sqrt{1+x} \, dx. \end{align*} (:latexend:)

Therefore, the arclength is

(:latex:) \begin{align*} L &= \int dL
&= \int_{x=0}^3 \sqrt{1+x} \, dx
&= \frac{2}{3}(1+x)^{3/2} \bigg|_{x=0}^3
&= \frac{16}{3}-\frac{2}{3}
&= \frac{14}{3}. \end{align*} (:latexend:)

Example

A catenary is the curve that is formed by hanging a cable between two towers. It is a fact that the rate of change of the slope of a hanging cable is proportional to the rate of change of arclength with respect to ($x$). Mathematically,

(:latex:) \[ \frac{d}{dx} \left(\frac{dy}{dx}\right) = \kappa \cdot \frac{dL}{dx}, \] (:latexend:)

for some constant ($\kappa$). Use this fact to find the equation of the catenary. Then find the length of the catenary for ($-l \leq x \leq l$).

(:toggle hide show="Answer" box3a:)

Using the formula for the arclength element, the fact tells us that

(:latex:) \[ \frac{d}{dx}\left(\frac{dy}{dx}\right) = \kappa \sqrt{1+ \left(\frac{dy}{dx}\right)^2} \] (:latexend:)

Now, making a substitution of

(:latex:) \[ u = \frac{dy}{dx} \] (:latexend:)

simplifies the equation to become

(:latex:) \[ \frac{du}{dx} = \kappa \sqrt{1+u^2}. \] (:latexend:)

This is a separable differential equation. Separating and integrating gives

(:latex:) \[ \int \frac{du}{\sqrt{1+u^2}} = \int \kappa \, dx. \] (:latexend:)

The left side can be handled with either a trigonometric or hyperbolic trigonometric substitution. We take the latter approach, and let

(:latex:) \begin{align*} u &= \sinh t
du &= \cosh t \, dt. \end{align*} (:latexend:)

So we have (remembering the Pythagorean identity for hyperbolic trigonometric functions from the trigonometric substitution module)

(:latex:) \begin{align*} \int \frac{du}{\sqrt{1+u^2}} &= \int \frac{\cosh t}{\sqrt{1+\sinh^2 t}} \, dt
&= \int \frac{\cosh t}{\sqrt{\cosh^2 t}} \, dt
&= \int \frac{\cosh t}{\cosh t} \, dt
&= \int dt
&= t
&= \arcsinh u \end{align*} (:latexend:)

(we leave the constant of integration off for now since we will be integrating on the right side as well). On the right side, we have

(:latex:) \[ \int \kappa \, dx = \kappa x + C. \] (:latexend:)

Putting it together, we have

(:latex:) \[ u = \sinh(\kappa x + C). \] (:latexend:)

If we pick our coordinates so that ($x=0$) occurs at the low point of the catenary, then note that at this point, we have

(:latex:) \[ u = \frac{dy}{dx} = 0, \] (:latexend:)

since the slope of the catenary is 0 at the low point. Using this fact and plugging in ($x=0$) into the earlier equation gives

(:latex:) \[ u = \sinh(C) = 0 \] (:latexend:)

and so ($C=0$). This gives

(:latex:) \[ u = \frac{dy}{dx} = \sinh(\kappa x). \] (:latexend:)

Now integrating both sides gives

(:latex:) \[ y = \frac{1}{\kappa} \cosh(\kappa x) + C, \] (:latexend:)

where ($C = y_0$) is the ($y$) value of the low point of the catenary.

To find the length of the catenary, we have

(:latex:) \begin{align*} L &= \int dL
&= \int_{x = -l}^l \sqrt{1 + \left(\frac{dy}{dx}\right)^2} \, dx
&= \int_{x=-l}^l \sqrt{1+\sinh^2 \kappa x} \, dx
&= \int_{x=-l}^l \cosh \kappa x \, dx
&= \frac{1}{\kappa} \sinh \kappa x \bigg|_{x = -l}^l
&= \frac{1}{\kappa} \left(\sinh \kappa l - \sinh \kappa (-l) \right)
&= \frac{2}{\kappa} \sinh \kappa l. \end{align*} (:latexend:)

since hyperbolic sine is an odd function. This grows very quickly as ($l$) increases, because

(:latex:) \[ \frac{2}{\kappa} \sinh \kappa l \approx \frac{1}{\kappa} e^{\kappa l}. \] (:latexend:)

Example

Show that the spiral

(:latex:) \begin{align*} x &= \frac{1}{t} \cos t
y &= \frac{1}{t} \sin t \end{align*} (:latexend:)

for ($2\pi \leq t$) has infinite arclength.

(:toggle hide show="Answer" box3b:)

Computing

(:latex:) \begin{align*} \frac{dx}{dt} &= \frac{-t \sin t - \cos t}{t^2}
\frac{dy}{dt} &= \frac{t \cos t - \sin t}{t^2}. \end{align*} (:latexend:)

Plugging these into the formula for the arclength of a parametric curve and noting the cancellation of cross terms, we have

(:latex:) \begin{align*} dL &= \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} \, dt
&= \sqrt{ \left(\frac{-t \sin t - \cos t}{t^2}\right)^2 + \left(\frac{t \cos t - \sin t}{t^2}\right)^2} \, dt
&= \sqrt{t^2 \cdot \frac{\sin^2t + \cos^2 t}{t^4} + \frac{\cos^2 t + \sin^2 t}{t^4}} \, dt
&= \sqrt{\frac{1}{t^2} + \frac{1}{t^4}} \, dt
&= \frac{\sqrt{t^2+1}}{t^2} \, dt. \end{align*} (:latexend:)

Therefore, the arclength is

(:latex:) \[ \int_{t=2\pi}^\infty \frac{\sqrt{t^2+1}}{t^2} \, dt. \] (:latexend:)

This integral is difficult to compute exactly, but we only want to show it diverges, which is not as difficult. Note that

(:latex:) \[ \frac{\sqrt{t^2+1}}{t^2} \geq \frac{\sqrt{t^2}}{t^2} = \frac{t}{t^2} = \frac{1}{t}. \] (:latexend:)

And so by the dominance of definite integrals,

(:latex:) \[ \int_{t = 2\pi}^\infty \frac{\sqrt{t^2+1}}{t^2} \, dt \geq \int_{t = 2\pi}^\infty \frac{1}{t} \, dt \] (:latexend:)

but the integral on the right diverges to infinity by our earlier discussions of p-integrals. Thus, our integral on the left, being larger, also diverges to infinity.
EXERCISES

    Compute the arclength of ($y=\frac{x^3}{3}+\frac{1}{4x}$), from ($x=1$) to ($x=2$). 