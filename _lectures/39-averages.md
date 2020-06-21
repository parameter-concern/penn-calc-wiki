---
title: Averages
description: The average value of a function over an interval
lecture_number: 39
topic_number: 4
layout: lecture
mathjax: true
---
Consider the problem of finding the average test score in a class of 100 students. The answer is to add up all the scores and divide by 100. But what would happen if there were infinitely many students? This module deals with the problem of finding the average value of a function.
Average value of a function

The definition of the average value of a function ($f(x)$) over the interval ($\left[a,b\right]$), denoted ($\overline{f}$), is

(:latex:) \begin{equation*} \overline{f} = \frac{\int_a^b f(x) \, dx}{b-a}. \end{equation*} (:latexend:)

One way to interpret the average value is to find the rectangle of length ($b-a$) whose area equals the area under the curve ($f$) over the interval ($\left[a,b\right]$). The height of this rectangle is ($\overline{f}$). Put another way, ($\overline{f}$) is the height of the horizontal line such that the area above the line and below ($f(x)$) equals the area which is below the line and above ($f(x)$). These areas are shown in red and blue, respectively, in the following diagram:

A better formulation of the average value, which will be useful in other situations and higher dimensions, is

(:latex:) \[ \overline{f} = \frac{\int_{x=a}^b f \, dx}{\int_{x=a}^b \,dx}. \] (:latexend:)

This emphasizes that the average value over a region is the integral of the function over the region divided by the volume of that region (in this case, the 1-dimensional volume is just the length of the interval). This generalizes nicely to higher dimensions.

If we go down a dimension to the discrete average, if ($f_i$) denotes the ith data point out of n, then the average value of the data is

(:latex:) \[ \overline{f} = \frac{\sum_{i=1}^n f_i}{n} = \frac{\sum_{i=1}^n f_i}{\sum_{i=1}^n 1}. \] (:latexend:)

This shares a common feature with the earlier formula for average value. Namely, it is the sum (integral) of the function values over a range of inputs divided by the sum (integral) of 1 over that range of inputs.

Example

Compute the average value of ($\sin^2x$) over the interval ($\left[0,2\pi\right]$).

(:toggle hide show="Answer" box1:)

From the definition,

(:latex:) \begin{align*} \overline{f} &= \frac{\int_0^{2\pi} \sin^2x dx}{2\pi}
&= \frac{1}{2\pi} \int_0^{2\pi} \frac{1}{2}\left(1-\cos(2x)\right)dx
&= \frac{1}{2\pi} \left(\frac{x}{2} - \frac{1}{4}\sin(2x)\right) \bigg|^{2\pi}_0
&= \frac{1}{2\pi} \cdot \frac{2\pi}{2}
&= \frac{1}{2}. \end{align*} (:latexend:)

Example

Compute the average of ($x^n$) and ($e^x$) over ($0 \leq x \leq T$). Compute the average of ($\ln x$) over ($1 \leq x \leq T$).

(:toggle hide show="Answer" box2:)

For ($f(x) = x^n$), one finds

(:latex:) \begin{align*} \overline{f} &= \frac{1}{T} \int_0^T x^n \, dx
&= \frac{1}{T} \frac{x^{n+1}}{n+1} \bigg|_0^T
&= \frac{T^n}{n+1}. \end{align*} (:latexend:)

For ($f(x) = e^x$), the average value is

(:latex:) \begin{align*} \overline{f} &= \frac{1}{T} \int_0^T e^x \, dx
&= \frac{e^T-1}{T} \end{align*} (:latexend:)

For ($f(x) = \ln x$), recalling the integral using integration by parts, one finds

(:latex:) \begin{align*} \overline{f} &= \frac{1}{T-1} \int_1^T \ln x \, dx
&= \frac{1}{T-1} (x \ln x - x) \bigg|^T_1
&= \frac{1}{T-1} (T \ln T - T + 1). \end{align*} (:latexend:)

Example

Suppose we are given the density function ($\rho(r)$) for the density of the earth at a distance ($r$) from the center. Find a formula for the average density of the earth, but do not try to evaluate the integral.

(:toggle hide show="Answer" box3:)

Note that we cannot simply integrate the density function and divide by the radius of the earth, for the same reason that we could not integrate the density function to find the mass of the earth in the previous module.

One way to logically think about it is to note that the average density times the volume of the earth should give the mass of the earth. That is,

(:latex:) \[ \overline{\rho} \cdot V = M. \] (:latexend:)

Remember that when we found the mass of the earth, we had ($dM = \rho \, dV$), where the volume element ($dV$) is a spherical shell. So we can write

(:latex:) \[ \overline{\rho} = \frac{M}{V} = \frac{\int \rho \, dV}{\int dV}. \] (:latexend:)

Then, remembering that the volume of the spherical shell (i.e. the volume element) is ($4 \pi r^2 \, dr$), we have

(:latex:) \[ \overline{\rho} = \frac{\displaystyle \int_{r=0}^R 4 \pi r^2 \rho(r) \, dr}{\displaystyle \int_{r=0}^R 4 \pi r^2 \, dr}. \] (:latexend:)
Root mean square

There is another type of average of a function called the root mean square. The root mean square of ($f$), denoted ($f_{RMS}$) is defined by

(:latex:) \[ f_{RMS} = \sqrt{ \overline{f^2} }. \] (:latexend:)

So the root mean square is the square root of the average value of the square of the function. This is a useful metric when the average value of ($f$) is uninteresting.

Example

Compute and compare the average value and the root mean square of ($f(x) = \sin x$) on the interval ($\left[0,2\pi \right]$).

(:toggle hide show="Answer" box4:)

The average value of ($\sin x$) is

(:latex:) \begin{align*} \overline{f} &= \frac{\displaystyle \int_{x=0}^{2\pi} \sin x \, dx}{2 \pi}
&= \frac{1}{2\pi} (-\cos x) \bigg|_{x=0}^{2\pi}
&= \frac{1}{2\pi} (-1 - (-1))
&= 0. \end{align*} (:latexend:)

Using the result of an example from above, the root mean square of ($\sin x$) is

(:latex:) \begin{align*} f_{RMS} &= \sqrt{ \frac{\displaystyle \int_{x=0}^{2\pi} \sin^2 x \, dx}{2 \pi} }
&= \sqrt{\frac{1}{2}}
&= \frac{1}{\sqrt{2}}. \end{align*} (:latexend:)
EXERCISES

    Consider the polar function ($f(\theta) = \cos^2(\theta) $). Compute the average value of ($f$) from ($\theta = 0$) to ($\theta = 2\pi$). 