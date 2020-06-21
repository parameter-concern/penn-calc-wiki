---
title: Discrete calculus
description: How to integrate discrete functions
lecture_number: 47
topic_number: 5
layout: lecture
mathjax: true
---
The previous two modules have laid the groundwork for the discretization, or digitization, of calculus:

    The discrete version of a function is a sequence.
    The discrete version of the derivative is the difference operator.
    The discrete version of the integral is the sum.
    The discrete version of a differential equation is a recurrence relation. 

This module mostly deals with #3, the integral of a discrete function. For continuous functions, there was the Fundamental Theorem of Integral Calculus which made computing integrals easy under certain conditions. Essentially, it said that the integral of the derivative is the function itself, evaluated at the endpoints. The discrete version says the same thing:

The Discrete Fundamental Theorem of Integral Calculus (FTIC)

Given a sequence ($u$),

(:latex:) \[ \sum_{n=A}^B \Delta u = u \bigg|_{n=A}^{B+1}, \] (:latexend:)

and

(:latex:) \[ \sum_{n=A}^B \nabla u = u \bigg|_{n=A-1}^B \] (:latexend:)

(:toggle hide show="Proof sketch" box1:)

To see why this holds, evaluate the sum and carefully note the cancellation. This type of sum is called a telescoping sum. First, for the forward difference operator, one finds

(:latex:) \begin{align*} \sum_{n=A}^B \Delta u &= \sum_{n=A}^B u_{n+1}-u_n
&= (u_{A+1} - u_A) + (u_{A+2}-u_{A+1}) + (u_{A+3}-u_{A+2}) + \dotsb + u_{B+1}-u_B
&= -u_A + u_{A+1} -u_{A+1} + u_{A+2} - u_{A+2} + u_{A+3} + \dotsb -u_B + u_{B+1}
&= -u_A + u_{B+1}, \end{align*} (:latexend:)

as desired. Similarly, with the backwards difference operator, one finds

(:latex:) \begin{align*} \sum_{n=A}^B \nabla u &= \sum_{n=A}^B u_n-u_{n-1}
&= u_A-u_{A-1} + u_{A+1} - u_A + u_{A+2} - u_{A+1} + \dotsb + u_B - u_{B-1}
&= -u_{A-1} + u_B, \end{align*} (:latexend:)

as claimed.

Example

Note that

(:latex:) \[ \Delta \frac{1}{n} = \frac{1}{n+1} - \frac{1}{n} = \frac{-1}{n^2+n}. \] (:latexend:)

Use this, along with FTIC, to find ($\displaystyle \sum_{n=A}^B \frac{1}{n^2+n}$).

(:toggle hide show="Answer" box2:)

By FTIC,

(:latex:) \begin{align*} \sum_{n=A}^B \frac{1}{n^2+n} &= - \sum_{n=A}^B \Delta \frac{1}{n}
&= -\left(\frac{1}{n} \bigg|_{n=A}^{B+1} \right)
&= \frac{1}{A} - \frac{1}{B+1}
&= \frac{B-A+1}{A(B+1)} \end{align*} (:latexend:)

Example

Use the fact that

(:latex:) \[ \Delta n! = (n+1)! - n! = (n+1)n! - n! = (n+1-1)n! = n \cdot n!, \] (:latexend:)

along with the FTIC to find

(:latex:) \[ \sum_{n=A}^B n!n \] (:latexend:)

(:toggle hide show="Answer" box2b:)

By the fact above, we have

(:latex:) \begin{align*} \sum_{n=A}^B n!n &= \sum_{n=A}^B \Delta n!
&= n! \bigg|_{n=A}^{B+1}
&= (B+1)! - A!. \end{align*} (:latexend:)

Example

Let ($F$) denote the Fibonacci sequence defined by

(:latex:) \[ F_{n+2} = F_{n+1} + F_n; \quad F_0 = 0, F_1 = 1. \] (:latexend:)

