---
title: Partial fractions
description: Integration of rational functions using algebra
lecture_number: 24
topic_number: 3
layout: lecture
mathjax: true
---
So far, the techniques of integration covered in this course have all been derived from differentiation rules run in reverse. This module gives an algebraic method for integrating rational functions. Recall that a rational function is a function of the form

(:latex:) \[ f(x) = \frac{P(x)}{Q(x)}, \] (:latexend:)

where ($P(x)$) and ($Q(x)$) are polynomials. It turns out that with a little bit of algebraic manipulation, many of these integrals are not too difficult to compute.

Example

Compute

(:latex:) \[ \int \frac{3x^2-5}{x-2} \, dx. \] (:latexend:)

(:toggle hide show="Answer" box0:)

By doing polynomial long division on this ratio, we find

(For more on polynomial long division, see wikipedia).

The above observation, which is entirely based on algebra, allows us to evaluate the integral as

(:latex:) \begin{align*} \int \frac{3x^2-5}{x-2} \, dx &= \int \left(3x+6+ \frac{7}{x-2}\right) \, dx
&= \frac{3}{2}x^2 + 6x + 7 \ln|x-2| + C. \end{align*} (:latexend:)

The rest of this module expands on this method (in particular, when the denominator is of a higher degree), which is known as the method of partial fractions.
Partial fractions

Given a rational function ($\frac{P(x)}{Q(x)}$), and ($P$) has a lower power than ($Q$), the method of partial fractions uses algebra to rewrite the function as a sum of simpler terms which are easy to integrate. While there are some cases to deal with, the basic outline of the method is:

    Given the integral ($\int \frac{P(x)}{Q(x)} dx$) where ($P$) and ($Q$) are polynomials.
    Factor ($Q(x) = (x-r_1)(x-r_2)\ldots(x-r_n)$). Assume for now that each of these factors is distinct.
    We use the following fact, that the rational function can be expressed as 

(:latex:) \[ \frac{P(x)}{Q(x)} = \frac{A_1}{x-r_1} + \frac{A_2}{x-r_2}+\ldots + \frac{A_n}{x-r_n}. \] (:latexend:)

    Use algebra to find what each of the constants ($A_i$) is. This step requires the most work.
    Then 

(:latex:) \begin{align*} \int \frac{P(x)}{Q(x)}dx &= \int \left( \frac{A_1}{x-r_1} + \ldots + \frac{A_n}{x-r_n} \right) dx
&= A_1 \ln|x-r_1| + \ldots + A_n \ln|x-r_n| + C. \end{align*} (:latexend:)

Example

Compute

(:latex:) \[ \int \frac{3x-1}{x^2-2x-3}dx. \] (:latexend:) (:toggle hide show="Answer" box2:)

Factoring the denominator gives ($x^2-2x-3 = (x+1)(x-3)$). Thus, the goal is to find constants ($A$) and ($B$) such that

(:latex:) \begin{equation*} \frac{3x-1}{\left(x+1\right)\left(x-3\right)} = \frac{A}{x+1} + \frac{B}{x-3}. \end{equation*} (:latexend:)

There are several methods for finding the constants, but one of the simplest is to clear denominators, which gives

(:latex:) \begin{equation*} 3x-1 = A(x-3) + B(x+1). \end{equation*} (:latexend:)

This equation must hold for every value of ($x$). In particular, one can pick convenient values of ($x$) which make the algebra easy. In this case, by plugging in ($x=3$), the first term on the right disappears. Thus, the equation becomes ($8 = B \cdot 4$), and so ($B = 2$). Similarly, picking ($x = -1$) makes the second term on the right disappear. Thus, ($-4 = A \cdot (-4)$) so ($A = 1$). It follows that

(:latex:) \begin{align*} \int \frac{3x-1}{x^2-2x-3} dx &=\int \frac{3x-1}{\left(x+1\right)\left(x-3\right)} dx
&= \int \left(\frac{1}{x+1} + \frac{2}{x-3}\right)dx
&= \ln|x+1| + 2 \ln|x-3| + C. \end{align*} (:latexend:)

