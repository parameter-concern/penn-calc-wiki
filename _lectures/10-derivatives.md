---
title: Derivatives
description: Definition and interpretations of the derivative
lecture_number: 10
topic_number: 2
layout: lecture
mathjax: true
---
There are several definitions of the derivative of a function ($f(x)$) at ($x=a$). These definitions are all equivalent, but they are all important because they emphasize different aspects of the derivative.

Derivative (first definition)

(:latex:) \begin{equation*} f'(a) = \frac{df}{dx} \bigg|_{x=a} = \lim_{x \rightarrow a} \frac{f(x)-f(a)}{x-a}. \end{equation*} (:latexend:)

If the limit does not exist, then the derivative is not defined at ($a$).

This first definition emphasizes that the derivative is the rate of change of the output with respect to the input. The next definition is similar.

Derivative (second definition)

(:latex:) \begin{equation*} f'(a) = \frac{df}{dx} \bigg|_{x=a} = \lim_{h \rightarrow 0} \frac{f(a+h)-f(a)}{h}. \end{equation*} (:latexend:)

If the limit does not exist, then the derivative is not defined at ($a$).

This definition can be interpreted as the change in output divided by the change in input, as the change in input goes to 0. One can see this is equivalent to the first definition by making the substitution ($h = x-a$). The third definition looks quite different from the first two.

Derivative (third definition)

