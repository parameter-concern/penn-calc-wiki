---
title: ODE Linearization
description: Solving harder differential equations
lecture_number: 20
topic_number: 3
layout: lecture
mathjax: true
---
We have seen techniques for solving two types of differential equations: separable and linear. Unfortunately, there are a lot of differential equations which do not fit into these categories. In some of these cases, we can use linearization to determine the behavior of such differential equations.
Oscillation

How does one model oscillation? It turns out that a first order differential equation will not work, but a second order (i.e. involving the second derivative) equation will:

(:latex:) \[ \frac{d^2x}{dt^2} = -a^2 x. \] (:latexend:)

Solving such an equation is beyond the scope of this course, but in a course on differential equations one finds the pair of solutions

(:latex:) \begin{align*} x &= C_1 \cos (at)
x &= C_2 \sin (at). \end{align*} (:latexend:)

For this course we will look at a simpler way to model oscillation.
Simple Oscillator

Consider a spinner where ($\theta(t)$) represents the angle the arrow makes with the positive x-axis at time ($t$). Then ($\theta$) increases linearly with ($t$) and whenever ($\theta$) gets to ($2\pi$), it goes back to 0:

(:toggle show show="Show oscillator" hide="Hide oscillator (to avoid hypnosis)" box1:)

This can be modeled by

(:latex:) \begin{align*} \frac{d\theta}{dt} &= a
\theta &= at + \theta_0 \, \mod 2\pi \end{align*} (:latexend:)

where ($\mod 2\pi$) means "take the remainder when divided by ($2\pi$)". Here ($a$) can be thought of as the frequency of the spinner (e.g. how many revolutions per minute it makes).
Coupled Oscillators

Now consider two simple oscillators, ($\theta_1$) and ($\theta_2$), with the same frequency ($a$), but which are slightly out of phase with each other (i.e. one arrow is slightly ahead of the other):

(:toggle show show="Show oscillators" hide="Hide oscillators (to avoid hypnosis)" box2:)

Now suppose these oscillators are coupled so that each exerts a small influence on the other (e.g. by connecting their axles with a rod). One way to represent this mathematically is to adjust the rates of change of the oscillators so that they are affected by the difference in angles:

(:latex:) \begin{align*} \frac{d\theta_1}{dt} &= a + \epsilon \sin(\theta_2-\theta_1)
\frac{d\theta_2}{dt} &= a - \epsilon \sin(\theta_2-\theta_1). \end{align*} (:latexend:)

Here, ($\epsilon$) is some small constant which represents the strength of the effect of the coupling. When ($\theta_2$) is bigger than ($\theta_1$), the above differential equations speed up ($\theta_1$) slightly and slow down ($\theta_2$) slightly. One can find by simulation that this coupling effect causes the oscillators to synchronize relatively quickly, depending on how big the phase is between them and how big ($\epsilon$) is:

(:toggle show show="Show oscillators" hide="Hide oscillators (to avoid hypnosis)" box3:)
Synchronization

To analyze the synchronization effect mathematically, consider the phase ($\varphi$) between the two oscillators:

(:latex:) \[ \varphi = \theta_2 - \theta_1. \] (:latexend:)

Looking at how the phase ($\varphi$) changes with respect to time gives

(:latex:) \begin{align*} \frac{d\varphi}{dt} &= \frac{d}{dt} \left(\theta_2 - \theta_1\right)
&= \frac{d\theta_2}{dt} - \frac{d\theta_1}{dt}
&= \left(a - \epsilon \sin(\theta_2-\theta_1)\right) - \left(a + \epsilon \sin(\theta_2-\theta_1) \right)
&= -2 \epsilon \sin(\theta_2 - \theta_1)
&= -2 \epsilon \sin(\varphi). \end{align*} (:latexend:)

This is a separable differential equation, but solving it to find ($\varphi$) as an explicit function of ($t$) is not so easy, and does not really help us understanding the synchronization phenomenon. But linearization will help us understand the synchronization effect and how quickly it occurs.
Linearization

Going back to the differential equation for the phase, suppose we replace ($\sin \varphi$) with its linearization:

(:latex:) \begin{align*} \frac{d\varphi}{dt} &= -2\epsilon \sin \varphi
&= -2\epsilon \left(\varphi + O(\varphi^3)\right)
& \approx -2\epsilon \varphi. \end{align*} (:latexend:)

This will be a good approximation assuming the phase is small (the oscillators are not too far out of sync). This is a familiar differential equation, which gives us the approximate solution

(:latex:) \[ \varphi(t) \approx \varphi_0 e^{-2\epsilon t}, \] (:latexend:)

where ($\varphi_0$) is the initial phase. This is called the linearized solution to the original differential equation. Here, the linearized solution predicts that the phase decays exponentially, which is consistent with the above simulation.
Equilibria

Another way to study differential equations and predict their behavior, is to study the equilibria of the equation. An equilibrium of the equation

(:latex:) \[ \dot{x} = f(x) \] (:latexend:)

(here, ($\dot{x} = \frac{dx}{dt}$)), is a solution ($x(t) = C$), C a constant, such that ($\dot{x} = 0$). In other words, an equilibrium is a root of ($f$). In terms of the differential equation, an equilibrium is a steady state where the quantity ($x$) does not change.

One way to find the equilibria of a differential equation is to plot the derivative of a function versus the function itself. From the phase differential equation above, we plot ($\dot{\varphi}$) on the y-axis and ($\varphi$) on the x-axis and look for roots:

