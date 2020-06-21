---
title: Differentiation as an operator
description: Using operators to compute other derivatives
lecture_number: 16
topic_number: 2
layout: lecture
mathjax: true
---
The sum, product, quotient, and chain rules make it possible to differentiate many functions. However, there are some more exotic functions which cannot be differentiated using these tools alone. For example, what is the derivative of ($2^x$) or ($x^x$) or ($x^{x^x}$)?

The derivative should be interpreted as a rate of change, but what about the act of differentiation? Differentiation is an operator: it takes in a function and gives out another function. Other examples of operators include the logarithm, exponentiation, and integration. These (and other) operators can be applied to an entire equation to transform a hard problem to an easy problem and (once the solution is found) back again. This idea will allow us to compute the derivatives of the exotic functions above, and more.
Logarithmic differentiation

A common combination is called logarithmic differentiation, which consists of applying the logarithm operator followed by the differentiation operator. It is best demonstrated by example.

Example

Find the derivative of ($e^x$) using logarthmic differentiation. (:toggle hide show="Answer" box0:)

We already know the derivative of ($e^x$), but suppose we did not. Let ($y = e^x$). Then applying the logarithm operator to this equation gives

(:latex:) \[ \ln y = \ln(e^x) = x. \] (:latexend:)

Now applying the differentiation operator to the equation (and remembering the chain rule) gives

(:latex:) \[ \frac{dy}{y} = dx, \] (:latexend:)

so ($\frac{dy}{dx} = y$), and since ($y=e^x$) from our original definition, we have

(:latex:) \[ \frac{dy}{dx} = e^x, \] (:latexend:)

as expected.

Example

Use logarithmic differentiation to show that ($\frac{d}{dx}(a^x) = a^x \ln a$). (:toggle hide show="Answer" box0b:)

Similarly to the above example, let ($y = a^x$). Then taking the logarithm gives

(:latex:) \[ \ln y = \ln(a^x) = x \ln a. \] (:latexend:)

Differentiating gives

(:latex:) \[ \frac{dy}{y} = (\ln a) \, dx \] (:latexend:)

And so

(:latex:) \[ \frac{dy}{dx} = y (\ln a) = a^x \ln a, \] (:latexend:)

as desired.

Example

Find the derivative of ($x^x$). (:toggle hide show="Answer" box1:)

Let ($y=x^x$). Taking the logarithm gives

(:latex:) \[ \ln y = x \ln x. \] (:latexend:)

Differentiating (using the product rule on the right) gives that

(:latex:) \[ \frac{dy}{y} = x \frac{1}{x}\,dx + \ln x\,dx. \] (:latexend:)

Next, factoring and solving for ($\frac{dy}{dx}$) gives

(:latex:) \[ \frac{dy}{dx} = y(1+\ln x) = x^x(1+\ln x) \] (:latexend:)

Example

Find the derivative of ($f(x)^{g(x)}$). (:toggle hide show="Answer" box2:)

Let ($y=f(x)^{g(x)}$). Applying the logarithm gives ($\ln y = g(x) \ln f(x)$), and differentiating gives

(:latex:) \[ \frac{dy}{y} = g(x) \frac{1}{f(x)}f'(x)\,dx + g'(x) \ln f(x)\, dx. \] (:latexend:)

Factoring and solving for ($\frac{dy}{dx}$) shows

(:latex:) \begin{align*} \frac{dy}{dx} &= y\left[g(x) \frac{1}{f(x)}f'(x) + g'(x) \ln f(x)\right]
&= f(x)^{g(x)} \left[\frac{g(x)}{f(x)}f'(x) + g'(x) \ln f(x) \right]
\end{align*} (:latexend:)
Other operators

There are other operators which can be used prior to differentiation. Consider the following examples.

Example

Compute the derivative of ($\ln x$) by using exponentiation followed by differentiation. (:toggle hide show="Answer" box2b:)

Letting ($y = \ln x$), we exponentiate the equation to find

(:latex:) \[ e^y = x. \] (:latexend:)

Now, differentiating gives

(:latex:) \[ e^y \, dy = dx, \] (:latexend:)

and solving for ($\frac{dy}{dx}$) gives

(:latex:) \[ \frac{dy}{dx} = \frac{1}{e^y} = \frac{1}{e^{\ln x}} = \frac{1}{x}, \] (:latexend:)

as desired.

Note that ($\ln x$) is the inverse of ($e^x$), and so when we exponentiated the equation, it could be thought of as applying the inverse of ($\ln x$). This same method works for many other inverse functions. In particular, applying a trigonometric function can be thought of as an operator as well. This method can be used to find the derivatives of the various inverse trigonometric functions.

Example

Find the derivative of ($\arcsin(x)$). (:toggle hide show="Answer" box2c:)

Letting ($y = \arcsin x$), take the sine of the equation to find

(:latex:) \[ \sin y = x. \] (:latexend:)

Now, differentiating gives

(:latex:) \[ \cos y \, dy = dx. \] (:latexend:)

Thus, we find that

(:latex:) \[ \frac{dy}{dx} = \frac{1}{\cos y}. \] (:latexend:)

Now, a little bit of trigonometry helps rewrite ($\sec y$) in terms of ($x$). Our original equation had ($y = \arcsin x$). That means that ($y$) is the angle such that ($\sin y = x$). Since sine is the opposite over the hypotenuse, we can express this relationship with the following right triangle:

where the adjacent leg comes from the Pythagorean theorem. It follows that ($\cos y = \sqrt{1-x^2}$), and so we find

(:latex:) \[ \frac{dy}{dx} = \frac{1}{\cos y} = \frac{1}{\sqrt{1-x^2}}. \] (:latexend:)

Example