The derivative of ($f(x)$) at ($x=a$), ($f'(a)$), is the constant ($C$) such that for any variation to the input ($h$), the following holds.

(:latex:) \begin{equation*} f(a+h) = f(a) + Ch + O(h^2). \end{equation*} (:latexend:)

That is, ($f'(a)$) is the first-order variation of the output. If no such ($C$) exists, then the derivative does not exist.

To show the equivalence, one can do a little algebra to see that

(:latex:) \[ \frac{f(a+h) - f(a)}{h} = C + O(h). \] (:latexend:)

Then taking the limit on both sides as ($h \rightarrow 0$) shows that ($C = f'(a)$).

Example Using the second and third definitions above, compute the derivative of ($f(x) = x^n$), where ($n$) is a positive integer. (:toggle hide show="Answer" box1:)

Using the binomial expansion and the above definition, one finds

(:latex:) \begin{align*} f'(a) &=\lim_{h \rightarrow 0} \frac(a+h)^n-a^n}{h}
&= \lim_{h \rightarrow 0} \frac{a^n +n a^{n-1}h +O(h^2) - a^n}{h}
&= \lim_{h \rightarrow 0} \frac{n a^{n-1} h+ O(h^2){h}
&= \lim_{h \rightarrow 0} na^{n-1} + O(h)
&= na^{n-1} \end{align*} (:latexend:)

Using the third definition, and again the binomial expansion, one writes

(:latex:) \begin{align*} f(a+h) &= (a+h)^n
&= a^n + na^{n-1}h + O(h^2), \end{align*} (:latexend:)

so ($f'(a) = na^{n-1}$).

Example Find the derivative of ($e^x$) using the third definition. (:toggle hide show="Answer" box1a:)

Note that ($e^{a+h} = e^a \cdot e^h$). Using our knowledge of the Taylor series for ($e^h$), we have

(:latex:) \begin{align*} e^{a+h} &= e^ae^h
&= e^a \left(1+h + O(h^2)\right)
&= e^a + e^ah + O(h^2), \end{align*} (:latexend:)

and so the derivative of ($e^x$), evaluated at ($x=a$), is ($e^a$).

Example Find the derivative of ($\cos x$) using the third definition. Hint: use the identity

(:latex:) \[ \cos (a+h) = \cos (a) \cos (h) - \sin (a) \sin (h). \] (:latexend:) (:toggle hide show="Answer" box1b:)

Using the above identity and our knowledge of Taylor series, we find

(:latex:) \begin{align*} \cos(a+h) &= \cos(a)\cos(h) - \sin(a)\sin(h)
&= \cos(a) \left(1 + O(h^2)\right) - \sin(a) \left(h + O(h^3)\right)
&= \cos(a) - \sin(a) h + O(h^2), \end{align*} (:latexend:)

so the derivative of ($\cos x$), evaluated at ($x=a$), is ($-\sin(x)$).

Example Find the derivative of ($f(x) = \sqrt{x}$) using the third definition. (:toggle hide show="Answer" box1c:)

First, write

(:latex:) \begin{align*} f(a+h) &= \sqrt{a+h}
&= \sqrt{a} \sqrt{1 + \frac{h}{a}}. \end{align*} (:latexend:)

Now, recalling the binomial series ($(1+x)^\alpha = 1 + \alpha x + O(x^2)$), we find

(:latex:) \begin{align*} \sqrt{a} \sqrt{1 + \frac{h}{a}} &= \sqrt{a} \left(1 + \frac{1}{2}\frac{h}{a} + O(h^2)\right)
&= \sqrt{a} + \frac{1}{2\sqrt{a}} h + O(h^2), \end{align*} (:latexend:)

and so the derivative of ($\sqrt{x}$), evaluated at ($x=a$), is ($\frac{1}{2 \sqrt{a}}$).
Notation

There are several different notations for the derivative of ($y=f(x)$). The best options are

(:latex:) \[ \frac{df}{dx} \quad \hbox{ or } \quad \frac{dy}{dx}, \] (:latexend:)

because they make it clear that the input is ($x$) and the output is ($f(x)$) or ($y$), respectively.

The next tier of options are fair, and have the advantage of requiring less writing, but they lose the benefit of knowing what the input variable is:

(:latex:) \[ f' \quad \hbox{ or } \quad \dot{y} \quad \hbox{ or } \quad df. \] (:latexend:)

The third option, ($df$), is known as differential notation, which will be covered more in a later module.

Do not try to cancel the d's in the derivative. Do not write the d's in cursive, or replace the d's with ($\Delta$)'s (those notations have a different meaning).
Interpretations

The derivative is commonly interpreted as the slope of the tangent line to the graph of the function. This is fine when the function has one input and one output. But what happens in the (more realistic) situation of a function with more than one input and more than one output? How does one graph such a function? And if the units of the input and output are different, what is the unit of slope?

A better interpretation for the derivative is as the rate of change of output with respect to input. This interpretation makes sense with functions of many inputs and outputs. However, that will be covered in the multivariable sequel to this course.
Examples with respect to time

The most common use of the derivative is with respect to time. Here are several such examples from different areas.
Physics

Velocity ($v(t)$) is the derivative of position ($x(t)$), with respect to time. Similarly, acceleration ($a(t)$) is the derivative of velocity with respect to time:

(:latex:) \[ v = \frac{dx}{dt} \quad \hbox{ and } \quad a = \frac{dv}{dt} \] (:latexend:)
Electromagnetism

Electric current, ($I$), in a circuit is the rate of change of charge, ($Q$), with respect to time:

(:latex:) \[ I = \frac{dQ}{dt}. \] (:latexend:)
Chemistry

The reaction rate for the product ($P$), denoted ($r_P$), in a chemical reaction is proportional to the rate of change of the concentration of ($P$), denoted ($\left[P\right]$), with respect to time:

(:latex:) \[ r_P = k \frac{d[P]}{dt}. \] (:latexend:)
Examples with respect to other variables
Spring constant

The spring constant ($k$) for a spring is the derivative of force with respect to deflection:

(:latex:) \[ k = \frac{d(\hbox{force})}{d(\hbox{deflection})}. \] (:latexend:)
Elasticity

The elasticity modulus ($\lambda$) of a material is the rate of change of stress with respect to strain:

(:latex:) \[ \lambda = \frac{d(\hbox{stress})}{d(\hbox{strain})}. \] (:latexend:)
Viscosity

The viscosity of a fluid ($\mu$) is related to the shear stress by the equation

(:latex:) \[ \hbox{shear stress} = \mu \frac{d(\hbox{velocity})}{d(\hbox{height})}. \] (:latexend:)
Tax rates

The marginal tax rate is the rate of change of tax with respect to income:

(:latex:) \[ \hbox{marginal tax rate} = \frac{d(\hbox{tax})}{d(\hbox{income})}. \] (:latexend:)
EXERCISES

    A rock is dropped from the top of a 320-foot building. The height of the rock at time ($t$) is given as ($s(t)=-8t^2+320$), where ($t$) is measured in seconds. Find the speed (that is, the absolute value of the velocity) of the rock when it hits the ground in feet per second. Round your answer to one decimal place.
    A very rough model of population size ($P$) for an ant species is ($P(t) = 2\ln(t+2)$), where ($t$) is time. What is the rate of change of the population at time ($t = 2$)?
    A particle's position, ($p$), as a function of time, ($t$), is represented by ($\displaystyle p(t) = \frac{1}{3}t^3 - 3t^2 + 9t$). When is the particle at rest?
    Hooke's law states that the force ($F$) exerted by an "ideal" spring displaced a distance ($x$) from its equilibrium point is given by ($F(x) = -kx$), where the constant ($k$) is called the "spring constant" and varies from one spring to another. In real life, many springs are nearly ideal for small displacements; however, for large displacements, they might deviate from what Hooke's law predicts. Much of the confusion between nearly-ideal and non-ideal springs is clarified by thinking in terms of series: for ($x$) near zero, ($F(x) = -kx + O(x^2)$). Suppose you have a spring whose force follows the equation ($F(x) = - 2 \tan 3x$). What is its spring constant?
    The profit, ($P$), of a company that manufactures and sells ($N$) units of a certain product is modeled by the function ($ P(N) = R(N) - C(N) $). The revenue function, ($R(N)=S\cdot N$), is the selling price ($S$) per unit times the number ($N$) of units sold. The company's cost, ($C(N)=C_0+C_\mathrm{op}(N)$), is a sum of two terms. The first is a constant ($C_0$) describing the initial investment needed to set up production. The other term, ($C_\mathrm{op}(N)$), varies depending on how many units the company produces, and represents the operating costs. Companies care not only about profit, but also "marginal profit", the rate of change of profit with respect to ($N$). Assume that ($S = \$50$), ($C_0 = \$75,000$), ($C_\mathrm{op}(N) = \$50 \sqrt{N}$), and that the company currently sells ($N=100$) units. Compute the marginal profit at this rate of production. Round your answer to one decimal place.
    In Economics, "physical capital" represents the buildings or machines used by a business to produce a product. The "marginal product of physical capital" represents the rate of change of output product with respect to physical capital (informally, if you increase the size of your factory a little, how much more product can you create?). A particular model tells us that the output product ($Y$) is given, as a function of capital ($K$), by ($ Y = A K^{\alpha} L^{1-\alpha} $), where ($A$) is a constant, ($L$) is units of labor (assumed to be constant), and ($\alpha$) is a constant between 0 and 1. Determine the marginal product of physical capital predicted by this model. 