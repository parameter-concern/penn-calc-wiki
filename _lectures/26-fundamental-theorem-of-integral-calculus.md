---
title: Fundamental Theorem of Integral Calculus
description: Connecting definite and indefinite integrals
lecture_number: 26
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
Computing definite integrals from the definition is difficult, even for fairly simple functions. Fortunately, there is a powerful tool—the Fundamental Theorem of Integral Calculus—which connects the definite integral with the indefinite integral and makes most definite integrals easy to compute.

The Fundamental Theorem of Integral Calculus (FTIC)

Given a continuous function $$f$$, it follows that

- $$\frac{d}{dx}\left(\int_a^x f(t)dt\right) = f(x)$$ and
- $$\int_a^b f(x)dx = \left( \int f(x)dx \right) \bigg\vert^b_a$$ 

(where $$F(x) \bigg\vert^b_a = F(b)-F(a)$$).

In other words, Part 1 says that the function

$$
F(x) = \int_{t=a}^x f(t) dt
$$

is an anti-derivative of $$f$$.

Part 2 says that the definite integral can be computed by finding the indefinite integral of $$f$$ and subtracting the evaluation at the bottom bound from the evaluation at the top bound. Note that even though the indefinite integral is actually a class of functions that differ by a constant, $$F(b)-F(a)$$ has the same value for any function $$F$$ in such a class, so when computing the antiderivative for the purpose of computing a definite integral, it is allowable (and convenient) to forego the constant of integration.

Part 2 can be expressed in a slightly different way which is illustrative. For a differentiable function $$F$$ we have

$$
F \bigg\vert_{x=a}^b = \int_{x=a}^b dF.
$$

This says that the net change in quantity (given on the left side) equals the integral of the rate of change (given on the right side). This interpretation will be used in many applications in the next chapter.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Part 1: By the definition of the derivative, and the definition of the definite integral,

$$
\begin{align*}
\frac{d}{dx}\left(\int_a^x f(t)dt\right) &= \lim_{h \rightarrow 0} \frac{\int_a^{x+h} f(t)dt - \int_a^x f(t)dt}{h}
&= \lim_{h \rightarrow 0} \frac{\int_x^{x+h} f(t)dt}{h}
&= \lim_{h \rightarrow 0} \frac{f(x^\ast) \Delta x}{h}
&= \lim_{h \rightarrow 0} \frac{f(x^\ast) h}{h}
&= \lim_{h \rightarrow 0} f(x^\ast)
&= f(x),
\end{align*}
$$

since $$x \leq x^\ast \leq x+h$$.

Part 2: By Part 1, $$F(x) = \int_a^x f(t)dt$$ is an anti-derivative of $$f$$. Furthermore, we have

$$
\begin{align*}
F(b)-F(a) &= \int_a^b f(t)dt - \int_a^a f(t)dt = \int_a^b f(t)dt - 0 = \int_a^b f(t)dt.
\end{align*}
$$

Let $$G(x)$$ be some anti-derivative of $$f$$. Since anti-derivatives of the same function differ only by a constant, $$G(x) = F(x)-C$$ for some constant $$C$$. Then we have

$$
\begin{align*}
G(b)-G(a) = (F(b)-C) - (F(a)-C) = F(b)-F(a)
\end{align*}
$$

as desired.

**Example**

Compute $$
\int_{x=1}^T \frac{1}{x}\, dx.
$$

<button class="toggle" data-box="#box1a">Answer</button>

<div id="box1a" class="answer-hidden"></div>
{: id="box1a" class="answer-hidden"}


Using Part 2 of the Fundamental Theorem, we find that

$$
\begin{align*}
\int_{x=1}^T \frac{1}{x}\, dx &= \ln x \bigg\vert_{x=1}^T
&= \ln T - \ln 1
&= \ln T.
\end{align*}
$$

Note that the above definite integral is sometimes used as the definition of the natural logarithm.

**Example**

Compute $$
\int_1^3 x^2 dx.
$$

<button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden"></div>
{: id="box1b" class="answer-hidden"}


By Part 2 of FTIC,

$$
\begin{align*}
\int_1^3 x^2 dx &= \frac{1}{3}x^3 \bigg\vert^3_1
&= \frac{1}{3}(3^3 - 1^3)
&= \frac{26}{3}.
\end{align*}
$$

**Example**

Suppose a publisher prints 12000 books per month with expected revenue of $60 per book. The marginal cost of each book is given by

$$
MC(x) = 10 + \frac{1}{2000}x.
$$

What would be the change in profit from a 25% increase in production?

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The additional 25% means an extra 3000 books. So the goal is to find the change in profit $$P$$ as $$x$$ goes from 12000 to 15000. That is,

