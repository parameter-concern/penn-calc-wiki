---
title: Probability densities
description: Using the density function to compute probabilities
lecture_number: 43
topic_number: 4
layout: lecture
mathjax: true
---
The last module dealt with the uniform distribution, where any one outcome is as likely as another. This module deals with experiments whose outcomes have different probabilities. For example, consider an unfair coin which has a ($\frac{2}{3}$) probability of landing heads and a ($\frac{1}{3}$) probability of landing tails. Another example is time spent on hold with customer service, where it is more likely that the call is answered in the first hour than in the second hour.
Random variable and probability density function (PDF)

A random variable ($X$) is a function whose output should be thought of as the outcome of an experiment. Associated with a random variable is a probability density function (PDF) ($\rho(x)$), which is defined by ($P(a \leq X \leq b) = \int_a^b \rho(x)dx$). That is, the probability that the random variable falls in a certain range of values is given by integrating the PDF over that range of values.

Phrased another way, we can think of probability ($P$) as the quantity we want to compute over a certain range of values, and the probability element is given by

(:latex:) \[ dP = \rho(x) \, dx. \] (:latexend:)

Example

Consider the spinner from the last module. The outcome of a spin is some angle (relative to the positive ($x$)-axis) between 0 and ($2\pi$). If ($X$) is the random variable which gives the output of a spin, then

(:latex:) \begin{equation*} P(a \leq X \leq b) = \frac{b-a}{2\pi}, \end{equation*} (:latexend:)

since the spinner was assumed to be fair. This holds for all ($0\leq a \leq b \leq 2\pi$). Then the associated PDF is

(:latex:) \begin{equation*} \rho(x) = \begin{cases} \frac{1}{2\pi} & \hbox{if $0 \leq x \leq 2\pi$}
0. & \hbox{otherwise} \end{cases} \end{equation*} (:latexend:)
Note

Sometimes a PDF ($\rho(x)$) is only defined on a certain domain ($D$). ($D$) can be thought of as the set of all possible outcomes of the experiment ($X$). In this case, it is assumed that ($\rho(x)=0$) for ($x$) not in that domain. So another way of defining the PDF for the spinner is ($\rho(x) = \frac{1}{2\pi}$) for ($0 \leq x \leq 2\pi$).
Properties of a probability density function

The following are defining properties of a PDF. In other words, a function ($\rho(x)$) is a PDF on the domain ($D$) if and only if it satisfies these properties.

    ($\rho(x)\geq 0$) for all ($x \in D$).
    ($\int_D \rho(x)\,dx = 1$). 

The first property is necessary since probabilities must be non-negative. The second property reflects the fact that the random variable ($X$) associated with ($\rho(x)$) must have some outcome in the domain ($D$) (since ($D$) is the set of all possible outcomes), and so integrating over all of these outcomes should give 1.
Note

If ($\rho(x)$) is defined on some specific domain ($D$), then the integral over that specific domain should equal 1. This is because ($\rho(x)=0$) outside of that domain, as mentioned in the above note.

Example

Find the value of the constant ($c$) so that ($\rho(x) = \frac{c}{1+x^2}$) for all ($x$) is a PDF.

(:toggle hide show="Answer" box1:)

As long as ($c \geq 0$), the first property for a PDF will be met, since ($1+x^2>0$) for all ($x$). To satisfy the second property, compute

(:latex:) \begin{align*} \int_{-\infty}^\infty \frac{c}{1+x^2}\,dx &= c \left(\arctan(x)\bigg|^\infty_{-\infty}\right)
&= c \left( \frac{\pi}{2} - (-\frac{\pi}{2})\right)
&= c \pi. \end{align*} (:latexend:)

Since this integral is supposed to be 1, we find that ($c = \frac{1}{\pi}$).
Several specific density functions
Uniform density

Hinted at above and in the previous module, the uniform density function (or uniform distribution) on ($\left[a,b\right]$) is given by ($\rho(x) = \frac{1}{b-a}$) (and ($\rho(x) = 0$) if ($x$) is not in ($\left[a,b\right]$)):

More generally, the uniform distribution on the domain ($D$) (whatever the dimension) is given by

(:latex:) \[ \rho(x) = \frac{1}{\hbox{Volume of $D$}}. \] (:latexend:)

In dimension 0, where outcomes are discrete (as in the rolling of a die or the flipping of a coin), remember that volume is just counting. So in this case the probability of a particular outcome is

(:latex:) \[ \rho(x) = \frac{1}{n}, \] (:latexend:)

where ($n$) is the number of outcomes in the domain ($D$) (e.g. ($n=6$) for the roll of a die; ($n=2$) for a coin flip).
Exponential density

Another density function used to model many common experiments is the exponential density function. This is actually a whole family of density functions given by ($\rho(t) = \alpha e^{-\alpha t}$) for ($t \geq 0$) and ($\alpha>0$) some constant. The reason a parameter ($t$) is used is that the exponential density is often used to model experiments with a time outcome.

Example

