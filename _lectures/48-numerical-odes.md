---
title: Numerical ODEs
description: Using sequences to solve ODEs
lecture_number: 48
topic_number: 5
layout: lecture
mathjax: true
---
The previous few modules have discretized functions, derivatives, and integrals. This module shows how discrete methods can be used to approximate solutions to problems in the continuous realm. One such application was Newton's method for approximating roots of functions, seen back in Linear Approximations. This module deals with approximating solutions of continuous differential equations.

In certain situations, differential equations can be solved exactly. For example, a separable differential equation

(:latex:) \[ \frac{dx}{dt} = f(x)g(t) \] (:latexend:)

is solved by rearranging and integrating, as seen in Antidifferentiation. A linear first order differential equation

(:latex:) \[ \frac{dx}{dt} = f(t)x + g(t) \] (:latexend:)

is solved by an application of the product rule, as seen in More differential equations. However, there are many differential equations of the form

(:latex:) \[ \frac{dx}{dt} = f(x,t) \] (:latexend:)

which cannot be solved exactly by the above methods. This is the situation where techniques known as numerical ordinary differential equations can be used to approximate a solution. There are three methods covered in this module:

    Euler's method
    Midpoint method
    Runge-Kutta method 

Euler's method

Euler's method uses a difference equation to approximate the solution of an initial value problem. More specifically, given the differential equation ($\frac{dx}{dt} = f(x,t)$), and initial value ($x_0 = x(t_0)$), Euler's method approximates ($x(t_\ast)$) for some ($t_\ast>t_0$).

One way to visualize the problem is to imagine a river where the water is going in different directions at different locations. If one drops something that floats (perhaps a very small rock, or a duck) at different locations in the river, where would the object end up further down the river?

To compute the approximation, first a positive integer ($N$) is chosen, and the ($t$) axis is split into ($N$) intervals, giving the sequence of time points ($t = (t_0,t_1,\ldots,t_N)$), where ($t_N = t_\ast$). The time step is ($h = \frac{t_\ast-t_0}{N}$). Then there is a corresponding sequence ($x = (x_0,x_1,\ldots, x_N)$) where ($x_0 = x(t_0)$) is the initial condition and each subsequent ($x_n$) is an approximation of ($x(t_n)$), given by the update rule

(:latex:) \begin{align*} x_{n+1} &= x_n + h f(x_n,t_n)
t_{n+1} &= t_n + h. \end{align*} (:latexend:)

This recurrence is sensible by considering the discretization of the original differential equation:

(:latex:) \begin{align*} \frac{dx}{dt} = f(x,t) \quad & \Rightarrow \quad \frac{\Delta x}{\Delta t} = f(x,t)
& \Rightarrow \quad \frac{x_{n+1}-x_n}{h} = f(x_n,t_n), \end{align*} (:latexend:)

and then rearranging.

This process is using a linearization at each point ($(t_n,x_n)$) to get to the next point ($(t_{n+1},x_{n+1})$), then this is repeated to get the next point, and so on:

Remember that a linearization is only good when the change in input, ($h$) in this case, is small. Therefore, a bigger value of ($N$) gives a better approximation, but requires more computation.

Example

Let ($\frac{dx}{dt} = x$) with ($x_0 = x(0) = 1$). Use Euler's method with ($N$) left as a variable to approximate ($x(1)$). What happens as ($N \rightarrow \infty$)?

(:toggle hide show="Answer" box2:)

Note that

(:latex:) \begin{align*} x_{n+1} &= x_n + \frac{x_n}{N}
&= x_n(1+\frac{1}{N}) \end{align*} (:latexend:)

(this is independent of ($t$)). Iterating this gives ($x_N = \left(1+\frac{1}{N}\right)^N \approx x(1)$). As ($N$) increases, the approximation gets better and better, and one finds that

(:latex:) \begin{align*} \lim_{N \rightarrow \infty} x_N &= \lim_{N \rightarrow \infty} \left(1+\frac{1}{N}\right)^N. \end{align*} (:latexend:)

Call this limit ($L$) and take the ($\ln$) of both sides. Then we find that

(:latex:) \begin{align*} \ln L &= \ln \left(\lim_{N \rightarrow \infty} \left(1+\frac{1}{N}\right)^N\right)
&= \lim_{N \rightarrow \infty} N \ln\left(1+\frac{1}{N}\right)
&= \lim_{N \rightarrow \infty} N \left(\frac{1}{N} + O\left(\frac{1}{N^2}\right) \right)
&= \lim_{N \rightarrow \infty} 1 + O\left(\frac{1}{N}\right)
&= 1. \end{align*} (:latexend:)

