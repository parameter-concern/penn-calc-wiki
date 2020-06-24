---
title: Trigonometric integrals
description: Products and powers of trigonometric functions
lecture_number: 28
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
A trigonometric integral is an integral involving products and powers of trigonometric functions: cosine, sine, tangent, secant, cosecant, and cotangent. Many of these integrals can be handled with u-substitution, but there are other methods which are outlined in this module. The three families of integrals discussed in this module are

$$
\begin{align*}
& \int \sin^m \theta \cos^n \theta \, d\theta
& \int \tan^m \theta \sec^n \theta \, d\theta
& \int \sin (m \theta) \cos (n \theta) \, d \theta.
\end{align*}
$$

Product of sines and cosines

Consider the integral

$$
\int \sin^m \theta \cos^n \theta \, d\theta.
$$

There are several cases to consider based on whether $$m$$ and $$n$$ are odd and even.
m is odd

If $$m$$ is odd, then one factor of $$\sin \theta$$ can be set aside. This leaves behind an even power of $$\sin \theta$$, which can be expressed in terms of $$\cos \theta$$ using the Pythagorean identity. Then the substitution $$u = \cos \theta$$ can be made.

**Example**

Find $$
\int \sin^3(x) \cos(x) \,dx.
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Following the above outline, set aside one factor of $$\sin x$$, which gives

$$
\int \sin^3 x \cos x \, dx = \int (\sin^2 x) (\cos x) (\sin x) \, dx.
$$

Now, there is an even power of sine remaining, which can be rewritten using the Pythagorean identity

$$
\sin^2 x = 1 - \cos^2 x.
$$

This gives

$$
\begin{align*}
\int \sin^3 x \cos x\,dx &= \int (\sin^2 x) (\cos x) \sin(x) \, dx
&= \int (1-\cos^2 x)(\cos x) \sin(x)\,dx.
\end{align*}
$$

Now, the integral can be handled by letting $$u = \cos(x)$$ (and $$du = -\sin(x)dx$$).

$$
\begin{align*}
\int (1-\cos^2 x)(\cos x)(\sin x) \, dx &= \int (1-u^2)u(-du) 
&= \int (u^3-u)\,du 
&= \frac{u^4}{4} - \frac{u^2}{2} + C 
&= \frac{\cos^4 x}{4} - \frac{\cos^2 x}{2} + C.
\end{align*}
$$

n is odd

If $$n$$ is odd, the procedure is very similar. This time, we set aside a factor of $$\cos \theta$$. This leaves an even power of $$\cos \theta$$ which can be expressed in terms of $$\sin \theta$$ using the Pythagorean identities.

**Example**

Find

$$
\int \sin^2(x) \cos^3(x) \, dx.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Following the procedure outlined above, we set aside a factor of cosine and use the Pythagorean identity, which gives

$$
\begin{align*}
\int \sin^2(x) \cos^3(x) \, dx &= \int \sin^2(x) \cos^2(x) \cos(x) \, dx
&= \int \sin^2(x) (1-\sin^2 x) \cos(x) \, dx.
\end{align*}
$$

Now, we are ready to make the substitution $$u = \sin(x)$$, $$du = \cos(x) \, dx$$. This gives

$$
\begin{align*}
\int \sin^2(x) (1-\sin^2 x) \cos(x) \, dx &= \int u^2 (1-u^2) \, du
&= \int u^2 - u^4 \, du
&= \frac{u^3}{3} - \frac{u^5}{5} + C
&= \frac{\sin^3 x}{3} - \frac{\sin^5 x}{5} + C.
\end{align*}
$$

Both m and n are even

If neither $$m$$ nor $$n$$ is odd, then both are even. This is a bit more difficult and requires using the power reduction formulas:
Power reduction
$$\sin^2(\theta) = \frac{1-\cos(2 \theta)}{2}$$
$$\cos^2(\theta) = \frac{1+\cos(2\theta)}{2}$$