Show that the exponential density ($\rho(t) = \alpha e^{-\alpha t}$) (for ($t \geq 0$)) satisfies the properties of a density function.

(:toggle hide show="Answer" box1b:)

The exponential function is never negative, so one need only check the integral. One finds

(:latex:) \begin{align*} \int_{t=0}^\infty \alpha e^{-\alpha t} \, dt &= \alpha \frac{1}{-\alpha} e^{-\alpha t} \bigg|_{t=0}^\infty
&= -(0-1)
&= 1, \end{align*} (:latexend:)

as desired. So the exponential density is in fact a density.

Example

Consider a call made to customer service at Acme company. The number of minutes spent on hold before the call is answered is often modeled with an exponential density function

(:latex:) \[ \rho(t) = \alpha e^{-\alpha t}. \] (:latexend:)

Find, in terms of ($\alpha$), the probability that the waiting time for a call is less than 30 minutes. (:toggle hide show="Answer" box2:)

To find the probability that ($0\leq X \leq 30$), use the relationship between probability and the PDF, which is

(:latex:) \begin{align*} P(0\leq X \leq 30) &= \int_0^{30} \rho(x)\,dx
&= \int_0^{30} \lambda e^{-\lambda x}\, dx
&= -e^{-\lambda x} \bigg|^{30}_0
&= -e^{-30 \lambda} - (-1)
&= 1 - e^{-30 \lambda}. \end{align*} (:latexend:)

Example

Again consider customer service call waiting time at Acme company, and again assume an exponential density function

(:latex:) \[ \rho(t) = \alpha e^{-\alpha t}. \] (:latexend:)

Suppose half of all customers are answered within 5 minutes. Find ($\alpha$) and then find the probability that a call takes more than 10 minutes to be answered.

(:toggle hide show="Answer" box2b:)

Since half of all customers are answered within 5 minutes, we have that

(:latex:) \[ P(0 \leq X \leq 5) = \frac{1}{2}. \] (:latexend:)

On the other hand, we know that this can be expressed as the integral of the density function, so we have

(:latex:) \begin{align*} \frac{1}{2} &= \int_{t=0}^5 \rho(t) \, dt
&= \int_{t=0}^5 \alpha e^{-\alpha t} \, dt
&= - e^{-\alpha t} \bigg|_{t=0}^5
&= -e^{-5 \alpha} - (-1)
&= 1 - e^{-5 \alpha}. \end{align*} (:latexend:)

So we have that

(:latex:) \[ e^{-5 \alpha} = \frac{1}{2}. \] (:latexend:)

Taking the log of both sides, dividing by ($-5$) and simplifying, we have

(:latex:) \begin{align*} \alpha &= \frac{1}{-5} \ln\left(\frac{1}{2}\right)
&= \frac{1}{-5} (-\ln 2)
&= \frac{1}{5} \ln 2. \end{align*} (:latexend:)

For the second part, we want to know the probability of waiting more than 10 minutes. This is (leaving ($\alpha$) as a constant for now)

(:latex:) \begin{align*} P(X \geq 10) &= \int_{t=10}^\infty \rho(t)\, dt
&= \int_{t=10}^\infty \alpha e^{-\alpha t} \, dt
&= -e^{-\alpha t} \bigg|_{t=10}^\infty
&= 0 - \left(-e^{-\alpha \cdot 10} \right). \end{align*} (:latexend:)

Now plugging in the value of ($\alpha$), we have

(:latex:) \begin{align*} P(X \geq 10) &= e^{- (\ln 2/5) \cdot 10}
&= e^{-2 \ln 2}
&= 2^{-2}
&= \frac{1}{4}. \end{align*} (:latexend:)
Gaussian density

The last probability density function is the 'Gaussian, or normal, density function. This is an important density function and is expanded on in the next module. Like the exponential, the Gaussian density function usually has parameters (see the next module), but in its simplest form, the Gaussian is given by

(:latex:) \[ \rho(x) = \frac{1}{\sqrt{2\pi}}e^{-x^2/2}. \] (:latexend:)

The Gaussian has all real ($x$) as its domain, but because it tails off so quickly in both directions, the probability of getting values far from the center (in this case ($x=0$)) is very small.
EXERCISES

    Which of the following are probability density functions? 

(:latex:) \begin{align*} a. f(x) =&1/2 \textrm{ on } D=[0,2]
b. f(x) =& \frac{\sin(x)}{2} \textrm{ on } D=[0, 3\pi]
c. f(x) =& 5 e^{-2x} \textrm{ on } D=[0, \infty)
d. f(x) =& \frac{1}{\pi (1+x^2)} \textrm{ on } D=(-\infty, \infty)
e. f(x) =& \frac{x}{2} \textrm{ for } 0 \leq x \leq1
& \frac{1}{2} \textrm{ for } 1 \leq x \leq 2
& \frac{3}{2}-\frac{x}{2} \textrm{ for } 2 \leq x \leq 3 \end{align*} (:latexend:) 