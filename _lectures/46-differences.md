---
title: Differences
description: Derivatives of sequences
lecture_number: 46
topic_number: 5
layout: lecture
mathjax: true
---
What is the derivative of a sequence? The original definition will not work because change in input is discrete and so one cannot take the limit as the change in input goes to 0. Instead, using the interpretation of the derivative as a rate of change leads to two different discrete derivatives. They are called difference operators, and are defined below.
Difference operators

The discrete analog of the derivative is the difference operator, defined as follows.

Difference operators

Given a sequence ($a_n$), the forward difference of ($a$), denoted ($(\Delta a)_n$), is defined by

(:latex:) \begin{equation*} (\Delta a)_n = a_{n+1} - a_{n}. \end{equation*} (:latexend:)

The backward difference of ($a$), denoted by ($(\nabla a)_n$), is defined by

(:latex:) \begin{equation*} (\nabla a)_n = a_n - a_{n-1}. \end{equation*} (:latexend:)

This can be interpreted as the change in output over the change in input:

(:latex:) \[ (\Delta a)_n = \frac{a(n+1) - a(n)}{(n+1)-n} = \frac{a_{n+1} - a_n}{1} = a_{n+1} - a_n, \] (:latexend:)

which resembles the definition for the derivative of a continuous function, but without the limit. If we plot the points of the sequence as if we were graphing the function, and then connect the dots with linear segments, then the forward difference can also be interpreted as the slope between adjacent points:

Example

The sequence ($(4n) = 0,4,8,12,16,\ldots$) has forward difference sequence

(:latex:) \[ \Delta (4n) = 4,4,4,4,\ldots \] (:latexend:)

Example

Find the forward difference sequence of the Fibonacci sequence ($F = 0, 1, 1, 2, 3, 5, 8, 13, 21\ldots$).

(:toggle hide show="Answer" box1:)

The difference sequence is

(:latex:) \[ \Delta F = 1,0,1,1,2,3,5,8,\ldots \] (:latexend:)

Note that this is just the Fibonacci sequence again, but slightly shifted. This makes sense since the difference

(:latex:) \[ (\Delta F)_n = F_{n+1}-F_n = F_{n-1}, \] (:latexend:)

by rearranging the Fibonacci recursion relation.

Example

Find the forward difference of the powers of two: ($\left( 2^n \right) = 1, 2, 4, 8, 16, 32, \ldots $).

(:toggle hide show="Answer" box2:)

The difference sequence is

(:latex:) \[ \Delta (2^n) = 1,2,4,8,16,32,\ldots \] (:latexend:)

This shows that ($2^n$) can be thought of as the discrete analog of the exponential ($e^x$), in the sense that it is its own (discrete) derivative.
Product rules

These difference operators have their own versions of the differentiation rules for continuous functions. For example, there is a product rule. For sequences ($a = (a_n)$) and ($b = (b_n)$), define the new sequence ($(ab)$) by ($(ab)_n = (a_nb_n)$). Then

(:latex:) \begin{align*} \Delta (ab)_n &= a_n \Delta b_n + b_n \Delta a_n + \Delta a_n \Delta b_n
\nabla (ab)_n &= a_n \nabla b_n + b_n \nabla a_n - \nabla a_n \nabla b_n. \end{align*} (:latexend:)

