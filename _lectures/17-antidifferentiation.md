---
title: Antidifferentiation
description: The indefinite integral and separable differential equations
lecture_number: 17
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
This module begins our study of integration. Integration, or anti-differentiation, can be thought of as running differentiation in reverse, or undoing the derivative.

This motivates the following definition:

The Indefinite Integral

The indefinite integral of $$f(t)$$, denoted $$\int f(t)\,dt$$, is the class of functions whose derivative is $$f(t)$$. $$\int f(t)\,dt$$ is also referred to as the anti-derivative of $$f$$. The act of taking the indefinite integral is an operator which is referred to as anti-differentiation or integration.
Note

The indefinite integral of a function is only defined up to an added constant, called the constant of integration. In other words, if $$F(x)$$ is an anti-derivative of $$f(x)$$, then $$G(x)=F(x)+C$$, $$C$$ a constant, is also an anti-derivative of $$f$$, because $$C$$ disappears when differentiated. Conversely, any two indefinite integrals of $$f(x)$$ differ only by some constant.

Any of the known derivatives from the previous chapter can be rephrased as an integral. For example, just as there was a power rule for differentiating monomials, there is a corresponding power rule for integrating monomials. And any anti-derivative can easily be checked by taking the derivative and seeing that the result gives back the original function.

**Example**

Give the integral of each of the following functions: $$x^n$$, $$\frac{1}{x}$$, $$\sin x$$, $$\cos x$$, $$e^x$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


$$
\begin{align*}
\int x^n dx &= \frac{1}{n+1}x^{n+1} + C
\int \frac{1}{x} dx &= \ln \vertx\vert + C
\int \sin x dx &= - \cos x + C
\int \cos x dx &= \sin x + C
\int e^x dx &= e^x + C
\end{align*}
$$