Therefore, ($L = e$). So ($x(1) = e$), which matches the value from solving the problem by separation of variables.

Example

Consider the differential equation

(:latex:) \[ \frac{dx}{dt} = t + x^2. \] (:latexend:)

Use Euler's method to estimate ($(t_\ast,x_\ast)$), where ($t_\ast = 1$), the initial conditions are ($t_0 = 0$) and ($x_0 = 1$), and the step size is ($h = \frac{1}{2}$).

(:toggle hide show="Answer" box3:)

Here, we have

(:latex:) \[ f(x,t) = t+x^2. \] (:latexend:)

So, using the initial conditions, we have

(:latex:) \[ f(x_0,t_0) = 0+1 = 1. \] (:latexend:)

Then we have that

(:latex:) \begin{align*} x_1 &= x_0 + h \cdot f(x_0,t_0)
&= 1 + \frac{1}{2} \cdot 1
&= \frac{3}{2}. \end{align*} (:latexend:)

And ($t_1 = \frac{1}{2}$). So

(:latex:) \begin{align*} f(x_1,t_1) &= t_1 + x_1^2
&= \frac{1}{2} + \left(\frac{3}{2}\right)^2
&= \frac{11}{4}. \end{align*} (:latexend:)

Thus,

(:latex:) \begin{align*} x_2 &= x_1 + h \cdot f(x_1,t_1)
&= \frac{3}{2} + \frac{1}{2} \cdot \frac{11}{4}
&= \frac{23}{8} \end{align*} (:latexend:)

And thus we have ($x_\ast = \frac{23}{8}$).
Taylor series perspective

If we think of ($x = x(t)$) as a function of ($t$), and expand the Taylor series of ($x$) about ($t = t_0$), we have

(:latex:) \begin{align*} x(t_0 + h) &= x(t_0) + h \cdot \frac{dx}{dt} \bigg|_{t=t_0} + O(h^2)
&= x_0 + h \cdot f(x_0,t_0) + O(h^2), \end{align*} (:latexend:)

so Euler's method can be seen as taking the first order Taylor approximation and using it to form the recursion relation. The above equation shows that the error for a single step is in ($O(h^2)$), so the error over all ($N$) steps is

(:latex:) \begin{align*} \hbox{Error} &= N \cdot O(h^2)
&= \frac{t_\ast - t_0}{h} \cdot O(h^2)
&= O(h). \end{align*} (:latexend:)
Midpoint method

Another method for solving the differential equation

(:latex:) \[ \frac{dx}{dt} = f(x,y) \] (:latexend:)

is known as the midpoint method. There is still an update rule which is similar to the one used in Euler's rule, but the function ($f$) is evaluated at a different point. The idea is to consider the point where Euler's rule would have taken us, and find the midpoint of that with our starting point. Use that midpoint as the point to evaluate ($f$) in the update rule.

As described, it is a little bit complicated, but with some extra notation and a diagram it becomes clearer. Let ($\kappa = h \cdot f(x_n,t_n)$). So ($\kappa$) is the quantity which would be added to ($x_n$) in the update rule for Euler's rule:

Then the eponymous midpoint which is used in the update rule is

(:latex:) \[ \left(t_n + \frac{h}{2},x_n + \frac{\kappa}{2}\right). \] (:latexend:)

So the update rule for the midpoint method is

(:latex:) \begin{align*} x_{n+1} &= x_n + h \cdot f \left( x_n + \frac{\kappa}{2}, t_n + \frac{h}{2}\right)
\kappa &= h \cdot f(x_n,t_n). \end{align*} (:latexend:)

The midpoint method is a bit more complicated than Euler's method, but it has a benefit. The midpoint method is a second order approximation, and as a result the error turns out to be ($O(h^3)$) for an individual step, and hence ($O(h^2)$) for the full approximation process. Therefore, it is a more accurate method of approximation.
Runge-Kutta method

The final method for solving the above differential equation is called the Runge-Kutta method. It is a fourth order approximation. Its error for an individual step is ($O(h^5)$) and for the whole process is ($O(h^4)$). This makes it the most accurate model of the three in this module. It is difficult to describe in an intuitive manner other than to say it is a sort of average of Euler's method, the midpoint method, and other methods. The update rule is as follows:

