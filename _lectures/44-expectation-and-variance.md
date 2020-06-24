---
title: Expectation and variance
description: Properties and interpretations of probability distributions
lecture_number: 44
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
When performing an experiment, it is useful to know what the expected outcome will be as well as how much variation one can expect among the outcomes. The notions of expected outcome and variation are made formal in this module by the terms expectation,variance, and standard deviation.

This module will also show some of the connections of these statistical metrics with the applications of the previous modules.
Expectation

Consider a random variable $$X$$ with probability density function (PDF) $$\rho(x)$$ defined on some domain $$D$$. The expectation of $$X$$, denoted by $$\mathbb{E}$$, is defined by

$$
\begin{align*}
\mathbb{E} &= \int_D x\rho(x)\,dx
&= \int_D x \, dP,
\end{align*}
$$

where $$dP$$ is the probability element. The expectation of $$X$$ is sometimes called the mean of $$X$$, the expected value, or the first moment. In some books it is denoted $$\mu_X$$. It is best to think of the expectation as the number one gets by repeating the experiment many times and taking the average of the outputs.

The notion of expectation is more general than the mean because one can also take the expectation of a function of $$X$$. The expectation of $$f(X)$$ is defined by

$$
\begin{equation*} \mathbb{E}[f(X)] = \int_D f(x)\rho(x)\,dx. \end{equation*}
$$

**Example**

Find the expectation of $$X$$, where $$X$$ is uniformly distributed on the interval $$\left[a,b\right]$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Recall that the PDF associated with $$X$$ is given by $$\rho(x) = \frac{1}{b-a}$$ for $$a \leq x \leq b$$. Thus, the mean is given by

$$
\begin{align*}
\mathbb{E} &= \int_a^b x \cdot \frac{1}{b-a}\,dx
&= \frac{1}{b-a} \frac{x^2}{2} \bigg\vert^b_a
&= \frac{1}{b-a} \cdot \frac{1}{2}(b^2-a^2)
&= \frac{1}{b-a} \cdot \frac{1}{2}(b+a)(b-a)
&= \frac{1}{2}(a+b).
\end{align*}
$$

**Example**

Recall that the random variable $$X$$ is said to have the exponential distribution if the PDF associated with $$X$$ is $$\rho(t) = \alpha e^{-\alpha t}$$ for $$t\geq 0$$, where $$\alpha>0$$ is some constant. Find the expectation of the exponential distribution (in terms of $$\alpha$$).

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


From the definition of expectation, one finds

$$
\begin{align*}
\mathbb{E} &= \int_0^\infty t \alpha e^{-\alpha t}\, dt
&= \alpha \int_0^\infty te^{-\alpha t}\, dt.
\end{align*}
$$

Using integration by parts, with

$$
\begin{align*}
u &= t & du &= dt
dv &= e^{-\alpha t} & v &= \frac{1}{-\alpha}e^{-\alpha t},
\end{align*}
$$

we find that

$$
\begin{align*}
\alpha \int_0^\infty te^{-\alpha t}\, dt &= \alpha \left(\frac{t}{-\alpha}e^{-\alpha t} - \int_0^{\infty} \frac{1}{-\alpha} e^{-\alpha t}\,dt \right)
&= \left(-te^{-\alpha t} - \frac{1}{\alpha} e^{-\alpha t}\right) \bigg\vert^\infty_0
&=(0-0)-(0 - \frac{1}{\alpha})
&= \frac{1}{\alpha}.
\end{align*}
$$

Variance

Consider a random variable $$X$$ with PDF $$\rho(x)$$. The variance of $$X$$, denoted $$\mathbb{V}$$, is defined by

$$
\begin{align*}
\mathbb{V} &= \mathbb{E}\left[ \left( X-\mathbb{E}[X] \right)^2 \right]
&=\mathbb{E}[X^2] - \mathbb{E}[X]^2.
\end{align*}
$$

In the notation of the lecture,