Note that

(:latex:) \[ \Delta (F_{n+1}) = F_{n+2} - F_{n+1} = F_n, \] (:latexend:)

by rearranging the above recursion relation. Use this, along with the FTIC, to find

(:latex:) \[ \sum_{n=1}^k F_n. \] (:latexend:)

(:toggle hide show="Answer" box2e:)

By the above fact, we have

(:latex:) \begin{align*} \sum_{n=1}^k F_n &= \sum_{n=1}^k \Delta(F_{n+1})
&= F_{n+1} \bigg|_{n=1}^{k+1}
&= F_{k+2} - F_2
&= F_{k+2} - 1. \end{align*} (:latexend:)
Power rule for falling powers

Recall from the previous module that the falling power

(:latex:) \[ n^{\underline{k}} = n(n-1)(n-2)\dotsb (n-k+1) \] (:latexend:)

has a nice power rule for the difference:

(:latex:) \[ \Delta (n^{\underline{k}}) = k n^{\underline{k-1}}. \] (:latexend:)

By running this in reverse, we can find the anti-difference (or antiderivative) of the falling power, which is very similar to the power rule for integration:

(:latex:) \[ \Delta^{-1} (n^{\underline{k}}) = \frac{1}{k+1} n^{\underline{k+1}}+C, \] (:latexend:)

where ($C$) is a constant. Using this, along with the FTIC, allows one to find closed formulas for the sum of polynomials.

Example

Using the power rule and the FTIC, find

(:latex:) \[ \sum_{n=1}^k n. \] (:latexend:)

(:toggle hide show="Answer" box2c:)

Note that ($n = n^{\underline{1}}$), and so

(:latex:) \begin{align*} \sum_{n=1}^k n &= \sum_{n=1}^k n^{\underline{1}}
&= \frac{1}{2}n^{\underline{2}} \bigg|_{n=1}^{k+1}
&= \frac{1}{2}n(n-1) \bigg|_{n=1}^{k+1}
&= \frac{k(k+1)}{2}. \end{align*} (:latexend:)

Example

Find

(:latex:) \[ \sum_{n=1}^k n^2. \] (:latexend:)

(:toggle hide show="Answer" box2d:)

Note that

(:latex:) \[ n^2 = n^{\underline{2}} + n^{\underline{1}}. \] (:latexend:)

Therefore,