Find the derivative of ($\arctan(x)$). (:toggle hide show="Answer" box3:)

Let ($y = \arctan(x)$). Applying ($\tan$) to the equation gives

(:latex:) \[ \tan y = x, \] (:latexend:)

and differentiating gives

(:latex:) \[ \sec^2y\,dy = dx. \] (:latexend:)

Therefore,

(:latex:) \begin{align*} \frac{dy}{dx} &= \frac{1}{\sec^2y} \end{align*} (:latexend:)

We can now do similar right triangle trig as in the previous example. Or we can recall that by the Pythagorean identity for tangent and secant, we have

(:latex:) \[ \tan^2y + 1 = \sec^2y \] (:latexend:)

Making this substitution gives

(:latex:) \begin{align*} \frac{dy}{dx} &= \frac{1}{\sec^2y}
&= \frac{1}{\tan^2y + 1}
&= \frac{1}{x^2+1}. \end{align*} (:latexend:)
Operators in other contexts

Besides being useful in computing derivatives of exotic functions, operators (especially the logarithm) can also be useful in computing limits. The method is similar to the above method for derivatives.

Example

Show that

(:latex:) \[ \lim_{x \rightarrow \infty} \left(1+\frac{a}{x}\right)^x = e^a. \] (:latexend:)

This is a common limit which will come up again in the course. (:toggle hide show="Answer" box4:)

Let ($y$) be the function given by

(:latex:) \[ y = \left(1+\frac{a}{x}\right)^x. \] (:latexend:)

Take the logarithm of both sides, and use the power property of logarithms to see

(:latex:) \begin{align*} \ln y &= \ln \left(1+\frac{a}{x}\right)^x
&= x \ln \left(1+\frac{a}{x}\right). \end{align*} (:latexend:)

Now, taking the limit of both sides gives

(:latex:) \begin{align*} \lim_{x \rightarrow \infty} \ln y &= \lim_{x \rightarrow \infty} x \ln \left(1+\frac{a}{x}\right). \end{align*} (:latexend:)

Now, since ($x \rightarrow \infty$), we have that ($\frac{a}{x}$) is small, and so we can use our Taylor series for ($\ln(1+x)$), which gives us that

(:latex:) \begin{align*} \lim_{x \rightarrow \infty} \ln y &= \lim_{x \rightarrow \infty} x \ln\left(1+\frac{a}{x}\right)
&= \lim_{x \rightarrow \infty} x \left(\frac{a}{x} + O\left(\frac{1}{x^2}\right) \right)
&= \lim_{x \rightarrow \infty} a + O \left(\frac{1}{x}\right)
&= a. \end{align*} (:latexend:)

Recall from our limit rules that the order of the logarithm and the limit can be switched since the logarithm is a continuous function. Thus

(:latex:) \[ \ln \left(\lim_{x \rightarrow \infty} y \right) = a. \] (:latexend:)

So, exponentiating both sides, we have that

(:latex:) \[ \lim_{x\rightarrow \infty} y = e^a, \] (:latexend:)

as desired.
Infinite Power Tower

Consider the infinite power tower

(:latex:) \[ y = x^{x^{x^{x^{\dotsb}}}}. \] (:latexend:)

That is, ($x$) raised to the ($x$) raised to the ($x$) etc. This is certainly an unusual function. A better way to define this function is implicitly:

(:latex:) \[ y = x^y. \] (:latexend:)

To see that this makes intuitive sense, note that the exponent of the first ($x$) in the infinite tower is itself an infinite tower, so replacing the exponent of ($x$) with ($y$) is sensible.

Use logarithmic differentiation to find the derivative of this function (that is, ($\frac{dy}{dx}$)).

(:toggle hide show="Answer" box5:)

First, taking the logarithm gives

(:latex:) \[ \ln y = y \ln x. \] (:latexend:)

Now, differentiating the equation (implicitly) gives

(:latex:) \[ \frac{dy}{y} = \ln x \, dy + y \frac{dx}{x} \] (:latexend:)

Factoring and solving for ($\frac{dy}{dx}$) gives

(:latex:) \begin{align*} \left(\frac{1}{y} - \ln x\right)dy &= y \frac{dx}{x}
\frac{dy}{dx} &= \frac{y}{x \left(1/y-\ln x\right)}
&= \frac{y^2}{x (1- y \ln x)}. \end{align*} (:latexend:)

This shows that although a function may be difficult to understand, it can nevertheless be fairly easy to find its derivative.

It turns out that this function is well-defined and differentiable on

(:latex:) \[ e^{-e} < x < e^{1/e} \] (:latexend:)

One can check that the ($(x,y)$) pairs ($(e^{-e},e^{-1}),(1,1),(\sqrt{2},2),(e^{1/e},e)$) all satisfy the above implicit equation.
EXERCISES

    Find the derivative of ($f(x) = (\ln x)^x$)
    Find the derivative of ($f(x) = x^{\ln x}$)
    Compute ($ \displaystyle \lim_{x \to +\infty} \left( \frac{x+2}{x+3} \right)^{2x} $)
    Compute ($ \displaystyle \lim_{x \to 0^+} \left[ \ln(1+x) \right]^{x} $)
    Compute ($ \displaystyle \lim_{x \to 0} \left(1 + \arctan\frac{x}{2} \right)^{2/x} $)
    Compute ($ \displaystyle \lim_{x \to 0^+} \left(\frac{2}{x}\right)^{\sin x} $)
    Let 

(:latex:) \[ \alpha =1 + \frac{2}{2+ \frac{2}{2+ \frac{2}{2+\cdots}}} \] (:latexend:)
What is the value of ($\alpha$)?

    Let 

(:latex:) \[ \varphi = \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+\cdots}}}}}\] (:latexend:)
What is the value of ($\varphi$)? 