Example

Compute

(:latex:) \[ \int \frac{2x^2-6x-2}{x^3-x^2-2x}dx. \] (:latexend:) (:toggle hide show="Answer" box2a:)

Factoring the denominator gives

(:latex:) \[ x^3-x^2-2x = x(x+1)(x-2) \] (:latexend:)

So we are looking for constants ($A$), ($B$), and ($C$) such that

(:latex:) \[ \frac{2x^2 - 6x-2}{x(x+1)(x-2)} = \frac{A}{x} + \frac{B}{x+1} + \frac{C}{x-2}. \] (:latexend:)

Clearing fractions gives

(:latex:) \[ 2x^2-6x-2 = A(x+1)(x-2) + Bx(x-2) + Cx(x+1). \] (:latexend:)

Now, picking the following convenient values of ($x$) allows us to find each constant:

(:latex:) \begin{align*} x &= 0 & -2 &= -2A & A &= 1
x &= -1 & 6 &= 3B & B &=2
x &= 2 & -6 &= 6C & C &=-1. \end{align*} (:latexend:)

So we have that

(:latex:) \begin{align*} \int \frac{2x^2-6x-2}{x(x+1)(x-2)} &= \int \left(\frac{1}{x} + \frac{2}{x+1} - \frac{1}{x-2}\right) \, dx
&= \ln|x| + 2 \ln|x+1| - \ln|x-2| + C. \end{align*} (:latexend:)

Example

Compute

(:latex:) \[ \int \frac{x^2+2x-1}{2x^3+3x^2-2x} \, dx. \] (:latexend:) (:toggle hide show="Answer" box2b:)

Factoring gives

(:latex:) \[ 2x^3+3x^2-2x = x(2x-1)(x+2) \] (:latexend:)

So we are looking for constants ($A,B,C$) such that

(:latex:) \[ \frac{x^2+2x-1}{2x^3+3x^2-2x} = \frac{A}{x} + \frac{B}{2x-1} + \frac{C}{x+2}. \] (:latexend:)

As before, we clear fractions which gives

(:latex:) \[ x^2 + 2x -1 = A(2x-1)(x+2) + Bx(x+2) + Cx(2x-1). \] (:latexend:)

Now we pick convenient values of ($x$) to make the factors cancel and solve for the constants:

(:latex:) \begin{align*} x &= 0 & -1 &= -2A & A &= \frac{1}{2}
x &= \frac{1}{2} & \frac{1}{4} &= \frac{5}{4}B & B &= \frac{1}{5}
x &= -2 & -1 &= 10C & C &= -\frac{1}{10}. \end{align*} (:latexend:)

So we find