(:latex:) \begin{align*} \sum_{n=1}^k n^2 &= \sum_{n=1}^k n^{\underline{2}} + n^{\underline{1}}
&= \frac{1}{3}n^{\underline{3}} + \frac{1}{2}n^{\underline{2}} \bigg|_{n=1}^{k+1}
&= \frac{\left( k+1 \right)k(k-1)}{3} + \frac(k+1)k}{2}
&= (k+1)k \left(\frac{k-1}{3} + \frac{1}{2}\right)
&= (k+1)k \left(\frac{2k-2 + 3}{6}\right)
&= \frac{k(k+1)(2k+1){6}. \end{align*} (:latexend:)

Example

With a little algebra (shown in the previous module), one finds that

(:latex:) \[ n^3 = n^{\underline{3}} + 3n^{\underline{2}} + n^{\underline{1}}. \] (:latexend:)

Use this fact, along with FTIC, to find

(:latex:) \[ \sum_{n=1}^k n^3 \] (:latexend:)

(:toggle hide show="Answer" box3:)

Using the above fact and FTIC, one finds

(:latex:) \begin{align*} \sum_{n=1}^k n^3 &= \sum_{n=1}^k \left(n^{\underline{3}} + 3n^{\underline{2}} + n^{\underline{1}} \right)
&= \frac{1}{4}n^{\underline{4}} + n^{\underline{3}} + \frac{1}{2}n^{\underline{2}} \bigg|_{n=1}^{k+1}. \end{align*} (:latexend:)

Now, note that ($n^{\underline{m}} = 0$) when ($n=1$) for all ($m>1$), because of the factor of ($n-1$). Therefore, the evaluation at the bottom limit is 0. Continuing with the algebra, we find

(:latex:) \begin{align*} \sum_{n=1}^k n^3 &= \frac{1}{4}(k+1)k(k-1)(k-2) + (k+1)k (k-1) + \frac{1}{2}(k+1)k
&= k(k+1) \left(\frac{1}{4}(k-1)(k-2) + k-1 + \frac{1}{2}\right)
&= k(k+1)\left(\frac(k-1)(k-2) + 4(k-1)+2}{4}\right)
&= \frac{k(k+1){4}\left(k^2-3k+2+4k-4+2 \right)
&= \frac{k(k+1)}{4} k(k+1)
&= \left(\frac{k(k+1)}{2}\right)^2. \end{align*} (:latexend:)

Recalling that ($1+2+3+\dotsb+k = \frac{k(k+1)}{2}$), this shows the remarkable fact that

(:latex:) \[ 1^3+2^3+3^3+\dotsb+k^3 = \left(1+2+3+\dotsb+k\right)^2. \] (:latexend:)
Integration by parts

There is also a discrete version of integration by parts. First, the following product rule can be established for the forward difference:

(:latex:) \[ \Delta(uv) = u\Delta v + Ev \Delta u. \] (:latexend:)

(:toggle hide show="Details" box4:)

By subtracting and adding a common term and rearranging, one finds

(:latex:) \begin{align*} (\Delta(uv))_n &= u_{n+1}v_{n+1} - u_nv_n
&= u_{n+1}v_{n+1} - u_nv_{n+1} + u_nv_{n+1} - u_nv_n
&= (u_{n+1}-u_n)v_{n+1} + u_n(v_{n+1}-v_n)
&= \left[\Delta u Ev + u \Delta v\right]_n. \end{align*} (:latexend:)

Then, just like for continuous functions, one can integrate both sides (i.e. sum both sides), rearrange, and apply FTIC to find

(:latex:) \[ \sum_{n=A}^B u \Delta v = uv \bigg|_{n=A}^{B+1} - \sum_{n=A}^B Ev \Delta u. \] (:latexend:)

Example

Find ($\displaystyle \sum_{n=0}^k n2^n$).

(:toggle hide show="Answer" box5:)

Let ($u = n$) and ($\Delta v = 2^n$). It follows that ($\Delta u = 1$), ($v = 2^n$), and ($Ev = 2^{n+1}$). Thus, by the integration by parts formula,

(:latex:) \begin{align*} \sum_{n=0}^k n2^n &= n2^n \bigg|_{n=0}^{k+1} - \sum_{n=0}^k 2^{n+1}
&=(k+1)2^{k+1} - (2^{k+2}-2)
&=(k+1)2^{k+1} - 2 \cdot 2^{k+1} + 2
&=(k-1)2^{k+1} + 2. \end{align*} (:latexend:)
Differential equations

The discrete version of a differential equation is a recurrence relation. This is an equation relating one term of a sequence ($u$) with one or more previous terms in the sequence. In this context, the shift operator acts like the derivative.

Example

Consider the linear first-order recurrence relation

(:latex:) \[ u_{n+1} = \lambda u_n, \] (:latexend:)

which can be written as

(:latex:) \[ Eu = \lambda u \] (:latexend:)

or, with some rearrangement,

(:latex:) \[ (E-\lambda I)u = 0. \] (:latexend:)

By inspection, one can see the solution ($u_n = C\lambda^n$), where ($C = u_0$) is some constant (it can be thought of as an initial condition).

Example

Now, consider using the following linear first-order difference equation

(:latex:) \[ \Delta u = \lambda u. \] (:latexend:)

This is reminiscent of the differential equation ($\frac{dx}{dt} = a x$), considered earlier in the course. Recall that ($\Delta = E-I$), and so this difference relation can be written (:latex:) \[ (E-I)u = \lambda u. \] (:latexend:)

With a little more rearranging one finds

(:latex:) \[ (E-(\lambda+1)I)u = 0, \] (:latexend:)

which is almost identical to the equation from the previous example, but with ($\lambda$) replaced by ($\lambda+1$). Therefore, the solution is ($ u_n = C(\lambda+1)^n$).

Compare this to the solution in the continuous case, which was

(:latex:) \[ \frac{dx}{dt} = \lambda x \quad \Longrightarrow \quad x = Ce^{\lambda t}. \] (:latexend:)

When ($\lambda = 1$), we have the solution

(:latex:) \[ x = Ce^t. \] (:latexend:)

If we let ($\lambda = 1$) in the discrete difference equation, we have

(:latex:) \[ u = C(\lambda +1)^n = C \cdot 2^n, \] (:latexend:)

which again shows that ($2^n$) is the discrete version of the exponential function ($e^t$).
Fibonacci numbers revisited

We can take the recurrence relation for the Fibonacci numbers:

(:latex:) \[ F_{n+2} = F_{n+1} + F_n \] (:latexend:)

and rearrange it to be rewritten in terms of the shift operator:

(:latex:) \begin{align*} F_{n+2} - F_{n+1} - F_n &= 0
(E^2 - E - I)F &= 0. \end{align*} (:latexend:)

Note that the solutions to the equation

(:latex:) \[ x^2 - x - 1 = 0 \] (:latexend:)

are

(:latex:) \[ \varphi = \frac{1}{2} (1+\sqrt{5}) \quad \hbox{and} \quad \psi = \frac{1}{2}(1-\sqrt{5}). \] (:latexend:)

So we can factor the operator ($E^2 - E - I$) to see that

(:latex:) \begin{align*} (E^2 - E - I)F &= 0
(E-\varphi I)(E - \psi I) F &= 0. \end{align*} (:latexend:)

It is a fact that solutions to this equation are combinations (that is, a sum) of solutions to

(:latex:) \begin{align*} (E-\varphi I)F1 &= 0
(E - \psi I) F2 &= 0. \end{align*} (:latexend:)

The solutions to these equations are

(:latex:) \begin{align*} F1_n &= c_1 \varphi^n
F2_n &= c_2 \psi^n. \end{align*} (:latexend:)

So we have that

(:latex:) \[ F_n = c_1 \varphi^n + c_2 \psi^n, \] (:latexend:)

for some constants ($c_1$) and ($c_2$), which depend on the initial conditions of the sequence. To find those constants, we can plug in convenient values of ($n$) and solve.

Letting ($n=0$), we have

(:latex:) \[ F_0 = 0 = c_1 + c_2 \quad \Longrightarrow \quad c_2 = -c_1. \] (:latexend:)

Letting ($n=1$), we have

(:latex:) \begin{align*} F_1 = 1 &= c_1 \varphi + c_2 \psi
&= c_1 \varphi - c_1 \psi
&= c_1 (\varphi - \psi)
&= c_1\cdot \sqrt{5}. \end{align*} (:latexend:)

So we find

(:latex:) \begin{align*} c_1 &= \frac{1}{\sqrt{5}}
c_2 &= -\frac{1}{\sqrt{5}}. \end{align*} (:latexend:)

This gives an explicit, closed form equation for the Fibonacci numbers:

(:latex:) \[ F_n = \frac{1}{\sqrt{5}} \left(\frac{1+\sqrt{5}}{2}\right)^n - \frac{1}{\sqrt{5}} \left(\frac{1-\sqrt{5}}{2}\right)^n. \] (:latexend:)
EXERCISES

    (a) What is ($ \Delta (\frac{1}{n^2}) $)? (b) Using part (a), find ($ \sum_{n=A}^B \frac{-2n-1}{n^2(n+1)^2} $). 