$$
P \bigg\vert_{x=12000}^{15000} = \int_{x=12000}^{15000} dP,
$$

according to Part 2 of the Fundamental Theorem. Now, since profit is revenue minus cost, it follows that marginal profit is given by

$$
dP = dR - dC.
$$

Here,

$$
dR = MR(x) \, dx = 60 \, dx
$$

since the marginal revenue from each book is $60. And

$$
dC = MC(x) \, dx = 10 + \frac{1}{2000}x \, dx.
$$

Putting it all together, we find that

$$
\begin{align*}
P \bigg\vert_{x=12000}^{15000} &= \int_{x=12000}^{15000} dP
&= \int_{x=12000}^{15000} \left(60-\left(10+\frac{1}{2000}x\right)\right)\, dx
&= \int_{x=12000}^{15000} \left(50 - \frac{1}{2000}x \right)\, dx
&= 50x - \frac{1}{4000}x^2 \bigg\vert_{x=12000}^{15000}
&= \left(50 \cdot 15000 - \frac{15000^2}{4000}\right) - \left(50 \cdot 12000 - \frac{12000^2}{4000}\right)
&= \$129750
\end{align*}
$$

**Example**

Find $$
\frac{d}{dx} \left(\int_0^x \sin(t) dt \right).
$$

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


By Part 1 of FTIC, $$\frac{d}{dx} \left(\int_0^x \sin(t)dt \right) = \sin(x)$$.

**Example**

Find $$
\frac{d}{dx} \left(\int_x^{x^3} \sin(t) dt \right).
$$

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


One must be careful with a function of $$x$$ in one or both bounds. A good way to break the problem down is to write $$F(x) = \int_0^x \sin(t) dt$$. By Part 1 of FTIC, $$F'(x) = \sin(x)$$. Now, note that

$$
\begin{align*}
\int_x^{x^3} \sin(t) dt &= \int_0^{x^3} \sin(t) dt - \int_0^x \sin(t) dt
&= F(x^3) - F(x).
\end{align*}
$$

Next, taking the derivative (and remembering the chain rule) gives

$$
\begin{align*}
\frac{d}{dx} \left( \int_x^{x^3} \sin(t) dt \right) &= \frac{d}{dx}\left(F(x^3) - F(x) \right)
&= F'(x^3)(3x^2) - F'(x)(1)
&= \sin(x^3)(3x^2) - \sin(x).
\end{align*}
$$

Caveat

Note that if the integrand $$f(t)$$ fails to be defined or continuous at a point in the interval $$\left[a,b\right]$$, then the FTIC does not hold. The following example shows this using the singularities of a rational function.

**Example**

Compute $$
\int_1^4 \frac{dx}{x^2-5x+6}.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


This is a rational function, and the denominator factors as $$(x-3)(x-2)$$, so use partial fractions to express

$$
\begin{equation*} \frac{1}{\left(x-3\right)(x-2)} = \frac{A}{x-3} + \frac{B}{x-2}. \end{equation*}
$$

Clearing denominators gives $$1 = A(x-2) + B(x-3)$$. Setting $$x=3$$ gives $$A=1$$. Setting $$x=2$$ gives $$B = -1$$. Thus,

$$
\begin{align*}
\int \frac{dx}{x^2-5x+6} &= \int \left(\frac{1}{x-3} - \frac{1}{x-2}\right)dx
&= \ln\vertx-3\vert - \ln\vertx-2\vert.
\end{align*}
$$

Then trying to apply FTIC would give

$$
\begin{align*}
\int_1^4 \frac{dx}{x^2-5x+6} &= \ln\vertx-3\vert - \ln\vertx-2\vert \bigg\vert^4_1
&= \ln(1) - \ln(2)-(\ln(2)-\ln(1))
&= -2\ln(2).
\end{align*}
$$

However, because $$\frac{1}{\left(x-3\right)(x-2)}$$ has singularities at $$x=2$$ and $$x=3$$, one must evaluate the improper integral as follows:

$$
\begin{align*}
\int_1^4 \frac{dx}{x^2-5x+6} &= \int_1^2 \frac{dx}{x^2-5x+6} + \int_2^3 \frac{dx}{x^2-5x+6} + \int_3^4 \frac{dx}{x^2-5x+6},
\end{align*}
$$

and none of these integrals exist, as will be shown in the next section on improper integrals, so the entire integral does not exist.
Limits of integration and substitution

One must be careful when using Part 2 of the Fundamental Theorem of Integral Calculus along with the method of substitution. The reason this can cause problems is that when a substitution is made, the old limits of integration are still in terms of the original variable. Therefore, one must either get the antiderivative in terms of the original variable before evaluating (this is what we usually did at the end of the substitution anyway), or one can change the limits of integration to reflect the new variable.

