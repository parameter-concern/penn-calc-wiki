---
title: Integration by Substitution
description: Substitution as an integration technique
lecture_number: 21
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
The previous modules gave some of the motivation for integration as a method of solving differential equations. In this and the next few modules, we turn to techniques of integration.
Integration rules

Since integration is the inverse of differentiation, one can turn differentiation rules into integration rules. For example, by the linearity of the derivative, we have linearity of the integral:

$$
\begin{align*}
\int (u+v) \, dx &= \int u \, dx + \int v \, dx
\int (c u) \, dx &= c \int u \, dx
\end{align*}
$$

where $$c$$ is a constant. In other words, integration is a linear operator.

The rest of this module deals with turning the chain rule for differentiation into a rule for integration. This rule is called substitution, or u-substitution traditionally.
Substitution: the chain rule in reverse

Recall the chain rule, which says that if $$u = u(x)$$ is a function of $$x$$, then

$$
du = \frac{du}{dx} dx.
$$

Now if $$f = f(u)$$ is a function of $$u$$, then we find

$$
\int f(u) \, du = \int f(u(x)) \frac{du}{dx} \, dx
$$

(To get from the left side to the right, all we have done is replace $$u$$ and $$du$$ by $$u(x)$$ and $$\frac{du}{dx}dx$$, respectively). This is the formula for substitution, or u-substitution.

Substitution is a useful technique but is not always easy to apply. In a typical problem, one encounters the right side of the above equation, but without knowing what $$f$$ and $$u$$ are. If one can find the correct $$f$$ and $$u$$ so that the integral can be expressed as above, then one can switch over to the left side of the above equation, which is usually easier to evaluate.

**Example**

Compute

$$
\int e^{\sin x} \cos x \, dx.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Let $$u = \sin x$$ and $$f(u) = e^u$$. Then

$$
du = \frac{du}{dx} \, dx = \cos x \, dx,
$$

and

$$
\begin{align*}
\int e^{\sin x} \cos x \, dx &= \int f(\sin x) d(\sin x)
&= \int f(u) \, du
&= \int e^u \, du
&= e^u + C
&= e^{\sin x} + C.
\end{align*}
$$

Note that after evaluating the integral in terms of $$u$$, we usually replace $$u$$ with its function of $$x$$, since the original integral was with respect to $$x$$.

We can check that this is the correct antiderivative by differentiating (remembering to apply the chain rule) and seeing that we get back the function which we were integrating originally.

Typically, we need not write out all the details of what $$f$$ is. It is sufficient to identify $$u$$ and $$du$$ and then make the necessary substitutions.

**Example**

Compute

$$
\int 2xe^{x^2} \, dx.
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The inner function here looks like $$u = x^2$$. Then $$du = 2x \, dx$$, which is the remaining factor in the integrand. Thus,

$$
\begin{align*}
\int 2x e^{x^2} \, dx &= \int e^u \, du 
&= e^u + C 
&= e^{x^2} + C.
\end{align*}
$$

It is not always so easy to see the ideal choice of $$u$$, and sometimes it might take a few tries to find the right substitution. Usually, a good strategy is to look for the inner function of a composition of functions and let that be $$u$$. Another idea is to look for a function whose derivative is also a factor of the integrand.

**Example**

Compute

$$
\int x \sqrt{x-1} \, dx
$$

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Here, the inner function seems to be $$x-1$$. So let $$u = x-1$$. Then $$du = dx$$. This takes care of what is under the square root, and the differential, but what about the extra factor of $$x$$? We can take care of this factor by noting that $$u = x-1$$ implies $$x = u+1$$. So the integral becomes

$$
\begin{align*}
\int x \sqrt{x-1} \, dx &= \int (u+1) \sqrt{u} \, du
&= \int (u+1)u^{1/2} \, du
&= \int u^{3/2} + u^{1/2} \, du
&= \frac{2}{5}u^{5/2} + \frac{2}{3}u^{3/2} + C
&= \frac{2}{5}(x-1)^{5/2} + \frac{2}{3}(x-1)^{3/2} + C.
\end{align*}
$$

From the third to the fourth line above, we used the power rule on each term of the integrand. Again, we can differentiate to make sure we get back to our original integrand (though it might require a little algebra to show that they are in fact equal).