This should be reminiscent of the product rule ($(fg)' = fg' + f'g$).
Higher order difference operators

Just as the derivative of a function gives another function, the difference operator of a sequence ($a$) gives another sequence ($\Delta a$). Then one can take the difference operator of ($\Delta a$) which gives yet another sequence ($\Delta^2 a$). And so on. Consider, for instance, the sequence ($a_n = n^3$) for ($n \geq 0$). Then

(:latex:) \begin{equation*} \begin{array}{ccccccccccc} a &=& 0 & 1 & 8 & 27 & 64 & 125 & 216 & 343 & \ldots
\Delta a &=& 1 & 7 & 19 & 37 & 61 & 91 & 127 & \ldots &
\Delta^2 a &=& 6 & 12 & 18 & 24 & 30 & 36 & \ldots & &
\Delta^3 a &=& 6 & 6 & 6 & 6 & 6 & \ldots & & &
\Delta^4 a &=& 0 & 0 & 0 & 0 & \ldots & &&& \end{array} \end{equation*} (:latexend:)

A little bit of pattern matching shows the following:

(:latex:) \begin{align*} a_n &= n^3
(\Delta a)_n &= 3n^2+3n+1
(\Delta^2 a)_n &= 6n + 6
(\Delta^3 a)_n &= 6
(\Delta^4 a)_n &= 0 \end{align*} (:latexend:)

Just as taking higher derivatives of a polynomial eventually gives 0, taking higher order difference operators of a polynomial eventually gives 0. Moreover, if ($a$) is a polynomial of degree ($p$), then ($\Delta^{p+1}a = (0)$).

Note that the power rule is not quite the same as for regular derivatives (e.g. ($n^3 \mapsto 3n^2+3n+1$)). This is an artifact of the binomial expansion. The next section shows a convenient way to avoid these problems.
Falling powers

The falling power ($n^{\underline{k}}$) is defined to be

(:latex:) \[ n^{\underline{k}} = n(n-1)(n-2) \dotsb (n-k+1), \qquad n^{\underline 0} = 1. \] (:latexend:)

The falling power can be thought of as a discrete version of the monomial ($x^k$). One nice feature of the falling power is that

(:latex:) \begin{align*} \Delta n^{\underline k} &= (n+1)^{\underline k} - n^{\underline k}
&= (n+1)n(n-1) \dotsb (n-k+2) - n(n-1) \dotsb (n-k+1)
&= n(n-1) \dotsb (n-k+2) \left(n+1 - (n-k+1)\right)
&= k n^{\underline{k-1}}, \end{align*} (:latexend:)

which is the familiar power rule.

Example

Express ($n^3$) in terms of falling factorials and use the power rule above to find ($\Delta n^3$).

(:toggle hide show="Answer" box3:)

This requires a little bit of algebra. We know that we need a ($n^{\underline{3}}$) to get a ($n^3$). Note that

(:latex:) \[ n^{\underline{3}} = n(n-1)(n-2) = n^3 - 3n^2 + 2n. \] (:latexend:)

So we have our ($n^3$), but we also have some unwanted lower order terms. We must add ($3n^{\underline{2}}$) to both sides to cancel the ($-3n^2$). Note that

(:latex:) \[ n^{\underline{2}} = n(n-1) = n^2 - n, \] (:latexend:)

and so

(:latex:) \begin{align*} n^{\underline{3}} + 3 n^{\underline{2}} &= (n^3 - 3n^2 + 2n) + 3(n^2-n)
&= n^3 - n. \end{align*} (:latexend:)

So to get rid of the final term of ($-n$), we note that ($n^{\underline{1}} = n$), and so we can add this to both sides to find

(:latex:) \[ n^{\underline{3}} + 3n^{\underline{2}} + n^{\underline{1}} = n^3. \] (:latexend:)

This tells us that

(:latex:) \begin{align*} \Delta n^3 &= \Delta \left(n^{\underline{3}} + 3n^{\underline{2}} + n^{\underline{1}} \right)
&= 3 n^{\underline{2}} + 6 n^{\underline{1}} + 1
&= 3 (n^2 - n) + 6n + 1
&= 3n^2 + 3n + 1, \end{align*} (:latexend:)

which matches the observation about ($\Delta (n^3)$) in the above section.
Discrete ($e$)

With the falling power in hand, consider the discretized version of the exponential function, found by replacing the usual monomials ($x^k$) with ($n^{\underline k}$) in the Taylor series for the exponential:

(:latex:) \[ \sum_{k=0}^\infty \frac{n^{\underline k}}{k!} = 1 + n + \frac{n(n-1)}{2!} + \frac{n(n-1)(n-2)}{3!} + \dotsb \] (:latexend:)

If one evaluates this at ($n=1$) to find the "discrete ($e$)", note that all the terms after the first two disappear because of the ($n-1$) factor in all the higher terms. Thus, the discrete version of ($e$) is 2. This is consistent with the earlier note that ($2^n$) acted like the exponential function (it is its own discrete derivative). Indeed, the above series is ($2^n$), which can be seen by noting it is simply the binomial series ($(1+x)^n$) evaluated at ($x=1$).
Sequence operators

Just as there were operators on functions (e.g. integration, differentiation, logarithm, exponentiation), there are operators on sequences:
Operator	Notation	What it does	Notes
Identity	($I$)	($(Ia)_n = a_n$)	($I^2=I$)
Left shift	($E$)	($(Ea)_n = a_{n+1}$)	($E^2$) shifts twice, etc.
Right shift	($E^{-1}$)	($(E^{-1}a)_n = a_{n-1}$)	($E^{-1}E = I$)
Forward difference	($\Delta$)	($(\Delta a)_n = a_{n+1} - a_n$)	($\Delta = E-I$)
Backward difference	($\nabla$)	($(\nabla a)_n = a_n - a_{n-1}$)	($\nabla = I-E^{-1}$)
Higher derivatives

The expressions for the forward and backward differences in terms of ($I$) and ($E$) can be used to compute the higher derivatives of sequences more easily than it would be to compute them by hand. For example, the third derivative can be found by expanding the expression as a binomial:

(:latex:) \begin{align*} \Delta^3 a &= (E-I)^3 a
&= (E^3 - 3E^2I + 3EI^2-I^3) a
&= (a_{n+3} - 3a_{n+2} + 3a_{n+1} - a_n). \end{align*} (:latexend:)

More generally, the ($k$)th derivative can be written similarly:

(:latex:) \begin{align*} \Delta^k &= (E-I)^k
&= \sum_{i=0}^k (-1)^{k-i} {k \choose i} E^i \end{align*} (:latexend:)
Indefinite integral

As shown above, the forward difference can be expressed in terms of the operators ($E$) and ($I$):

(:latex:) \[ \Delta = E - I. \] (:latexend:)

A logical question is to ask whether it is possible to take the anti-difference, just as there is the antiderivative for functions. The claim is that

(:latex:) \[ \Delta^{-1} = -(I + E + E^2 + E^3 + E^4 + \dotsb ) \] (:latexend:)

This looks reminiscent of the geometric series. By taking the inverse of ($\Delta$) (and a few liberties with the algebra), we have

(:latex:) \begin{align*} \Delta^{-1} &= (E-I)^{-1}
&= -(I-E)^{-1}
&= - (I + E + E^2 + E^3 + \dotsb), \end{align*} (:latexend:)

by thinking of ($(I-E)^{-1}$) as the reciprocal of ($1-E$) in a sense (because ($I$) acts like 1), and applying the geometric series. This derivation is not rigorous, but the above formula does give the anti-difference (up to an additive constant), so long as the sequence ($a_n$) is eventually 0.

This is just a hint of the calculus of sequences, which we explore a little bit more in the modules to come. 