$$
\begin{align*}
\mathbb{V} &= \int_D (x-\mathbb{E})^2 \, dP
&= \int_D x^2 \, dP - \mathbb{E}^2.
\end{align*}
$$

Note: it requires some calculation to show the second equality above holds. Either of the above expressions may be taken as the definition of variance, and the second one might be slightly simpler for the sake of computation.

<button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


Expanding out the expression and using the linearity of the integral, we find

$$
\begin{align*}
\int_D (x-\mathbb{E})^2 \, dP &= \int_D (x-\mathbb{E})^2 \rho(x) \, dx
&= \int_D x^2 \, dP - \int_D 2x \mathbb{E} \, dP + \int \mathbb{E}^2 \, dP
&= \int_D x^2 \, dP - 2 \mathbb{E} \int_D x \, dP + \mathbb{E}^2 \int \, dP
&= \int_D x^2 \, dP - 2 \mathbb{E} \cdot \mathbb{E} + \mathbb{E}^2
&= \int_D x^2 \, dP - \mathbb{E}^2.
\end{align*}
$$

because $$\int x \, dP = \mathbb{E}$$ and $$\int \, dP = 1$$, by the definition of expectation and the definition of the probability density function, respectively.

**Example**

Compute the variance of the exponential density function $$\rho(x) = \alpha e^{-\alpha x}$$.

<button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


The variance requires us to compute

$$
\begin{align*}
\mathbb{E}(X^2) &= \int_D x^2 \, dP
&= \int_{x=0}^\infty x^2 \alpha e^{-\alpha x} \, dx.
\end{align*}
$$

Using integration by parts, with

$$
\begin{align*}
u &= x^2 & du &= 2x \, dx
dv &= \alpha e^{-\alpha x} \, dx & v &= -e^{-\alpha x},
\end{align*}
$$

we find

$$
\begin{align*}
\int_{x=0}^\infty x^2 \alpha e^{-\alpha x} \, dx &= -x^2 e^{-\alpha x} \bigg\vert_{x=0}^\infty + \int_{x=0}^\infty 2x e^{-\alpha x} \, dx.
\end{align*}
$$

This second integral can be done with integration by parts again, or we can use the fact that this is almost the integral for the expectation. Namely, we know

$$
\int_{x=0}^\infty x \alpha e^{-\alpha x} \, dx = \frac{1}{\alpha},
$$

and so by dividing through by $$\alpha$$, we have

$$
\int_{x=0}^\infty x e^{-\alpha x} \, dx = \frac{1}{\alpha ^2}.
$$

Putting this together, we have

$$
\begin{align*}
\int_{x=0}^\infty x^2 \alpha e^{-\alpha x} \, dx &= -x^2 e^{-\alpha x} \bigg\vert_{x=0}^\infty + \frac{2}{\alpha^2}
&= (0 - 0) + \frac{2}{\alpha^2}
&= \frac{2}{\alpha^2}.
\end{align*}
$$

Finally, then, the variance is

$$
\begin{align*}
\mathbb{V} &= \int_D x^2 \, dP - \mathbb{E}^2
&= \frac{2}{\alpha^2} - \left(\frac{1}{\alpha}\right)^2
&= \frac{1}{\alpha^2}.
\end{align*}
$$

Standard deviation

Consider a random variable $$X$$ with PDF $$\rho(x)$$. Then the standard deviation of $$X$$, denoted $$\sigma_X$$, is defined by

$$
\begin{align*}
\sigma_X &= \sqrt{V[X]}
&= \sqrt{E[X^2]-E[X]^2}
&= \sqrt{\int_D x^2\rho(x)\,dx - \left(\int_D x\rho(x) \,dx\right)^2}.
\end{align*}
$$

**Example**

Find the standard deviation of $$X$$, where $$X$$ is uniformly distributed over $$\left[a,b\right]$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Again, recall that the PDF for the uniform distribution is $$\rho(x) = \frac{1}{b-a}$$ for $$a \leq x \leq b$$. Thus,