(:latex:) \begin{align*} x_{n+1} &= x_n + \frac{1}{6} \left(\kappa_1 + 2 \kappa_2 + 2 \kappa_3 + \kappa_4 \right)
\kappa_1 &= h \cdot f(x_n,t_n)
\kappa_2 &= h \cdot f \left(x_n + \frac{\kappa_1}{2},t_n + \frac{h}{2} \right)
\kappa_3 &= h \cdot f \left(x_n + \frac{\kappa_2}{2},t_n + \frac{h}{2}\right)
\kappa_4 &= h \cdot f \left(x_n + \kappa_3, t_n + h\right). \end{align*} (:latexend:)

Note that ($\kappa_1$) is the increase used in Euler's method, and ($\kappa_2$) is the increase used in the Midpoint method.
Comparison of methods

We already know that Euler's method is the most basic, then the Midpoint method, and finally Runge-Kutta. We should expect, then, that Runge-Kutta should give the best approximation, followed by the Midpoint method, followed by Euler's method.

Example

Use each of the three methods to approximate the solution of

(:latex:) \[ \frac{dx}{dt} = x \] (:latexend:)

with initial conditions

(:latex:) \begin{align*} t_0 &= 0 & x_0 &= 1
t_\ast &= 1 & x_\ast &= e \end{align*} (:latexend:)

(we already know that ($x_\ast = e$) because we have solved this differential equation several times already), using a step size of ($h=1$).

(:toggle hide show="Answer" box4:)

It may seem ill advised to use a step size equal to the distance from the start time to the end time, but this is just for the sake of comparison. Note that in this example,

(:latex:) \[ f(x,t) = x. \] (:latexend:)

Euler's method gives

(:latex:) \begin{align*} x_1 &= x_0 + h \cdot f(x_0,t_0)
&= 1 + 1 \cdot 1
&= 1+1, \end{align*} (:latexend:)

which is a pretty rough estimate of ($e$). From this computation we have that ($\kappa = 1$) for the midpoint method.

The Midpoint method gives

(:latex:) \begin{align*} x_1 &= x_0 + h \cdot f \left(x_0 + \frac{\kappa}{2}, t_0 + \frac{h}{2} \right)
&= 1 + 1 \cdot f \left(1 + \frac{1}{2}, 0 + \frac{1}{2}\right)
&= 1 + 1 \cdot \left(1+\frac{1}{2}\right)
&= 1 + 1 + \frac{1}{2}, \end{align*} (:latexend:)

so we see that we have gotten another term closer to ($e$).

For Runge-Kutta, we need to compute several different ($\kappa$)s. From the computations we did in Euler's method and the Midpoint method, we have that

(:latex:) \begin{align*} \kappa_1 &= 1
\kappa_2 &= \frac{3}{2}. \end{align*} (:latexend:)

Computing the other values, we have

(:latex:) \begin{align*} \kappa_3 &= h \cdot f \left( x_0 + \frac{\kappa_2}{2},t_0 + \frac{h}{2} \right)
&= 1 \cdot f \left(1 + \frac{3}{4},0 + \frac{1}{2}\right)
&= 1 + \frac{3}{4}
&= \frac{7}{4}. \end{align*} (:latexend:)

And

(:latex:) \begin{align*} \kappa_4 &= h \cdot f \left( x_0 + \kappa_3,t_0 + h \right)
&= 1 \cdot f \left(1 + \frac{7}{4}, 0 + 1\right)
&= 1+ \frac{7}{4}
&= \frac{11}{4}. \end{align*} (:latexend:)

Putting these together (and rearranging the fractions a little bit), we have that

(:latex:) \begin{align*} x_1 &= x_0 + \frac{1}{6}(\kappa_1 + 2 \kappa_2 + 2 \kappa_3 + \kappa_4)
&=1 + \frac{1}{6} \left(1 + 2 \cdot \frac{3}{2} + 2 \cdot \frac{7}{4} + \frac{11}{4}\right)
&=1 + \frac{1}{6} + \frac{1}{2} + \frac{7}{12} + \frac{11}{24}
&=1 + 1 + \frac{1}{2} + \frac{1}{6} + \frac{1}{24}, \end{align*} (:latexend:)

which has two more terms of ($e$), making it a very good approximation, despite only having one step.
EXERCISES

    Given ($\frac{dx}{dt} = x^3+x^2t$) with initial condition ($t_0 = 0, x_0=1$), approximate ($x(2)$) using the midpoint method with size step ($h=1$). 