---
title: Arclength
description: Finding the length along a curve
lecture_number: 35
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
Consider the graph of a function $$y = f(x)$$ for $$a \leq x \leq b$$. The purpose of this module is to find the length of this piece of the curve, known as the arclength of the function $$f$$ from $$a$$ to $$b$$.

As in previous modules, the basic method is to find the arclength element $$dL$$ and then integrate it:

$$
L = \int dL.
$$

By zooming in on a portion of the curve, it begins to look like a straight line. Then one can express $$dL$$ in terms of the infinitesimal horizontal change $$dx$$ and vertical change $$dy$$:

Now, by the Pythagorean theorem one finds that $$dL = \sqrt{dx^2+dy^2}$$. A little algebra and the chain rule gives that

$$
\begin{align*}
dL &= \sqrt{dx^2+dy^2}
&= \sqrt{dx^2+\left(\frac{dy}{dx}dx\right)^2}
&= \sqrt{1 + \left(\frac{dy}{dx}\right)^2}dx
&= \sqrt{1 + (f'(x))^2}dx.
\end{align*}
$$

So the arclength of the function $$f$$ from $$a$$ to $$b$$ is given by

$$
\begin{equation*} L = \int_a^b \sqrt{1+(f'(x))^2}dx. \end{equation*}
$$

**Example**

Find the arclength of the curve

$$
y = \ln \sin x; \quad \frac{\pi}{4} \leq x \leq \frac{\pi}{2}.
$$

Hint: recall the facts that

$$
\begin{align*}
1 + \cot^2 x &= \csc^2 x
\int \csc x \, dx &= -\ln\vert\csc x + \cot x\vert + C.
\end{align*}
$$

<button class="toggle" data-box="#box1a">Answer</button>

<div id="box1a" class="answer-hidden"></div>
{: id="box1a" class="answer-hidden"}


Computing the arclength element from the above formula gives

$$
\begin{align*}
dL &= \sqrt{1+\left(\frac{dy}{dx}\right)^2} \, dx
&= \sqrt{1 + \left(\frac{1}{\sin x} \cos x \right)^2} \, dx
&= \sqrt{1+ \cot^2 x} \, dx
&= \sqrt{\csc^2 x} \, dx
&= \csc x \, dx.
\end{align*}
$$

Therefore, we find that the arclength is

$$
\begin{align*}
L &= \int dL
&= \int_{x = \pi/4}^{\pi/2} \csc x \, dx
&= -\ln\vert \csc x + \cot x\vert \bigg\vert_{x=\pi/4}^{\pi/2}
&= -\ln(1 + 0) + \ln(\sqrt{2} + 1)
&= \ln(1+\sqrt{2}).
\end{align*}
$$

**Example**

Find the arclength of the curve

$$
y = x^2 - \frac{1}{8}\ln(x); \quad 1 \leq x \leq 4.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


First, one finds $$\frac{dy}{dx} = 2x - \frac{1}{8x}$$. So, with some careful algebra one sees that

$$
\begin{align*}
\sqrt{1+\left(\frac{dy}{dx}\right)^2} &= \sqrt{1+\left(2x-\frac{1}{8x}\right)^2}
&= \sqrt{1+(2x)^2 - 2\frac{2x}{8x} + \frac{1}{(8x)^2}}
&= \sqrt{1+(2x)^2-\frac{1}{2}+\frac{1}{(8x)^2}}
&= \sqrt{(2x)^2+\frac{1}{2}+\frac{1}{(8x)^2}}
\end{align*}
$$

Now note that by reversing the cancellation done in an earlier step when simplifying $$-2\frac{2x}{8x} = -\frac{1}{2}$$, one finds that $$\frac{1}{2} = 2\frac{2x}{8x}$$. And so, continuing the computation, one finds

$$
\begin{align*}
\sqrt{1+\left(\frac{dy}{dx}\right)^2} &= \sqrt{(2x)^2 + 2\frac{2x}{8x} + \frac{1}{(8x)^2}}
&= \sqrt{\left(2x+\frac{1}{8x}\right)^2}
&= 2x + \frac{1}{8x}.
\end{align*}
$$

Thus, $$dL = \left(2x+\frac{1}{8x}\right)dx$$, and it follows that

$$
\begin{align*}
L &= \int dL
&= \int_{x=1}^4 \left(2x+\frac{1}{8x}\right)dx
&= \left(x^2 + \frac{1}{8}\ln(x)\right)\bigg\vert_{x=1}^4
&= (16 + \frac{1}{8}\ln(4)) - (1+ \frac{1}{8}\ln(1))
&= 15 + \frac{\ln(4)}{8}.
\end{align*}
$$

Parametric curves

If a curve is defined parametrically, i.e. $$x = x(t)$$ and $$y = y(t)$$ for $$a \leq t \leq b$$, then the arclength element can be written as

$$
\begin{align*}
dL &= \sqrt{dx^2+dy^2}
&= \sqrt{\left(\frac{dx}{dt}dt\right)^2 + \left(\frac{dy}{dt}dt\right)^2} \\ &= \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} dt
&= \sqrt{x'(t)^2 + y'(t)^2} dt.
\end{align*}
$$

So the arclength of a parametric curve $$(x(t),y(t))$$ for $$a \leq t \leq b$$ is given by

$$
\begin{equation*} L = \int_a^b \sqrt{x'(t)^2+y'(t)^2}dt. \end{equation*}
$$

**Example**

Find the arclength for a circle of radius $$r$$.

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


A simple parametrization for the circle of radius $$r$$ is

$$
\begin{align*}
x &= r \cos t
y &= r \sin t.
\end{align*}
$$

Note that $$t$$ ranges from 0 to $$2\pi$$. Using the above formula, we find that the arclength element is

$$
\begin{align*}
dL &= \sqrt{ \left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} \, dt
&= \sqrt{ (-r\sin t)^2 + (r\cos t)^2} \, dt
&= \sqrt{ r^2(\sin^2 t + \cos^2 t)} \, dt
&= \sqrt{ r^2} \, dt
&= r \, dt.
\end{align*}
$$

(we used the Pythagorean identity $$\sin^2t + \cos^2t = 1$$ from line three to line four). Therefore,

$$
\begin{align*}
L &= \int dL
&= \int_{t = 0}^{2\pi} r \, dt
&= r \cdot t \bigg\vert_{t=0}^{2\pi}
&= 2 \pi r,
\end{align*}
$$

as desired.

**Example**

Find the arclength for the spiral $$x(t) = t\cos(t)$$, $$y(t) = t\sin(t)$$ for $$0 \leq t \leq 2\pi$$.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


First, compute $$x'(t) = \cos(t) -t\sin(t)$$ and $$y'(t) = \sin(t)+t\cos(t)$$. Then

$$
\begin{align*}
\sqrt{x'(t)^2+y'(t)^2} &= \sqrt{(\cos(t)-t\sin(t))^2 + (\sin(t)+t\cos(t))^2}
&= \sqrt{\cos^2(t) - 2t\cos(t)\sin(t) + t^2\sin^2(t) + \sin^2(t) + 2t\cos(t)\sin(t) + t^2\cos^2(t)}
&= \sqrt{1 + t^2}.
\end{align*}
$$

Thus, $$dL = \sqrt{1+t^2}dt$$. So one finds that

$$
\begin{align*}
L &= \int_0^{2\pi} \sqrt{1+t^2}dt.
\end{align*}
$$

This integral was computed in the Trigonometric Substitution module. The answer becomes

$$
\begin{align*}
L &= \left(\frac{1}{2} \sinh^{-1}(t) + \frac{1}{2}t\sqrt{1+t^2}\right) \bigg\vert_0^{2\pi}
&= \frac{1}{2}\sinh^{-1}(2\pi) + \pi \sqrt{1+4\pi^2}.
\end{align*}
$$

Additional Examples

**Example**

Compute the arclength of the curve

$$
y = \frac{2}{3}x^{3/2}; \quad 0 \leq x \leq 3
$$

<button class="toggle" data-box="#box3a0">Answer</button>

<div id="box3a0" class="answer-hidden"></div>
{: id="box3a0" class="answer-hidden"}


Computing the arclength element, we find

$$
\begin{align*}
dL &= \sqrt{1+ \left(\frac{dy}{dx}\right)^2} \, dx
&= \sqrt{1+ \sqrt{x}^2} \, dx
&= \sqrt{1+x} \, dx.
\end{align*}
$$

Therefore, the arclength is

$$
\begin{align*}
L &= \int dL
&= \int_{x=0}^3 \sqrt{1+x} \, dx
&= \frac{2}{3}(1+x)^{3/2} \bigg\vert_{x=0}^3
&= \frac{16}{3}-\frac{2}{3}
&= \frac{14}{3}.
\end{align*}
$$

**Example**

A catenary is the curve that is formed by hanging a cable between two towers. It is a fact that the rate of change of the slope of a hanging cable is proportional to the rate of change of arclength with respect to $$x$$. Mathematically,

$$
\frac{d}{dx} \left(\frac{dy}{dx}\right) = \kappa \cdot \frac{dL}{dx},
$$

for some constant $$\kappa$$. Use this fact to find the equation of the catenary. Then find the length of the catenary for $$-l \leq x \leq l$$.

<button class="toggle" data-box="#box3a">Answer</button>

<div id="box3a" class="answer-hidden"></div>
{: id="box3a" class="answer-hidden"}


Using the formula for the arclength element, the fact tells us that

$$
\frac{d}{dx}\left(\frac{dy}{dx}\right) = \kappa \sqrt{1+ \left(\frac{dy}{dx}\right)^2}
$$

Now, making a substitution of

$$
u = \frac{dy}{dx}
$$

simplifies the equation to become

$$
\frac{du}{dx} = \kappa \sqrt{1+u^2}.
$$

This is a separable differential equation. Separating and integrating gives

$$
\int \frac{du}{\sqrt{1+u^2}} = \int \kappa \, dx.
$$

The left side can be handled with either a trigonometric or hyperbolic trigonometric substitution. We take the latter approach, and let

$$
\begin{align*}
u &= \sinh t
du &= \cosh t \, dt.
\end{align*}
$$

So we have (remembering the Pythagorean identity for hyperbolic trigonometric functions from the trigonometric substitution module)

$$
\begin{align*}
\int \frac{du}{\sqrt{1+u^2}} &= \int \frac{\cosh t}{\sqrt{1+\sinh^2 t}} \, dt
&= \int \frac{\cosh t}{\sqrt{\cosh^2 t}} \, dt
&= \int \frac{\cosh t}{\cosh t} \, dt
&= \int dt
&= t
&= \arcsinh u
\end{align*}
$$

(we leave the constant of integration off for now since we will be integrating on the right side as well). On the right side, we have

$$
\int \kappa \, dx = \kappa x + C.
$$

Putting it together, we have

$$
u = \sinh(\kappa x + C).
$$

If we pick our coordinates so that $$x=0$$ occurs at the low point of the catenary, then note that at this point, we have

$$
u = \frac{dy}{dx} = 0,
$$

since the slope of the catenary is 0 at the low point. Using this fact and plugging in $$x=0$$ into the earlier equation gives

$$
u = \sinh(C) = 0
$$

and so $$C=0$$. This gives

$$
u = \frac{dy}{dx} = \sinh(\kappa x).
$$

Now integrating both sides gives

$$
y = \frac{1}{\kappa} \cosh(\kappa x) + C,
$$

where $$C = y_0$$ is the $$y$$ value of the low point of the catenary.

To find the length of the catenary, we have

$$
\begin{align*}
L &= \int dL
&= \int_{x = -l}^l \sqrt{1 + \left(\frac{dy}{dx}\right)^2} \, dx
&= \int_{x=-l}^l \sqrt{1+\sinh^2 \kappa x} \, dx
&= \int_{x=-l}^l \cosh \kappa x \, dx
&= \frac{1}{\kappa} \sinh \kappa x \bigg\vert_{x = -l}^l
&= \frac{1}{\kappa} \left(\sinh \kappa l - \sinh \kappa (-l) \right)
&= \frac{2}{\kappa} \sinh \kappa l.
\end{align*}
$$

since hyperbolic sine is an odd function. This grows very quickly as $$l$$ increases, because

$$
\frac{2}{\kappa} \sinh \kappa l \approx \frac{1}{\kappa} e^{\kappa l}.
$$

**Example**

Show that the spiral

$$
\begin{align*}
x &= \frac{1}{t} \cos t
y &= \frac{1}{t} \sin t
\end{align*}
$$

for $$2\pi \leq t$$ has infinite arclength.

<button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


Computing

$$
\begin{align*}
\frac{dx}{dt} &= \frac{-t \sin t - \cos t}{t^2}
\frac{dy}{dt} &= \frac{t \cos t - \sin t}{t^2}.
\end{align*}
$$

Plugging these into the formula for the arclength of a parametric curve and noting the cancellation of cross terms, we have

$$
\begin{align*}
dL &= \sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} \, dt
&= \sqrt{ \left(\frac{-t \sin t - \cos t}{t^2}\right)^2 + \left(\frac{t \cos t - \sin t}{t^2}\right)^2} \, dt
&= \sqrt{t^2 \cdot \frac{\sin^2t + \cos^2 t}{t^4} + \frac{\cos^2 t + \sin^2 t}{t^4}} \, dt
&= \sqrt{\frac{1}{t^2} + \frac{1}{t^4}} \, dt
&= \frac{\sqrt{t^2+1}}{t^2} \, dt.
\end{align*}
$$

Therefore, the arclength is

$$
\int_{t=2\pi}^\infty \frac{\sqrt{t^2+1}}{t^2} \, dt.
$$

This integral is difficult to compute exactly, but we only want to show it diverges, which is not as difficult. Note that

$$
\frac{\sqrt{t^2+1}}{t^2} \geq \frac{\sqrt{t^2}}{t^2} = \frac{t}{t^2} = \frac{1}{t}.
$$

And so by the dominance of definite integrals,

$$
\int_{t = 2\pi}^\infty \frac{\sqrt{t^2+1}}{t^2} \, dt \geq \int_{t = 2\pi}^\infty \frac{1}{t} \, dt
$$

but the integral on the right diverges to infinity by our earlier discussions of p-integrals. Thus, our integral on the left, being larger, also diverges to infinity.

## Exercises

- Compute the arclength of $$y=\frac{x^3}{3}+\frac{1}{4x}$$, from $$x=1$$ to $$x=2$$. 