**Example**

Find

$$
\int \sin^2x\, dx.
$$

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Using the first power reduction formula gives

$$
\begin{align*}
\int \sin^2x\, dx &= \int \frac{1}{2}(1-\cos(2x))\,dx
&= \frac{1}{2}\left(x - \frac{\sin(2x)}{2}\right) + C.
\end{align*}
$$

**Example**

Find

$$
\int \sin^2 \theta \cos^2 \theta \, d\theta.
$$

<button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


Using both the power reduction formulas and doing some algebra gives

$$
\begin{align*}
\int \sin^2 \theta \cos^2 \theta \, d \theta &= \int \frac{1}{2}\left(1-\cos 2\theta\right) \frac{1}{2}\left(1+\cos 2\theta\right) \, d \theta
&= \frac{1}{4} \int (1- \cos 2 \theta)(1+\cos 2 \theta) \, d \theta
&= \frac{1}{4} \int (1 - \cos^2 2 \theta) \, d\theta
&= \frac{1}{4} \int \sin^2 2 \theta \, d \theta
&= \frac{1}{4} \int \frac{1}{2}\left(1 - \cos 4 \theta \right)\, d \theta
&= \frac{1}{8} \left( \theta - \frac{\sin 4 \theta}{4} \right) + C.
\end{align*}
$$

**Example**

Find

$$
\int \cos^4(x)\,dx.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Using the second power reduction formula (and then again in a later step) gives