(:latex:) \begin{align*} \int \frac{x^2+2x-1}(x(2x-1)(x+2) \, dx &= \int \left( \frac{1/2}{x} + \frac{1/5}{2x-1} + \frac{-1/10}{x+2}\right) \, dx
&= \frac{1}{2} \ln|x| + \frac{1}{5} \cdot \frac{1}{2}\ln|2x-1| - \frac{1}{10}\ln|x+2| + C
&= \frac{1}{2}\ln|x| + \frac{1}{10}\ln|2x-1|-\frac{1}{10}\ln|x+2|+C. \end{align*} (:latexend:)

Note the extra factor of ($\frac{1}{2}$) for the middle term comes from doing a substitution of ($u = 2x-1$), which implies ($dx = \frac{1}{2}\, du$).

Example

A simple model for the deflection ($x(t)$) of a thin beam under a load proportional to ($\lambda^2$) is

(:latex:) \[ \frac{dx}{dt} = \lambda^2 x - x^3 = x(\lambda-x)(\lambda+x). \] (:latexend:)

Solve this differential equation (but do not solve for ($x(t)$) explicitly). Then find the equilibria of the differential equation and classify them as stable or unstable. (:toggle hide show="Answer" box2c:)

Factoring gives

(:latex:) \[ \frac{dx}{dt} = x(\lambda-x)(\lambda+x). \] (:latexend:)

Separating and integrating gives

(:latex:) \[ \int \frac{dx}{x(\lambda-x)(\lambda+x)} = \int dt. \] (:latexend:)

Now, we use partial fractions on the left side:

(:latex:) \[ \frac{1}{x(\lambda-x)(\lambda+x)} = \frac{A}{x} + \frac{B}{\lambda-x} + \frac{C}{\lambda + x} \] (:latexend:)

Clearing fractions gives

(:latex:) \[ 1 = A(\lambda-x)(\lambda+x) + Bx(\lambda+x) + Cx(\lambda-x). \] (:latexend:)

Picking convenient values of ($x$) gives

(:latex:) \begin{align*} x &= 0 & 1 &= \lambda^2 A & A &= \frac{1}{\lambda^2}
x &= \lambda & 1 &= 2\lambda^2 B & B &= \frac{1}{2\lambda^2}
x &= -\lambda & 1 &= -2\lambda^2 C & C &= -\frac{1}{2\lambda^2}. \end{align*} (:latexend:)

So we have

(:latex:) \begin{align*} \int \frac{dx}{x(\lambda-x)(\lambda+x)} &= \int \left(\frac{1/\lambda^2}{x} +\frac{1/2\lambda^2}{\lambda-x} - \frac{1/2\lambda^2}{\lambda+x} \right) \, dx
&= \frac{1}{\lambda^2} \ln|x| - \frac{1}{2\lambda^2}\ln|\lambda - x| - \frac{1}{2\lambda^2}\ln|\lambda+x|. \end{align*} (:latexend:)

All of this equals ($t + C$) on the right.

The equilibria of the differential equation are ($x = 0$), ($x = \lambda$), and ($x = -\lambda$). The equilibrium at 0 is unstable and the other two are stable, as the graph shows:

Example

The logistic model for population dynamics says that the rate of change of a population ($P$) with respect to time is

(:latex:) \[ \frac{dP}{dt} = rP - bP^2 \] (:latexend:)

where ($r$) and ($b$) are positive constants which can be thought of as the reproduction rate and death rate, respectively. Factoring and letting ($K = \frac{r}{b}$), we have

(:latex:) \[ \frac{dP}{dt} = bP(K-P). \] (:latexend:)

Solve this differential equation. What is the long run population behavior? (:toggle hide show="Answer" box3:)

Separating gives

(:latex:) \begin{equation} \frac{dP}{P(K-P)} = b dt. \end{equation} (:latexend:)

Integrating the left side is done using partial fractions, and the denominator is already factored. So the next step is to find ($A$) and ($B$) such that

(:latex:) \begin{equation*} \frac{1}{P(K-P)} = \frac{A}{P} + \frac{B}{K-P}. \end{equation*} (:latexend:)

Clearing denominators gives ($1 = A(K-P) + BP$). Remember, ($K$) and ($A$) are constants, and this equation must hold for every value of ($P$). Setting ($P=K$) cancels the first term and gives ($1 = BK$), so ($B = \frac{1}{K}$). Setting ($P=0$) cancels the second term and gives ($A=\frac{1}{K}$). Thus,

(:latex:) \begin{align*} \int \frac{dP}{P(K-P)} &= \int \frac{1}{K} \left(\frac{1}{P} + \frac{1}{K-P}\right) \, dP
&= \frac{1}{K} \left(\ln P - \ln(K-P)\right)
&= \frac{1}{K} \ln \frac{P}{K-P}, \end{align*} (:latexend:)

by a property of logarithms. Multiplying through by ($K$) gives

(:latex:) \begin{align*} \ln\left(\frac{P}{K-P}\right)&= \int Kb \, dt
&= \int r \, dt
&= rt+C \end{align*} (:latexend:)

(recall that ($Kb = r$) by the definition of ($K$)). Now, exponentiating gives

(:latex:) \[ \frac{P}{K-P} = \tilde{C}e^{rt}, \] (:latexend:)

for a new constant ($\tilde{C}$). By plugging in ($t=0$), we find that

(:latex:) \[ \tilde{C} = \frac{P_0}{K-P_0}, \] (:latexend:)

where ($P_0$) is the initial population. Multiplying through by ($K-P$) and doing a little algebra gives

(:latex:) \begin{align*} P &= \tilde{C}e^{rt}(K-P)
P + P\tilde{C}e^{rt} &= \tilde{C}e^{rt}K
P(1+\tilde{C}e^{rt}) &= \tilde{C}e^{rt}K
P &= \frac{\tilde{C}e^{rt}K}{1+\tilde{C}e^{rt}}. \end{align*} (:latexend:)

Replacing ($\tilde{C} = \frac{P_0}{K-P_0}$) gives

(:latex:) \begin{align*} P &= \frac{P_0}{K-P_0} e^{rt}K \cdot \frac{1}{1+\frac{P_0}{K-P_0}e^{rt}}
&= \frac{K P_0 e^{rt}}{K-P_0 + P_0e^{rt}}
&= \frac{K P_0}{(K-P_0)e^{-rt} + P_0} \end{align*} (:latexend:)

(From the first to the second line, we distributed ($(K-P_0)$) in the denominator. From the second to third line, we multiplied the top and bottom by ($e^{-rt}$).).

Note that if ($P_0 = 0$) (i.e. there was no population to begin with), then the population will stay at 0. This is consistent with the above equation. On the other hand, if ($P_0 > 0$), then as ($t \rightarrow \infty$), the ($e^{-rt}$) in the denominator goes to 0, and so

(:latex:) \[ \lim_{t \rightarrow \infty} P(t) = \frac{KP_0}{P_0} = K. \] (:latexend:)

We can think of ($K$) as the carrying capacity for the population, a sort of ideal size for the population. Alternatively, by looking at the original differential equation, we see that ($K$) is an equilibrium. It is stable, since populations above ($K$) have a negative derivative (hence are decreasing), and populations below ($K$) have a positive derivative (hence are increasing).

On the other hand 0 is an unstable equilibrium. The model implies that as long as the population is not extinct to begin with, it will grow and eventually equal ($K$).
Other technicalities
Higher degree numerator

For the algebra to work out above, the degree of the numerator, ($P(x)$), must be lower than that of the denominator, ($Q(x)$). However, it is easy to deal with the case when the numerator has equal or higher degree. One can use long division to rewrite the quotient as a divisor plus a remainder, just like writing an improper fraction as a mixed number in middle school.
Repeated factors

If the denominator has one or more repeated factors, i.e.

(:latex:) \begin{equation*} \frac{P(x)}{Q(x)} = \frac{P(x)}{(x-r_1)^{m_1} \ldots (x-r_k)^{m_k}}, \end{equation*} (:latexend:)

where one or more of the ($m_i$) is greater than 1. Then the way to express the function is

(:latex:) \begin{align*} \frac{P(x)}{(x-r_1)^{m_1} \ldots (x-r_n)^{m_n}} &= \frac{A_1}{x-r_1} + \frac{A_2}{(x-r_1)^2} + \dotsb+ \frac{A_{m_1}}{(x-r_1)^{m_1}}
& + \frac{B_1}{x-r_2} + \frac{B_2}{(x-r_2)^2}+ \dotsb + \frac{B_{m_2}}{(x-r_2)^{m_2}}
& + \ldots. \end{align*} (:latexend:)

Now, the algebra proceeds as before to find the constants in the numerators. It is easiest to see this through an example.

Example

Compute

(:latex:) \[ \int \frac{2x^2-4x-2}{(x+1)(x-1)^2}dx. \](:latexend:) (:toggle hide show="Answer" box4:)

The denominator is already factored, so write

(:latex:) \begin{equation*} \frac{2x^2-4x-2}{(x+1)(x-1)^2} = \frac{A}{x+1} + \frac{B}{x-1} + \frac{C}{(x-1)^2}. \end{equation*} (:latexend:)

Clearing the denominators gives

(:latex:) \begin{equation*} 2x^2-4x-2= A(x-1)^2 + B(x+1)(x-1) + C(x+1). \end{equation*} (:latexend:)

Plugging in ($x=1$) cancels the first two terms on the right, leaving ($-4 = 2C$), so ($C=-2$). Plugging in ($x=-1$) cancels the second two terms and leaves ($4 = 4A$), so ($A = 1$).

Now, it seems that there are no more nice values of ($x$) to help solve for ($B$). But remember that the equation must hold for any value of ($x$). Picking ($x=0$) (which is an easy value to use), gives ($-2 = A - B + C$). Knowing ($A = 1$) and ($C=-2$) gives ($B=1$).

Thus,

(:latex:) \begin{align*} \int \frac{2x^2-4x-2}{\left(x+1\right)(x-1)^2} dx &= \int \left(\frac{1}{x+1} + \frac{1}{x-1} + \frac{-2}{(x-1)^2} \right)dx
&= \ln|x+1| + \ln|x-1| + \frac{2}{x-1} + C \end{align*} (:latexend:)
Quadratic factors

Suppose one of the factors of the denominator is a quadratic which cannot be factored (e.g. ($x^2+1$)). Then the numerator of this factor in the expansion should be of the form ($Ax+B$). Then the algebra proceeds as before.

Example

Compute

(:latex:) \[ \int \frac{3x^2-2x+1}{\left(x-1\right)(x^2+1)}dx. \] (:latexend:) (:toggle hide show="Answer" box5:)

Write

(:latex:) \begin{equation*} \frac{3x^2-2x+1}{\left(x-1\right)(x^2+1)} = \frac{A}{x-1} + \frac{Bx+C}{x^2+1}. \end{equation*} (:latexend:)

Clearing fractions gives ($3x^2 - 2x + 1 = A(x^2+1) + (Bx+C)(x-1)$). Picking ($x=1$) gives ($2 = 2A$), so ($A = 1$). Now, picking any other two values for ($x$) will allow finding ($B$) and ($C$). For instance, ($x = 0$) gives ($1 = A -C$), and so ($C = 0$). Finally, picking ($x=-1$) gives ($6 = 2A + (-B)(-2)$), so ($B = 2$).

Thus,

(:latex:) \begin{align*} \int \frac{3x^2-2x+1}{\left(x-1\right)(x^2+1)}dx &= \int \left( \frac{1}{x-1} + \frac{2x}{x^2+1}\right)dx
&= \ln|x-1| + \ln(x^2+1)+C. \end{align*} (:latexend:)
EXERCISES

Compute the following integrals:

    ($ \displaystyle \int \frac{5+x}{x^2+x-6} \, dx $)
    ($ \displaystyle \int \frac{2x + 3}{6x^2 + 5x + 1} \, dx $)
    ($ \displaystyle \int \frac{x}{\left(x+1\right)(x+2)} \, dx $)
    ($ \displaystyle \int \frac{x^2-x+5}{\left(x-2\right)(x-1)(x+3)} \, dx $)
    ($ \displaystyle \int \frac{2x-1}{x^3-x} \, dx $)
    ($ \displaystyle \int \frac{x^2-3}{x^2-4} \, dx $)
    ($ \displaystyle \int \frac{x^3+10x^2+33x+36}{x^2+4x+3} \, dx $)
    ($ \displaystyle \int \frac{x+2}{(x-1)^2} \, dx $)
    ($ \displaystyle \int \frac{dx}{x^4 - 6x^3 + 12x^2} $) 