The roots of this equation are the values of ($\varphi$) for which ($\sin \varphi = 0$). For the range of values in which we are interested, the roots are ($\varphi = -\pi,0,\pi$). The equilibrium at 0 is familiar, because that is the state of synchronization to which the above simulation converged. The other two correspond to a phase of ($\pi$), which means the oscillators are completely opposite one another (it is the same for ($-\pi$) since these angles are co-terminal).
Stable and Unstable

A logical question at this point is why did the above coupled oscillator simulation eventually synchronize rather than ending up in opposite directions?

In general, some equilibria are attractive in the sense that if the quantity ($x$) gets near such an equilibrium, it will be drawn towards it and stay at it. Some equilibria are repellent in the sense that even if ($x$) is very close to such an equilibrium, it will be pushed away from it. Formally,

Stable and Unstable Equilibria

An equilibrium ($C$) of the differential equation

(:latex:) \[ \frac{dx}{dt} = f(x) \] (:latexend:)

is stable if ($f'(C) < 0$) and is unstable if ($f'(C) > 0$).

It is best to make sense of these definitions visually. Plot ($\dot{x}$) versus ($x$). Then each root of this equation is an equilibrium. If the graph crosses from positive to negative (going from left to right), then the equilibrium is stable. If the graph crosses from negative to positive (again, from left to right), then the equilibrium is unstable:

Another way to think of stable and unstable equilibria is to visualize one ball sitting in a bowl, and another ball sitting on top of an inverted bowl:

Each of these balls is in equilibrium (it will stay where it is as long as it is not disturbed). But the ball in the bowl is stable because if we nudge it in either direction, it will return to its equilibrium. However, the ball on the inverted bowl is unstable because if it is nudged in either direction it will roll off the bowl.

Example

Find and classify the equilibria of the equation

(:latex:) \[ \frac{dx}{dt} = x^2-4x+3. \] (:latexend:) (:toggle hide show="Answer" box4:)

Here, ($f(x) = x^2-4x+3$). Factoring, one finds

(:latex:) \[ \frac{dx}{dt} = (x-1)(x-3). \] (:latexend:)

So the roots (and hence the equilibria) are ($x=1$) and ($x=3$). Taking the derivative, we find

(:latex:) \begin{align*} f'(x) &= 2x-4
f'(1) &= -2 < 0
f'(3) &= 2 > 0. \end{align*} (:latexend:)

Thus ($x=1$) is a stable equilibrium, and ($x=3$) is an unstable equilibrium.
EXERCISES

    The differential equation 

($ \displaystyle \frac{dx}{dt} = (e^x-1)(x-1) $)
has an equilibrium at ($x=0$). What is the linearized equation at this equilibrium? Hint: Taylor-expand the right hand side about zero.

    There is also an equilibrium at ($x=1$) in the equation above. What is the linearized equation at this equilibirum? Hint: let ($h=x-1$) be a local coordinate and compute ($\dot{h}=\dot{x}=\cdots$) by Taylor expanding the right hand side at ($x=1$).
    Recall from Lecture 18, Newton's Law of Heat Transfer, which states that 

($ \displaystyle \frac{dT}{dt} = \kappa ( A - T ), $)
where ($\kappa>0$) is a thermal conductivity constant and ($A$) is the (constant) ambient temperature. Find and classify the equilibria in this system (using the derivative of the right hand side at the equilibria, recall...). Wasn't that easy?

    Find and classify all the equilibria of the ODE 

($ \displaystyle \frac{dy}{dt} = -2y + y^2 + y^3 $)

    Recall from Lecture 19 how we computed the terminal velocity of a falling body with linear drag given by 

($ \displaystyle m\frac{dv}{dt} = mg - \kappa v , $)
where, of course, ($m$) is mass, ($g$) is gravitation, ($v$) is velocity, and ($\kappa>0$) is the drag coefficient. Can you see how easily one can solve for the equilibrium ($v_\infty = mg/\kappa$)? Do it!

    Very good. Now, let's use a more realistic model of drag that is quadratic as opposed to linear: 

($ \displaystyle m\frac{dv}{dt} = mg - \lambda v^2 , $)
where ($\lambda>0$) is a constant drag coefficient. This differential equation is not as easy to solve (but soon you will learn how). Is there is terminal velocity? What is it?

    Recall that with continuous compounding at an interest rate of ($r>0$), an investment ($I(t)$) with initial investment ($I_0=I(0)$) is ($I(t)=I_0e^{rt}$). What happens if you wish to withdraw funds from the investment at a rate of spending ($S$), where ($S>0$) is constant? The differential equation is: 

($ \displaystyle \frac{dI}{dt} = rI - S . $)
Your goals are as follow. You have an initial investment ($I_0$), and you cannot change it or the rate ($r$). You want to be able to spend as much as possible but you also don't want to ever spend all your money. What amount of spending rate ($S$) can you bear? Hint: if you're not sure what to do, find and classify the equilibria in this model and think about which initial conditions lead to which long-term behaviors.

    In our lesson, we looked at two oscillators with "sinusoidal" coupling. Other types of coupling are possible as well. Consider the system of two oscillators modeled by 

($ \displaystyle \frac{d\theta_1}{dt} = 2 + \epsilon(e^{\theta_1-\theta_2}-1) \quad ; \quad \frac{d\theta_2}{dt} = 2 + \epsilon(1-e^{\theta_1-\theta_2}) $)
Consider the phase difference ($\varphi = \theta_2 - \theta_1$). Note that ($\varphi=0$) (where the oscillators are coupled) is an equilibrium. What is the linearized equation for ($\varphi$) about ($0$)?
This looks intimidating, but is very straightforward. If you're not sure how to start, compute ($\displaystyle \frac{d\varphi}{dt}$). Then linearize this about ($\varphi=0$). 