Consider the following example which demonstrates both techniques.

**Example**

Compute

$$
\int_{x=0}^1 x(x-1)^n \, dx,
$$

where $$n$$ is some fixed positive constant. <button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


First, we will try the method of substituting back in before evaluating. We make the substitution

$$
\begin{align*}
u &= x-1
du &= dx.
\end{align*}
$$

Then the integral becomes

$$
\begin{align*}
\int_{x=0}^1 x(x-1)^n \, dx &= \int_{x=0}^1 (u+1)u^n \, du
&= \int_{x=0}^1 u^{n+1} + u^n \, du
&= \frac{u^{n+2}}{n+2} + \frac{u^{n+1}}{n+1} \bigg\vert_{x=0}^1.
\end{align*}
$$

This is where a lot of students might make the mistake of plugging in the limits of $$x$$ when trying to evaluate the integral. This is a reason to include the $$x=a$$ at the bottom limit of integration: it helps remind us that those limits are in terms of $$x$$, even if we have made one or more substitution.

To avoid this pitfall, we now finish getting the antiderivative in terms of $$x$$ so that we can evaluate:

$$
\begin{align*}
\frac{u^{n+2}}{n+2} + \frac{u^{n+1}}{n+1} \bigg\vert_{x=0}^1 &= \frac(x-1)^{n+2}}{n+2} + \frac{(x-1)^{n+1}}{n+1} \bigg\vert_{x=0}^1
&= 0 + 0 - \frac{(-1)^{n+2}}{n+2} - \frac{(-1)^{n+1}}{n+1}
&= (-1)^{n+2} \left(\frac{1}{n+1}-\frac{1}{n+2}\right)
&= \frac{(-1)^n}{\left(n+1\right)\left(n+2\right).
\end{align*}
$$

On the other hand, as soon as we made the substitution $$u = x-1$$, we could have changed the limits of integration to reflect our new variable.

Namely, at the lower limit $$x=0$$, what is the corresponding value of $$u$$? Well, $$u = x-1$$, so when $$x=0$$, we have $$u = -1$$. Similarly, when $$x=1$$, the corresponding value of $$u$$ is $$u=0$$. So as we were making our substitution, we could make a corresponding change in the limits of integration so that the new definite integral is entirely in terms of $$u$$:

$$
\begin{align*}
\int_{x=0}^1 x(x-1)^n \, dx &= \int_{u=-1}^0 (u+1)u^n \, du.
\end{align*}
$$

Now the calculation proceeds as before, and gives the same answer. Changing the limits can sometimes be easier, especially in a complicated integral which may involve (for example) a u-substitution and a trigonometric substitution. Otherwise, the algebra can get messy as one substitutes back in and then substitutes back in again.

Another case where one must be careful of the limits of integration is with Integration By Parts. One can compute the indefinite integral completely and then apply the limits of integration, or one can apply them as one goes, as in the following:

$$
\int_a^b u \, dv = uv \bigg\vert_a^b - \int_a^b v \, du.
$$

**Example**

Again compute the definite integral

$$
\int_{x=0}^1 x(x-1)^n \, dx,
$$

but this time using integration by parts. <button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


The logical choice of parts is

$$
\begin{align*}
u &= x & du &= dx
dv &= (x-1)^n \, dx & v &= \frac{(x-1)^{n+1}}{n+1}.
\end{align*}
$$

Then by the formula for parts, we have

$$
\begin{align*}
\int_{x=0}^1 x (x-1)^n \, dx &= x \frac{(x-1)^{n+1}}{n+1}\bigg\vert_{x=0}^1 - \int_{x=0}^1 \frac{(x-1)^{n+1}}{n+1} \, dx
&= 0 - \frac{ (x-1)^{n+2} }{ \left( n+1 \right) \left( n+2 \right) } \bigg\vert_{x=0}^1
&= \frac{ (-1)^{n+2} }{ \left(n+1\right)\left(n+2\right) }
&= \frac{ (-1)^n }{ \left( n+1 \right)\left( n+2 \right) }.
\end{align*}
$$

Note that from the first to second line above, we have $$x \frac{(x-1)^{n+1}}{n+1}$$ is 0 at both $$x=1$$ and at $$x=0$$, so that entire term disappears.
Additional examples

**Example**

Compute

$$
\int_{x=e^3}^{e^5} \frac{\ln x}{x} \, dx.
$$

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


This integral is best computed with a substitution of

$$
\begin{align*}
u &= \ln x
du &= \frac{1}{x} \, dx
\end{align*}
$$

(Integration by parts works too, but it involves a little bit of algebra). Here it is convenient to change the limits of integration as we go, so note that when $$x=e^3$$, we have $$u = 3$$. When $$x=e^5$$ we have $$u = 5$$. Thus,

$$
\begin{align*}
\int_{x=e^3}^{e^5} \frac{\ln x}{x} \, dx &= \int_{u=3}^5 u \, du
&= \frac{1}{2}u^2 \bigg\vert_{u=3}^5
&= \frac{1}{2}\left(25 - 9 \right)
&= \frac{1}{2} \cdot 16
&= 8.
\end{align*}
$$

**Example**

Compute

$$
\int_{x=-1}^1 \frac{1}{1+3x^2} \, dx.
$$

<button class="toggle" data-box="#box8">Answer</button>

<div id="box8" class="answer-hidden"></div>
{: id="box8" class="answer-hidden"}


This looks like a good candidate for a trigonometric substitution. Because of the extra factor of 3, the logical substitution is

$$
\begin{align*}
x &= \frac{1}{\sqrt{3}} \tan \theta
dx &= \frac{1}{\sqrt{3}} \sec^2 \theta \, d\theta.
\end{align*}
$$

Remember the constant $$\frac{1}{\sqrt{3}}$$ is there so that when it is squared it will cancel with the factor of 3 and allow us to use the identity $$1 + \tan^2 = \sec^2$$. Again, we will change the bounds as we go. Note that

$$
\begin{align*}
x = -1 \quad & \Rightarrow \quad \frac{1}{\sqrt{3}} \tan \theta = -1
& \Rightarrow \quad \tan \theta = -\sqrt{3}.
\end{align*}
$$

The value of $$\theta$$ for which this holds is $$\theta = -\frac{\pi}{3}$$. Similarly, when $$x=1$$ we have $$\theta = \frac{\pi}{3}$$. Proceeding, we have

$$
\begin{align*}
\int_{x=-1}^1 \frac{1}{1+3x^2} &= \frac{1}{\sqrt{3}} \int_{\theta = -\pi/3}^{\pi/3} \frac{\sec^2 \theta \, d\theta}{1+3 (\frac{1}{\sqrt{3}} \tan \theta)^2}
&= \frac{1}{\sqrt{3}} \int_{\theta = -\pi/3}^{\pi/3} \frac{\sec^2 \theta \, d\theta}{1+\tan^2 \theta}
&= \frac{1}{\sqrt{3}} \int_{\theta = -\pi/3}^{\pi/3} \frac{\sec^2 \theta}{\sec^2 \theta} \, d\theta
&= \frac{1}{\sqrt{3}} \int_{\theta = -\pi/3}^{\pi/3} d\theta
&= \frac{1}{\sqrt{3}} \theta \bigg\vert_{-\pi/3}^{\pi/3}
&= \frac{1}{\sqrt{3}} \left(\frac{\pi}{3} - \frac{-\pi}{3}\right)
&= \frac{2 \pi}{3 \sqrt{3}}
\end{align*}
$$


## Exercises

- Evaluate the following integrals: 

$$ \displaystyle \int_{x=-1}^1 \frac{dx}{1+x^2} $$
$$ \displaystyle \int_{x=0}^{3} 5x \sqrt{x+1} \, dx $$
$$ \displaystyle \int_{x=-\pi}^\pi \frac{d}{dx} ( x\cos x ) \, dx $$

- Compute the following derivatives: 

$$ \displaystyle \frac{d}{dx} \int_{x=-\pi}^\pi x\cos x \, dx $$
$$ \displaystyle \frac{d}{dx} \int_{t=0}^x \cos t \, dt $$
$$ \displaystyle \frac{d}{dx} \int_{t=x^2}^{x^4} e^{-t^2} \, dt $$
$$ \displaystyle \frac{d}{dx} \int_{t=1}^{x} \frac{1}{\sqrt{t}} \, dt $$
$$ \displaystyle \frac{d}{dx} \int_{t=0}^{\arcsin x} \ln \left\vert \sin t + \cos t \right\vert \, dt $$
$$ \displaystyle \frac{d}{dx} \int_{t=\sin x}^{\tan x} e^{-t^2} \, dt $$

- What is the leading-order term int he Taylor series about $$x=0$$ of 

$$ \displaystyle f(x) = \int_{0}^x\ln(\cosh(t)) dt $$

- We usually use Riemann sums to approximate integrals, but we can go the other way, too, using an antiderivative to approximate a sum. Using only your head (no paper, no calculator), compute an approximation for 

$$ \displaystyle \sum_{n=0}^{100} n^3 $$
Hint: what integral does this resemble?

- Compute $$ \displaystyle \frac{d}{dx} \int_{3x}^{x^4} e^{-t^2/2} dt $$
- Find the critical points of the function $$ f(x) = \int_e^{x^2} \ln(1+t^2)\cos(\sqrt{t}) dt $$ 