$$
\begin{align*}
E[X^2] &= \int_a^b x^2 \frac{1}{b-a} \,dx
&= \frac{1}{b-a} \frac{x^3}{3} \bigg\vert^b_a
&= \frac{1}{b-a} \cdot \frac{1}{3} (b^3-a^3)
&= \frac{1}{b-a} \cdot \frac{1}{3} (b-a)(b^2 +ba + a^2)
&= \frac{b^2+ab+a^2}{3}
\end{align*}
$$

From the previous example, $$E[X] = \mu_X = \frac{a+b}{2}$$. Thus,

$$
\begin{align*}
\sigma_X &= \sqrt{E[X^2] - E[X]^2}
&= \sqrt{ \frac{b^2+ba+a^2}{3} - \frac{b^2+2ba+a^2}{4}}
&= \sqrt{ \frac{b^2-2ab+a^2}{12}}
&= \frac{b-a}{\sqrt{12}}.
\end{align*}
$$

Interpretations

If one interprets the PDF $$\rho(x)$$ as the density of a rod at location $$x$$, then:

- The mean, $$\mu = \int x\rho(x)\,dx$$, gives the center of mass of the rod.
- The variance, $$V = \int (x-\mu)^2\rho(x)\,dx$$, gives the moment of inertia about the line $$x = \mu$$.
- The standard deviation, $$\sigma = \sqrt{V}$$, gives the radius of gyration about the line $$x = \mu$$. 

The normal distribution

A random variable $$X$$ is said to have the normal distribution, or to be normally distributed, with mean $$\mu$$ and standard deviation $$\sigma$$ if its PDF is of the form

$$
\begin{equation*} \rho(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} \left(\frac{x-\mu}{\sigma}\right)^2}. \end{equation*}
$$

Due to its ubiquity throughout the sciences, the normal distribution is one of the most well-known probability distributions. However, because its PDF does not have an elementary anti-derivative, it is not easy to calculate exact probabilities associated with the normal distribution. Instead, there are is a rule of thumb which can be used.
The 68-95-99.7 rule

Given a random variable $$X$$ which is normally distributed with mean $$\mu$$ and standard deviation $$\sigma$$, the following hold:

- $$P(\mu-\sigma \leq X \leq \mu+\sigma) \approx .68$$.
- $$P(\mu-2\sigma \leq X \leq \mu+2\sigma) \approx .95$$.
- $$P(\mu-3\sigma \leq X \leq \mu+3\sigma) \approx .997$$. 

In other words, 68% of samples will fall within 1 standard deviation of the mean. 95% of samples will fall within 2 standard deviations of the mean. And 99.7% of samples will fall within 3 standard deviations. These rules, along with the symmetry of the normal PDF, can be used to approximate many probabilities relating to the normal distribution:
**Example**

The height of men in a certain population is normally distributed with mean $$\mu = 70$$ inches and standard deviation $$\sigma = 2$$ inches. If a man is chosen at random from the population, what is the probability that he is taller than 72 inches? <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Let $$X$$ be the height of a randomly chosen man. Then $$P(68 \leq X \leq 72) = .68$$ by the above rule. By symmetry $$P(68 \leq X \leq 70) = P(70 \leq X \leq 72) = .34$$. Also, by symmetry, $$P(X \leq 70) = .5$$. Thus,

$$
\begin{align*}
P(X \leq 72) &= P(X \leq 70)+P(70 \leq X \leq 72)
&= .5 + .34
&= .84.
\end{align*}
$$

It follows that

$$
\begin{align*}
P(X > 72) &= 1 - P(X \leq 72)
&= 1 - .84
&= .16.
\end{align*}
$$

This is best visualized by labeling the various regions under the normal curve with their areas:

So the probability that a randomly chosen man from the population is taller than 72 inches is .16.

## Exercises

- Compute the expected value of normally distributed random variable with probability density function $$ \rho(x)= \frac{1}{\sqrt{2\pi}} e^{-\frac{x^2}{2}} $$ on $$ -\infty < x < \infty $$. 