Another general tip for integration by substitution is to try to simplify the integrand as much as possible before integrating.

**Example**

Compute

$$
\int \cot \theta \csc \theta \, d\theta.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Since cotangent and cosecant are not very familiar functions, it is helpful to rewrite them in terms of sine and cosine. This gives

$$
\begin{align*}
\int \cot \theta \csc \theta \, d\theta &= \int \frac{\cos \theta}{\sin \theta} \cdot \frac{1}{\sin \theta} \, d\theta
&= \int \frac{\cos \theta}{\sin^2 \theta} \, d\theta.
\end{align*}
$$

It is easier now to see that $$u = \sin \theta$$ is a good choice, since its derivative $$du = \cos \theta \, d\theta$$ is in the numerator. Making this substitution shows

$$
\begin{align*}
\int \frac{\cos \theta}{\sin^2 \theta} \, d\theta &= \int \frac{1}{u^2} \, du
&= \int u^{-2} \, du
&= -u^{-1} + C
&= -\frac{1}{\sin \theta} + C
&= -\csc \theta + C.
\end{align*}
$$

Of course, if one happened to remember the fact that

$$
\frac{d}{d\theta} \csc \theta = -\csc \theta \cot \theta,
$$

then we would not require a substitution. But substitution allows us to do these integrals (and harder ones) without needing to memorize a lot of information.

**Example**

The Gompertz model for the size $$N(t)$$ of a tumor at time $$t$$ is

$$
\frac{dN}{dt} = -aN\ln (bN),
$$

where $$a>0$$ and $$0 < b < 1$$ are constants. Solve this differential equation. Hint: it is separable.

Then find the limit behavior

$$
\lim_{t \rightarrow \infty} N(t).
$$

Finally, find the equilibria of the original differential equation and classify them as stable or unstable.

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Separating variables and integrating both sides gives

$$
\int \frac{dN}{N \ln(bN)} = \int -a \, dt.
$$

The right side is easy, but the left side requires some work. Looking for a function whose derivative is a factor in the integrand, we see that $$u = \ln(bN)$$ is a good choice. In this case

$$
du = \frac{1}{bN} \cdot b \, dN = \frac{dN}{N}.
$$

And so, the integral on the left above becomes

$$
\begin{align*}
\int \frac{dN}{N \ln(bN)} &= \int \frac{1}{u} \, du
&= \ln u + C
&= \ln \ln (bN) + C.
\end{align*}
$$

Putting this together with the integral on the right above (and combining the integration constants to one integration constant on the right), we have

$$
\ln \ln (bN) = -at + C
$$

Exponentiating twice and then dividing by $$b$$ gives

$$
N = \frac{1}{b}e^{e^{-at+C}} = \frac{1}{b}e^{Ce^{-at}}.
$$

By plugging in $$t=0$$, we find that $$C = \ln (bN_0)$$, where $$N_0$$ is the initial size of the tumor.

In the long run, the exponential $$e^{-at} \rightarrow 0$$, since $$a>0$$ by assumption. Therefore, the entire exponent is going to 0, and so

$$
\lim_{t \rightarrow \infty} N(t) = \frac{1}{b}.
$$

Note that $$N(t) = \frac{1}{b}$$ is an equilibrium solution to the original differential equation, since it gives $$\frac{dN}{dt} = 0$$. It is a stable equilibrium since the graph of of $$-aN \ln(bN)$$ goes from positive to negative as $$N$$ goes from less than $$\frac{1}{b}$$ to greater than $$\frac{1}{b}$$.

Another equilibrium is $$N=0$$. This is unstable, since $$N>0$$ means $$\frac{dN}{dt}>0$$. Intuitively, even if the tumor is very tiny, it will grow according to this model.

**Example**

Compute

$$
\int 4 (2x+5)^4 dx.
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


In this case, the inner function is $$u = 2x+5$$, and one finds that $$du = 2dx$$. Thus $$dx = \frac{du}{2}$$, which gives

$$
\begin{align*}
\int 4(2x+5)^4 dx &= \int 4 u^4 \frac{du}{2} 
&= \int 2u^4du 
&= \frac{2}{5}u^5 +C
&= \frac{2}{5}(2x+5)^5 +C.
\end{align*}
$$

