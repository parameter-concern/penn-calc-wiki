---
title: Differentiation as an operator
description: Using operators to compute other derivatives
lecture_number: 16
topic_number: 2
layout: lecture
mathjax: true
hidden_answers: true
---
The sum, product, quotient, and chain rules make it possible to differentiate many functions. However, there are some more exotic functions which cannot be differentiated using these tools alone. For example, what is the derivative of $$2^x$$ or $$x^x$$ or $$x^{x^x}$$?

The derivative should be interpreted as a rate of change, but what about the act of differentiation? Differentiation is an operator: it takes in a function and gives out another function. Other examples of operators include the logarithm, exponentiation, and integration. These (and other) operators can be applied to an entire equation to transform a hard problem to an easy problem and (once the solution is found) back again. This idea will allow us to compute the derivatives of the exotic functions above, and more.
Logarithmic differentiation

A common combination is called logarithmic differentiation, which consists of applying the logarithm operator followed by the differentiation operator. It is best demonstrated by example.

**Example**

Find the derivative of $$e^x$$ using logarthmic differentiation. <button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


We already know the derivative of $$e^x$$, but suppose we did not. Let $$y = e^x$$. Then applying the logarithm operator to this equation gives

$$
\ln y = \ln(e^x) = x.
$$

Now applying the differentiation operator to the equation (and remembering the chain rule) gives

$$
\frac{dy}{y} = dx,
$$

so $$\frac{dy}{dx} = y$$, and since $$y=e^x$$ from our original definition, we have

$$
\frac{dy}{dx} = e^x,
$$

as expected.

**Example**

Use logarithmic differentiation to show that $$\frac{d}{dx}(a^x) = a^x \ln a$$. <button class="toggle" data-box="#box0b">Answer</button>

<div id="box0b" class="answer-hidden"></div>
{: id="box0b" class="answer-hidden"}


Similarly to the above example, let $$y = a^x$$. Then taking the logarithm gives

$$
\ln y = \ln(a^x) = x \ln a.
$$

Differentiating gives

$$
\frac{dy}{y} = (\ln a) \, dx
$$

And so

$$
\frac{dy}{dx} = y (\ln a) = a^x \ln a,
$$

as desired.

**Example**

Find the derivative of $$x^x$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Let $$y=x^x$$. Taking the logarithm gives

$$
\ln y = x \ln x.
$$

Differentiating (using the product rule on the right) gives that

$$
\frac{dy}{y} = x \frac{1}{x}\,dx + \ln x\,dx.
$$

Next, factoring and solving for $$\frac{dy}{dx}$$ gives

$$
\frac{dy}{dx} = y(1+\ln x) = x^x(1+\ln x)
$$

**Example**

Find the derivative of $$f(x)^{g(x)}$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Let $$y=f(x)^{g(x)}$$. Applying the logarithm gives $$\ln y = g(x) \ln f(x)$$, and differentiating gives

$$
\frac{dy}{y} = g(x) \frac{1}{f(x)}f'(x)\,dx + g'(x) \ln f(x)\, dx.
$$

Factoring and solving for $$\frac{dy}{dx}$$ shows

$$
\begin{align*}
\frac{dy}{dx} &= y\left[g(x) \frac{1}{f(x)}f'(x) + g'(x) \ln f(x)\right]
&= f(x)^{g(x)} \left[\frac{g(x)}{f(x)}f'(x) + g'(x) \ln f(x) \right]
\end{align*}
$$

Other operators

There are other operators which can be used prior to differentiation. Consider the following examples.

**Example**

Compute the derivative of $$\ln x$$ by using exponentiation followed by differentiation. <button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


Letting $$y = \ln x$$, we exponentiate the equation to find

$$
e^y = x.
$$

Now, differentiating gives

$$
e^y \, dy = dx,
$$

and solving for $$\frac{dy}{dx}$$ gives

$$
\frac{dy}{dx} = \frac{1}{e^y} = \frac{1}{e^{\ln x}} = \frac{1}{x},
$$

as desired.

Note that $$\ln x$$ is the inverse of $$e^x$$, and so when we exponentiated the equation, it could be thought of as applying the inverse of $$\ln x$$. This same method works for many other inverse functions. In particular, applying a trigonometric function can be thought of as an operator as well. This method can be used to find the derivatives of the various inverse trigonometric functions.

**Example**

Find the derivative of $$\arcsin(x)$$. <button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


Letting $$y = \arcsin x$$, take the sine of the equation to find

$$
\sin y = x.
$$

Now, differentiating gives

$$
\cos y \, dy = dx.
$$

Thus, we find that

$$
\frac{dy}{dx} = \frac{1}{\cos y}.
$$

Now, a little bit of trigonometry helps rewrite $$\sec y$$ in terms of $$x$$. Our original equation had $$y = \arcsin x$$. That means that $$y$$ is the angle such that $$\sin y = x$$. Since sine is the opposite over the hypotenuse, we can express this relationship with the following right triangle:

where the adjacent leg comes from the Pythagorean theorem. It follows that $$\cos y = \sqrt{1-x^2}$$, and so we find

$$
\frac{dy}{dx} = \frac{1}{\cos y} = \frac{1}{\sqrt{1-x^2}}.
$$