(Don't forget the constant!)

There are other functions which are harder to integrate by merely using one of the derivatives we already know. Some of these can be integrated using other techniques from upcoming modules, but there are also functions whose anti-derivative cannot be expressed in terms of simple functions.
Differential equations

The motivating problem for the study of anti-differentiation is solving a differential equation. A differential equation is an equation involving a function and its derivative. In this course, we deal with ordinary differential equations, ODEs, which are differential equations involving only functions of one variable and the derivative with respect to that variable (future courses deal with partial differential equations, which involve functions of several variables and partial derivatives).

Solving a differential equation means finding the function (or class of functions, usually) which satisfy the differential equation.
A Simple ODE

The simplest differential equation is of the form

$$
\frac{dx}{dt} = f(t).
$$

Here, the goal is to find the function $$x(t)$$ whose derivative with respect to $$t$$ is $$f(t)$$. But this is precisely what the integral is. And so, the solution of the differential equation $$\frac{dx}{dt} = f(t)$$ is given by $$x(t) = \int f(t)dt$$.

Using the interpretation of the derivative as slope, one can think of the function $$f(t)$$ as describing the slope of the function $$x(t)$$:

Thus, $$x(t)$$ is a function which fits the slopes prescribed by $$f(t)$$. Note that any constant vertical shift of a solution $$x(t)$$ will still have the same slope at each point. This is one interpretation of the integration constant: it represents the potential vertical shifts to a solution of the differential equation.

**Example**

Consider a falling object. Let $$x(t)$$ be the height of the object at time $$t$$, $$v(t)$$ be the velocity of the object, and assume that acceleration is the constant $$-g$$ (negative because gravity pulls down). Express the height of the object as a function of $$t$$, $$v_0$$, and $$x_0$$; here, $$v_0$$ and $$x_0$$ are the velocity and height of the object, respectively, at time $$t=0$$.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


We know from an earlier module that

$$
\frac{dv}{dt} = a = -g.
$$

Beginning with the second of these equations, we find that

$$
v(t) = \int (-g) \, dt = -gt + C.
$$

We can determine $$C$$ by plugging in $$t=0$$. This cancels that $$-gt$$ and leaves us with $$C = v(0) = v_0$$, the initial velocity. Thus,

$$
v(t) = -gt + v_0
$$

Now, using the fact that

$$
\frac{dx}{dt} = v,
$$

we find that

$$
\begin{align*}
x(t) &= \int v(t) \, dt
&= \int (-gt + v_0) \, dt
&= -\frac{1}{2}gt^2 + v_0t + C.
\end{align*}
$$

Again, we can find $$C$$ by plugging in $$t=0$$. This leaves us with $$x(0) = C$$, and so $$C=x_0$$, the initial height. Thus,

$$
x(t) = -\frac{1}{2}gt^2 + v_0t + x_0.
$$

The Next Simplest ODE

Another slightly more complex ODE is of the form

$$
\frac{dx}{dt} = f(x).
$$

Before we discuss how to solve this in general, we consider a specific example, which is one of the most famous differential equations:

$$
\frac{dx}{dt} = ax,
$$

where $$a$$ is a constant. We solve this differential equation in three different ways:

- (Guess) Solve this differential equation by first observing that $$x = Ce^t$$ satisfies $$\frac{dx}{dt} = x$$ and then adjusting the exponent so that an extra factor of $$a$$ comes out when differentiating. Hint: remember the chain rule. <button class="toggle" data-box="#box3a">Answer</button>

<div id="box3a" class="answer-hidden"></div>
{: id="box3a" class="answer-hidden"}
 

Observe that $$x = Ce^{at}$$ will get an extra factor of $$a$$ when differentiated by the chain rule. That is,

$$
\frac{d}{dt} \left(Ce^{at}\right) = a Ce^{at}.
$$

And so $$x(t) = Ce^{at}$$ is a solution of the differential equation.

- (Series) Solve the differential equation by assuming 

$$
x(t) = c_0 + c_1 t + c_2 t^2 + c_3t^3 + \dotsb
$$

and then determining what the constants $$c_i$$ must be to satisfy the differential equation. <button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


Assuming that

$$
x(t) = c_0 + c_1 t + c_2 t^2 + c_3t^3 + \dotsb,
$$

and then taking the derivative of this series, term by term, we find

$$
\frac{dx}{dt} = 0 + c_1 + 2c_2 t + 3c_3t^2 + \dotsb.
$$

On the other hand, from the original differential equation we have

$$
\begin{align*}
\frac{dx}{dt} &= a x
& = a \left(c_0 + c_1 t + c_2t^2 + c_3t^3+\dotsb\right)
&= ac_0 + ac_1 t + ac_2t^2 + ac_3t^3 + \dotsb.
\end{align*}
$$

Because these two series both equal $$\frac{dx}{dt}$$, they must be equal to each other. But two series are equal if and only if their corresponding coefficients are equal. Therefore,

$$
\begin{align*}
c_1 &= a c_0
2c_2 &= a c_1
3c_3 &= a c_2,
\end{align*}
$$

and so on. Solving these equations one by one gives

$$
\begin{align*}
c_1 &= ac_0
c_2 &= \frac{1}{2}a c_1= \frac{1}{2}a^2 c_0
c_3 &= \frac{1}{3}a c_2= \frac{1}{6}a^3 c_0
\end{align*}
$$

And, generally, $$c_n = \frac{1}{n!}a^n c_0$$ (this can be proven using a method called induction). Doing a little bit of factoring and grouping of factors, we find

$$
\begin{align*}
x(t) &= c_0 + ac_0 t + \frac{1}{2!} a^2 c_0 t^2 + \frac{1}{3!} a^3 c_0 t^3 + \dotsb
&= c_0 \left(1 + (at) + \frac{1}{2!}(at)^2 +\frac{1}{3!}(at)^3 + \dotsb \right)
&= c_0 e^{at},
\end{align*}
$$

which is, again, of the form $$Ce^{at}$$.

- (Integration) Rearrange the differential equation into the form 

$$
\frac{dx}{x} = a \, dt
$$

and integrate both sides to solve the differential equation. <button class="toggle" data-box="#box3c">Answer</button>

<div id="box3c" class="answer-hidden"></div>
{: id="box3c" class="answer-hidden"}


Using the chain rule and substituting according to the differential equation, we have

$$
\begin{align*}
dx &= \frac{dx}{dt} \, dt
dx &= a x \, dt
\frac{dx}{x} &= a \, dt.
\end{align*}
$$

Integrating both sides of the equation gives

$$
\ln x = at+C
$$

(only one constant of integration is necessary here, because a constant on the left side could be subtracted from both sides and absorbed into $$C$$). Now, exponentiating the equation gives $$x = e^{at+C}$$. By exponential rules, $$e^{at+C} = e^{at}e^C$$, and the $$e^C$$ is often rewritten as a new constant, often written $$C$$ again.

Thus, the solution to $$\frac{dx}{dt} = ax$$ is $$x(t) = Ce^{at}$$, where $$C$$ is any constant.

The differential equation from this example is sometimes used as a simple model of population growth. In words, the differential equation says that the growth of a population is proportional to the size of the population. As the solution above slows, this model implies the population has exponential growth. This is not a very good model for most populations because of competition for resources and overcrowding. But under certain conditions and for short periods of time, some populations (for instance, bacteria with an abundant food supply) do exhibit exponential growth. For more examples of exponential growth, see the next module.
Initial value problems

Although a general differential equation's solution often depends on a constant (sometimes several), an additional condition called an initial value or initial condition can specify a specific solution. This condition is usually of the form $$y(t_0) = y_0$$. A differential equation with such an initial condition is called an initial value problem. To solve such a problem, first find the general solution and then use the initial value to find the specific constant of integration which satisfies the initial condition.

In the context of population growth, the initial value is typically the size of the population at time 0. This is particularly nice in the exponential growth model, because the solution is of the form $$P(t) = De^{At}$$. So if $$P(0) = P_0$$ is given, then plugging this in gives $$P(t) = P_0e^{At}$$.

## Exercises

- $$ \displaystyle \int (4x^3 + 3x^2 + 2x + 1) \, dx = $$
- $$ \displaystyle \frac{d}{dx} \int \ln \tan x \, dx = $$
- $$ \displaystyle \int \left( \frac{d}{dx} e^{-x} \right) \, dx = $$
- Find the general solution of the differential equation 

$$ \displaystyle \frac{dx}{dt} = t^2 $$

- Find the general solution of the differential equation 

$$ \displaystyle \frac{dx}{dt} = x^2 $$

- There is a large class of differential equations -- the so-called "linear" ones -- for which we can find solutions using the Taylor series method discussed in the Lecture. One such differential equation is 

$$ \displaystyle t \frac{d^2x}{dt^2} + \frac{dx}{dt} + tx = 0 $$
This is a particular case of the more general "Bessel differential equation", and one solution of it is given by the Bessel function $$J_0(t)$$ that we saw earlier. Notice that this involves not only the first derivative but also the second derivative. For this reason, it is said to be a "second order" differential equation.
In this problem we will content ourselves with finding a relationship (specifically, a "recurrence relation") on the coefficients of a Taylor series expansion about $$t=0$$ of a solution to our equation. Hence consider the Taylor series
$$ \displaystyle x(t) = \sum_{k=0}^\infty c_k t^k $$
Substituting this into the differential equation above will give you two conditions. The first one is $$c_1 = 0$$. What is the other one?
"Note:" this problem involves some nontrivial manipulation of indices in summation notation. Do not get discouraged if it feels more difficult than other problems: it is!

- Find the general solution of the differential equation 

$$ \displaystyle \frac{dx}{dt} = t^3+x^2t^3 $$ 