$$
\begin{align*}
\int \cos^4(x)\,dx &= \int (\cos^2(x))^2\,dx
&= \int (\frac{1}{2}(1+\cos(2x))^2\,dx
&= \frac{1}{4} \int \left(1 + 2 \cos(2x) + \cos^2(2x)\right)\,dx
&= \frac{1}{4} \int \left(1+ 2 \cos(2x) + \frac{1}{2}(1+\cos(4x)) \right)\,dx
&= \frac{1}{4} \left(x + \sin(2x) + \frac{1}{2}x + \frac{1}{8}\sin(4x) \right) + C
\end{align*}
$$

Product of tangents and secants

Next consider the integral

$$
\int \tan^m \theta \sec^n \theta \, d\theta.
$$

As with the product of sines and cosines, the method will depend on whether $$m$$ and $$n$$ are odd or even.
m is odd

If $$m$$ is odd, we will set aside a factor of $$\tan \theta \sec \theta$$. Note that this is the derivative of $$\sec \theta$$ and so this sets up a substitution of $$u = \sec \theta$$. After setting aside these factors, we are left with an even power of $$\tan \theta$$, which can be expressed in terms of $$\sec \theta$$ using the Pythagorean identity

$$
\tan^2 \theta = \sec^2 \theta - 1.
$$

Now, the integral can be computed using the substitution $$u = \sec \theta$$.

**Example**

Compute

$$
\int \tan^3 \theta \sec \theta \, d \theta.
$$

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Since the power of tangent is odd, we set aside a factor of $$\tan \theta \sec \theta$$, and use the Pythagorean identity to find

$$
\begin{align*}
\int \tan^3 \theta \sec \theta \, d \theta &= \int \tan^2 \theta (\tan \theta \sec \theta) \, d\theta
&= \int (\sec^2 \theta - 1) (\tan \theta \sec \theta) d\theta.
\end{align*}
$$

Now, we can make the substitution

$$
\begin{align*}
u &= \sec \theta
du &= \sec \theta \tan \theta \, d\theta,
\end{align*}
$$

which gives

$$
\begin{align*}
\int (\sec^2 \theta - 1) (\tan \theta \sec \theta) d\theta &= \int (u^2 - 1) \, du
&= \frac{1}{3}u^3 - u + C
&= \frac{1}{3}\sec^3 \theta - \sec \theta + C.
\end{align*}
$$

n is even

If $$n$$ is even, then we can set aside a factor of $$\sec^2\theta$$. Note that this is the derivative of $$\tan \theta$$ and therefore sets up the substitution $$u = \tan \theta$$. Setting aside $$\sec^2 \theta$$ leaves an even power of $$\sec \theta$$, which can be expressed in terms of $$\tan \theta$$ using the Pythagorean identity

$$
\sec^2 \theta = 1 + \tan^2 \theta.
$$

Then the substitution $$u = \tan \theta$$ allows the computation of the integral.

**Example**

Compute

$$
\int \tan^2 \theta \sec^6 \theta \, d \theta.
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


Because the power of secant is even, we set aside $$\sec^2 \theta$$ and use the Pythagorean identity to find

$$
\begin{align*}
\int \tan^2 \theta \sec^6 \theta \, d \theta &= \int \tan^2 \theta \sec^4 \theta (\sec^2 \theta) \, d\theta
&= \int \tan^2 \theta (1 + \tan^2 \theta)^2 (\sec^2 \theta) \, d\theta.
\end{align*}
$$

Now, we are prepared for a substitution of

$$
\begin{align*}
u &= \tan \theta
du &= \sec^2 \theta \, d \theta.
\end{align*}
$$

Making this substitution and simplifying gives

$$
\begin{align*}
\int \tan^2 \theta (1 + \tan^2 \theta)^2 (\sec^2 \theta) \, d\theta &= \int u^2 (1+u^2)^2 \, du
&= \int u^2 (1+2u^2 + u^4) \, du
&= \int (u^2 + 2u^4 + u^6) \, du
&= \frac{1}{3}u^3 + \frac{2}{5}u^5 + \frac{1}{7}u^7 + C
&= \frac{1}{3}\tan^3 \theta + \frac{2}{5}\tan^5 \theta + \frac{1}{7} \tan^7 \theta + C.
\end{align*}
$$

m is even, n is odd

If neither of the above cases holds, then the integral is a bit more difficult. It typically requires a bit of algebra and several applications of a reduction formula (or integration by parts). A general method is to rewrite the even power of tangent entirely in terms of secant by using the Pythagorean identity

$$
\tan^2 \theta = \sec^2 \theta - 1.
$$

This gives an integral which is sums of powers of $$\sec \theta$$. Each of these can be solved using the reduction formula for secant:

$$
\int \sec^n \theta \, d\theta = \frac{1}{n-1} \sec^{n-2} \theta \tan \theta + \frac{n-2}{n-1} \int \sec^{n-2} \theta \, d \theta,
$$

along with the fact that

$$
\int \sec \theta \, d\theta = \ln \vert\sec \theta + \tan \theta\vert + C.
$$

**Example**

Compute

$$
\int \tan^2 \theta \sec \theta \, d \theta.
$$

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


Using the Pythagorean identity gives

$$
\begin{align*}
\int \tan^2 \theta \sec \theta \, d \theta &= \int (\sec^2 \theta - 1) \sec \theta \, d \theta
&= \int (\sec^3 \theta - \sec \theta) \, d \theta
&= \int \sec^3 \theta \, d \theta - \int \sec \theta \, d \theta.
\end{align*}
$$

Now, using the reduction formula on the first of these integrals gives

$$
\begin{align*}
\int \sec^3 \theta \, d \theta &= \frac{1}{2}\sec \theta \tan \theta + \frac{1}{2} \int \sec \theta \, d \theta.
\end{align*}
$$

Combining this with the above expression and using the integral of secant, we find

$$
\begin{align*}
\int \tan^2 \theta \sec \theta \, d \theta &= \int \sec^3 \theta \, d \theta - \int \sec \theta \, d \theta
&= \left(\frac{1}{2}\sec \theta \tan \theta + \frac{1}{2} \int \sec \theta \, d \theta \right) - \int \sec \theta \, d \theta
&= \frac{1}{2} \sec \theta \tan \theta -\frac{1}{2} \int \sec \theta \, d \theta
&= \frac{1}{2} \sec \theta \tan \theta - \frac{1}{2} \ln\vert\sec \theta + \tan \theta\vert + C.
\end{align*}
$$

Product of sine and cosine with constants

Finally, consider the integral

$$
\int \sin(m \theta) \cos(n \theta) \, d\theta.
$$

This integral requires some algebra to simplify the integrand. One can verify using the sum and difference formulas for sine that

$$
\sin(m \theta)\cos(n \theta) = \frac{1}{2} \left(\sin((m+n)\theta) + \sin((m-n)\theta)\right).
$$

This expression can be integrated term by term to find

$$
\begin{align*}
\int \sin (m \theta) \cos (n \theta) \, d \theta &= \int \frac{1}{2}\left(\sin((m+n)\theta) + \sin((m-n)\theta)\right) \, d \theta
&= \frac{1}{2} \left(-\frac{\cos((m+n)\theta)}{m+n} - \frac{\cos((m-n)\theta)}{m-n} \right) + C.
\end{align*}
$$

There are similar formulas for related integrals:

$$
\begin{align*}
\int \sin (m \theta) \sin (n \theta) \, d \theta &= -\frac{\sin((m+n)\theta)}{2\left(m+n \right)} + \frac{\sin((m-n)\theta)}{2\left(m-n\right)} + C
\int \cos(m \theta) \cos(n \theta) \, d \theta &= \frac{\sin((m+n)\theta)}{2\left(m+n\right)} + \frac{\sin((m-n)\theta)}{2 \left(m-n\right)} + C.
\end{align*}
$$

These formulas need not be memorized, but be aware they exist and look them up when necessary.

**Example**

Compute

$$
\int \sin(3\theta) \cos(4 \theta) \, d \theta.
$$

<button class="toggle" data-box="#box8">Answer</button>

<div id="box8" class="answer-hidden"></div>
{: id="box8" class="answer-hidden"}


Using the formula given, we have

$$
\begin{align*}
\int \sin(3 \theta) \cos(4 \theta) \, d \theta &= - \frac{\cos(7 \theta)}{14} - \frac{\cos(-\theta)}{-2} + C
&= -\frac{\cos(7 \theta)}{14} + \frac{\cos \theta}{2} + C,
\end{align*}
$$

where we have used the fact that cosine is even to simplify the final expression.
Additional examples

**Example**

Compute

$$
\int_{\theta = -\pi/2}^{\pi/2} \cos^n \theta \, d \theta.
$$

Use the fact (which is proven using integration by parts) that

$$
\int \cos^n \theta \, d\theta = \frac{\cos^{n-1}\theta \sin \theta}{n} + \frac{n-1}{n} \int \cos^{n-2} \theta \, d \theta.
$$

<button class="toggle" data-box="#box9">Answer</button>

<div id="box9" class="answer-hidden"></div>
{: id="box9" class="answer-hidden"}


Applying the limits of integration in the above reduction formula gives

$$
\int_{\theta = -\pi/2}^{\pi/2} \cos^n \theta \, d\theta = \frac{\cos^{n-1}\theta \sin \theta}{n} \bigg\vert_{-\pi/2}^{\pi/2} + \frac{n-1}{n} \int_{\theta = -\pi/2}^{\pi/2} \cos^{n-2} \theta \, d \theta.
$$

Now, notice that

$$
\frac{\cos^{n-1}\theta \sin \theta}{n} \bigg\vert_{-\pi/2}^{\pi/2} = 0
$$

because cosine is 0 at $$\pm \pi/2$$. Therefore,

$$
\int_{\theta = -\pi/2}^{\pi/2} \cos^n \theta \, d\theta = \frac{n-1}{n} \int_{\theta = -\pi/2}^{\pi/2} \cos^{n-2} \theta \, d \theta.
$$

This is itself a reduction formula. By computing the base cases $$n=0$$ and $$n=1$$, respectively, we find

$$
\begin{align*}
\int_{\theta = -\pi/2}^{\pi/2} d\theta &= \theta \bigg\vert_{-\pi/2}^{\pi/2}
&= \pi,
\end{align*}
$$

and

$$
\begin{align*}
\int_{\theta = -\pi/2}^{\pi/2} \cos \theta \, d\theta &= \sin \theta \bigg\vert_{-\pi/2}^{\pi/2}
&= 2.
\end{align*}
$$

Now the value of the integral for any higher value of $$n$$ can be found by repeatedly using the above formula until the integral reduces to one of the base cases above. Using induction, one finds

$$
\begin{equation*} \int_{\theta = -\pi/2}^{\pi/2} \cos^n \theta \, d \theta = \begin{cases} \frac{1 \cdot 3 \cdot 5 \dotsb (n-1)}{2 \cdot 4 \cdot 6 \dotsb n} \pi & \hbox{if $n$ is even}
\frac{2 \cdot 4 \cdot 6 \dotsb (n-1)}{3 \cdot 5 \cdot 7 \dotsb n} \cdot 2 & \hbox{if $n$ is odd.} \end{cases} \end{equation*}
$$

**Example**

Compute

$$
\int \tan^3 \theta \, d\theta
$$

<button class="toggle" data-box="#box10">Answer</button>

<div id="box10" class="answer-hidden"></div>
{: id="box10" class="answer-hidden"}


Here the power of tangent is odd, so the method calls for setting aside a factor of $$\sec \theta \tan \theta$$. However, there is no factor of secant in this integral! It turns out that this is not a problem; we can multiply the top and the bottom by secant to introduce a factor of secant, and the algebra works out:

$$
\begin{align*}
\int \tan^3 \theta \, d\theta &= \int \frac{\tan^2 \theta}{\sec \theta} (\sec \theta \tan \theta) \, d \theta
&= \int \frac{\sec^2 \theta - 1}{\sec \theta} (\sec \theta \tan \theta) \, d \theta
&= \int \left(\sec \theta - \frac{1}{\sec \theta} \right) (\sec \theta \tan \theta) \, d \theta.
\end{align*}
$$

Now, proceed as usual with the substitution

$$
\begin{align*}
u &= \sec \theta
du &= \sec \theta \tan \theta \, d\theta.
\end{align*}
$$

Thus,

$$
\begin{align*}
\int \left(\sec \theta - \frac{1}{\sec \theta} \right) (\sec \theta \tan \theta) \, d \theta &= \int \left(u - \frac{1}{u}\right)\, du
&= \frac{1}{2}u^2 - \ln\vertu\vert + C
&= \frac{1}{2}\sec^2 \theta - \ln\vert\sec \theta\vert + C.
\end{align*}
$$


## Exercises

Compute the following indefinite integrals. You may need to use reduction formulae or coordinate changes.

- $$ \displaystyle \int \sin ^2 x \cos ^2 x \, dx $$
- $$ \displaystyle \int \sin ^3 \frac{x}{2} \cos ^3 \frac{x}{2} \, dx $$
- $$ \displaystyle \int \frac{x^3\, dx}{\sqrt{9-x^2}} $$
- $$ \displaystyle \int 5\tan ^5 x \sec ^3 x \, dx $$
- $$ \displaystyle \int 7\tan ^4 x \sec ^4 x \, dx $$
- $$ \displaystyle \int 9\sin ^3 3x \, dx $$
- $$ \displaystyle \int \cos^4 x \, dx $$
- $$ \displaystyle \int \sin x \sec x \tan x \, dx $$
- $$ \displaystyle \int \tan^5 2x \, \sec ^4 2x \, dx $$
- $$ \displaystyle \int \cos x \sqrt{1 - \sin x} \, dx $$
- $$ \displaystyle \int \frac{x^2 \, dx}{\sqrt{1+x^2}} $$
- $$ \displaystyle \int \tan^4(2x) \, \sec^4(2x) \, dx $$ 