**Example**

Find the derivative of $$\arctan(x)$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Let $$y = \arctan(x)$$. Applying $$\tan$$ to the equation gives

$$
\tan y = x,
$$

and differentiating gives

$$
\sec^2y\,dy = dx.
$$

Therefore,

$$
\begin{align*}
\frac{dy}{dx} &= \frac{1}{\sec^2y}
\end{align*}
$$

We can now do similar right triangle trig as in the previous example. Or we can recall that by the Pythagorean identity for tangent and secant, we have

$$
\tan^2y + 1 = \sec^2y
$$

Making this substitution gives

$$
\begin{align*}
\frac{dy}{dx} &= \frac{1}{\sec^2y}
&= \frac{1}{\tan^2y + 1}
&= \frac{1}{x^2+1}.
\end{align*}
$$

Operators in other contexts

Besides being useful in computing derivatives of exotic functions, operators (especially the logarithm) can also be useful in computing limits. The method is similar to the above method for derivatives.

**Example**

Show that

$$
\lim_{x \rightarrow \infty} \left(1+\frac{a}{x}\right)^x = e^a.
$$

This is a common limit which will come up again in the course. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Let $$y$$ be the function given by

$$
y = \left(1+\frac{a}{x}\right)^x.
$$

Take the logarithm of both sides, and use the power property of logarithms to see

$$
\begin{align*}
\ln y &= \ln \left(1+\frac{a}{x}\right)^x
&= x \ln \left(1+\frac{a}{x}\right).
\end{align*}
$$

Now, taking the limit of both sides gives

$$
\begin{align*}
\lim_{x \rightarrow \infty} \ln y &= \lim_{x \rightarrow \infty} x \ln \left(1+\frac{a}{x}\right).
\end{align*}
$$

Now, since $$x \rightarrow \infty$$, we have that $$\frac{a}{x}$$ is small, and so we can use our Taylor series for $$\ln(1+x)$$, which gives us that

$$
\begin{align*}
\lim_{x \rightarrow \infty} \ln y &= \lim_{x \rightarrow \infty} x \ln\left(1+\frac{a}{x}\right)
&= \lim_{x \rightarrow \infty} x \left(\frac{a}{x} + O\left(\frac{1}{x^2}\right) \right)
&= \lim_{x \rightarrow \infty} a + O \left(\frac{1}{x}\right)
&= a.
\end{align*}
$$

Recall from our limit rules that the order of the logarithm and the limit can be switched since the logarithm is a continuous function. Thus

$$
\ln \left(\lim_{x \rightarrow \infty} y \right) = a.
$$

So, exponentiating both sides, we have that

$$
\lim_{x\rightarrow \infty} y = e^a,
$$

as desired.
Infinite Power Tower

Consider the infinite power tower

$$
y = x^{x^{x^{x^{\dotsb}}}}.
$$

That is, $$x$$ raised to the $$x$$ raised to the $$x$$ etc. This is certainly an unusual function. A better way to define this function is implicitly:

$$
y = x^y.
$$

To see that this makes intuitive sense, note that the exponent of the first $$x$$ in the infinite tower is itself an infinite tower, so replacing the exponent of $$x$$ with $$y$$ is sensible.

Use logarithmic differentiation to find the derivative of this function (that is, $$\frac{dy}{dx}$$).

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


First, taking the logarithm gives

$$
\ln y = y \ln x.
$$

Now, differentiating the equation (implicitly) gives

$$
\frac{dy}{y} = \ln x \, dy + y \frac{dx}{x}
$$

Factoring and solving for $$\frac{dy}{dx}$$ gives

$$
\begin{align*}
\left(\frac{1}{y} - \ln x\right)dy &= y \frac{dx}{x}
\frac{dy}{dx} &= \frac{y}{x \left(1/y-\ln x\right)}
&= \frac{y^2}{x (1- y \ln x)}.
\end{align*}
$$

This shows that although a function may be difficult to understand, it can nevertheless be fairly easy to find its derivative.

It turns out that this function is well-defined and differentiable on

$$
e^{-e} < x < e^{1/e}
$$

One can check that the $$(x,y)$$ pairs $$(e^{-e},e^{-1}),(1,1),(\sqrt{2},2),(e^{1/e},e)$$ all satisfy the above implicit equation.

## Exercises

- Find the derivative of $$f(x) = (\ln x)^x$$
- Find the derivative of $$f(x) = x^{\ln x}$$
- Compute $$ \displaystyle \lim_{x \to +\infty} \left( \frac{x+2}{x+3} \right)^{2x} $$
- Compute $$ \displaystyle \lim_{x \to 0^+} \left[ \ln(1+x) \right]^{x} $$
- Compute $$ \displaystyle \lim_{x \to 0} \left(1 + \arctan\frac{x}{2} \right)^{2/x} $$
- Compute $$ \displaystyle \lim_{x \to 0^+} \left(\frac{2}{x}\right)^{\sin x} $$
- Let 

$$
\alpha =1 + \frac{2}{2+ \frac{2}{2+ \frac{2}{2+\cdots}}}
$$

What is the value of $$\alpha$$?

- Let 

$$
\varphi = \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+\cdots}}}}}
$$

What is the value of $$\varphi$$? 