Perspective

The big idea of this module is that a change of variables (a substitution of one variable for a function of another) can change a difficult integral into an easier one. After computing the easier integral, we can change the variables back again. This idea will come up again in this course and in multivariable calculus.
Additional Examples

**Example**

Compute

$$
\int \frac{(\ln x)^2}{x} \, dx.
$$

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


Here, a good inner function is $$u = \ln x$$, because the derivative $$du = \frac{1}{x}\, dx$$. Thus

$$
\begin{align*}
\int \frac{(\ln x)^2}{x} \, dx &= \int u^2 \, du
&= \frac{u^3}{3} + C
&= \frac{(\ln x)^3}{3} + C.
\end{align*}
$$

**Example**

Compute

$$
\int \tan \theta \, d\theta.
$$

<button class="toggle" data-box="#box8">Answer</button>

<div id="box8" class="answer-hidden"></div>
{: id="box8" class="answer-hidden"}


First, rewrite tangent in terms of sine and cosine:

$$
\int \tan \theta \, d \theta = \int \frac{\sin \theta}{\cos \theta} \, d \theta
$$

Now, note that $$u = \sin \theta$$ would not work, because its derivative, $$\cos \theta$$ is in the denominator. On the other hand, $$u = \cos \theta$$ is a good substitution because its derivative (up to a constant) is in in the numerator. That is, $$du = -\sin \theta \, d\theta$$. Therefore,

$$
\begin{align*}
\int \frac{\sin \theta}{\cos \theta} \, d \theta &= \int -\frac{1}{u} \, du
&= - \ln(u) + C
&= - \ln(\cos \theta) + C.
\end{align*}
$$

**Example**

Compute

$$
\int x^5 \sqrt{1+x^3} \, dx.
$$

<button class="toggle" data-box="#box9">Answer</button>

<div id="box9" class="answer-hidden"></div>
{: id="box9" class="answer-hidden"}


The logical choice of inner function is $$u = 1+x^3$$, which gives $$du = 3x^2 \, dx$$ and so

$$
dx = \frac{du}{3x^2}
$$

Substituting in, we find

$$
\begin{align*}
\int x^5 \sqrt{1+x^3} \, dx &= \int x^5 \sqrt{u} \frac{du}{3x^2}
&= \frac{1}{3} \int x^3 \sqrt{u} \, du.
\end{align*}
$$

This seems problematic, because we haven't been able to get everything in terms of $$u$$. But we can use our original substitution to help. Since $$u = 1+ x^3$$, we have that $$x^3 = u-1$$, and so

$$
\begin{align*}
\frac{1}{3} \int x^3 \sqrt{u} \, du &= \frac{1}{3} \int (u-1)\sqrt{u} \, du
&= \frac{1}{3} \int u^{3/2} - u^{1/2} \, du
&= \frac{1}{3} \left( \frac{2}{5}u^{5/2} - \frac{2}{3}u^{3/2} \right) + C
&= \frac{2}{15}(1+x^3)^{5/2} - \frac{2}{9}(1+x^3)^{3/2} + C.
\end{align*}
$$


## Exercises

- Compute the integral $$ \displaystyle \int 3\cos x \, dx $$
- Compute the integral $$ \displaystyle \int x \sec^2 x^2 \, dx $$
- Compute the integral $$ \displaystyle \int \frac{4x}{(x^2 - 1)^3} \, dx $$
- Compute the integral $$ \displaystyle \int \frac{e^{\sqrt{x}}}{\sqrt{x}} \, dx $$
- Compute the integral $$ \displaystyle \int \frac{ \ln(15x^5)}{x} \, dx $$
- Compute the integral $$ \displaystyle \frac{x\, dx}{\sqrt{x+3}} \, dx $$
- Compute the integral $$ \displaystyle \frac{dx}{x\sqrt{x^2-1}} \, dx $$ using the substitution $$ u = \sqrt{x^2-1} $$
- Now do the same integral using the substitution $$ u = x^{-1} $$ What is going on here?
- Compute the integral $$ \displaystyle \frac{dx}{x \sqrt{x^2+1}} \, dx $$ 