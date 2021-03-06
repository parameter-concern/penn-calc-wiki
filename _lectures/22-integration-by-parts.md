---
title: Integration by parts
description: Using the product rule as an integration technique
lecture_number: 22
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
This module uses the product rule to derive another useful integration technique: integration by parts. Recall the product rule:

$$
\begin{equation*} d(u \cdot v) = u \cdot dv + v \cdot du. \end{equation*}
$$

Integrating both sides gives

$$
\begin{align*}
\int d(u \cdot v) = \int u \, dv + \int v \, du.
\end{align*}
$$

Solving for $$\int u \, dv$$ gives

Integration by parts

If $$u = u(x)$$ and $$v = v(x)$$ are two functions of $$x$$, then

$$
\begin{equation*} \int u \, dv = uv - \int v \, du. \end{equation*}
$$

Intuitively, we are given a difficult integral $$\int u \, dv$$. By breaking the integrand into $$u$$ and $$dv$$ and applying the above formula, we are hopefully able to wind up with an easier integral $$\int v \, du$$. Like with the substitution technique, it requires a little bit of thought to choose suitable $$u$$ and $$dv$$. Once $$u$$ and $$dv$$ are picked, it is a fairly mechanical process to apply the formula (assuming a good choice of $$u$$ and $$dv$$).

Note that the selection is constrained by the fact that $$u \, dv$$ must be the entire integrand. So whatever choice is made for $$u$$, whatever factors are left over become $$dv$$. Note also that the formula involves finding $$v$$, and so $$dv$$ must be integrable. Ideally, $$dv$$ should be easy to integrate, which can help guide the selection.

**Example**

Compute

$$
\int xe^x dx.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Letting $$u = x$$ and $$dv = e^xdx$$ (we see that these factors together make up our integrand), one finds by differentiating $$u$$ and integrating $$dv$$ that $$du = dx$$ and $$v = e^x$$. Many students find it helps to organize this information in a grid:

$$
\begin{align*}
u &= x & du &= dx
dv &= e^x \, dx & v &= e^x.
\end{align*}
$$

Then, from the formula it follows that

$$
\begin{align*}
\int xe^xdx &= xe^x - \int e^xdx
&= xe^x - e^x +C
&= (x-1)e^x + C.
\end{align*}
$$

One can check that the derivative of this gives back the original integrand, as desired.

**Example**

Compute

$$
\int \ln(x) dx.
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The selection of $$u$$ and $$dv$$ that works is

$$
\begin{align*}
u &= \ln(x) & du &= \frac{1}{x}\,dx
dv &= dx & v &= x.
\end{align*}
$$

Note that the only other possibility would be $$dv = \ln(x)dx$$. But this choice would mean that to find $$v$$ we would need to find the integral of $$\ln(x)$$, which is the problem at hand.

Applying the formula, we find

$$
\begin{align*}
\int \ln(x) dx &= x \ln(x) - \int x \cdot \frac{1}{x} \, dx
&= x\ln(x) - \int dx
&= x\ln(x) - x +C
&= x(\ln(x)-1) + C.
\end{align*}
$$

Again, we can check that the derivative of this function gives back $$\ln x$$, our original integrand.

**Example**

Try to compute

$$
\int \frac{\sin x}{x} \, dx
$$

Hint: it cannot be done using integration by parts.

<button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


One choice we might try is

$$
\begin{align*}
u &= \sin x & du &= \cos x \,dx
dv &= \frac{1}{x} \, dx & v &= \ln x.
\end{align*}
$$

However, this requires us to compute the integral

$$
\int v \, du = \int \ln x \cos x \, dx,
$$

which is no better than the original integral. Another possible choice is

$$
\begin{align*}
u &= \frac{1}{x} & du &= -\frac{1}{x^2}\,dx
dv &= \sin x \, dx & v &= -\cos x.
\end{align*}
$$

This leads to the integral

$$
\int v \, du = \int \frac{\cos x}{x^2} \, dx,
$$

which is again no better than the original integral.

It turns out no selection will work. Some integrals cannot be computed using integration by parts. And some integrals (like this one) have no elementary answer (i.e. some combination of trigonometric functions, polynomials, exponentials, etc.).

That said, we could expand $$\sin(x)$$ as a Taylor series, divide by $$x$$ and integrate term by term, which gives a series solution. This gives a perfectly suitable solution provided that $$x$$ is not too far from 0.
LIPET: A tip for choosing $$u$$ and $$dv$$

It is not always obvious how to choose $$u$$ and $$dv$$. The mnemonic LIPET gives a suggestion for how to select $$u$$, and then whatever is left over becomes $$dv$$.

- Logarithm
- Inverse function
- Polynomial
- Exponential
- Trigonometric. 

When picking $$u$$, go down the list until some factor of the integrand first matches something from the list. So in the first example above, there was no logarithm, no inverse function, but there was a polynomial, $$x$$, which was chosen for $$u$$. In the second example, there was a logarithm, so that became $$u$$.

This will not always work perfectly, because (as the above example showed) some integrals simply cannot be computed using integration by parts. But in most examples where integration by parts works, the above mnemonic will help give the correct selection of $$u$$ and $$dv$$.

**Example**

Compute

$$
\int \frac{\ln x}{x^2} \, dx.
$$

<button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


A good choice is

$$
\begin{align*}
u &= \ln x & du &= \frac{1}{x}\, dx
dv &= \frac{1}{x^2} \, dx & v &= - \frac{1}{x}.
\end{align*}
$$

Then

$$
\begin{align*}
\int \frac{\ln x}{x^2} \, dx &= -\frac{1}{x} \ln x - \int -\frac{1}{x^2} \, dx
&= -\frac{1}{x} \ln x - \frac{1}{x} + C.
\end{align*}
$$

Repeated use

Sometimes integration by parts requires repeated use, if the integral $$\int v \,du$$ is not easy to compute. It is not always easy to tell when repeating integration by parts will help, but with practice it becomes easier.

**Example**

Compute

$$
\int e^x \cos(x)dx.
$$

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


We can take

$$
\begin{align*}
u &= e^x & du &= e^x \, dx
dv &= \cos x \, dx & v &= \sin x.
\end{align*}
$$

(it turns out that this would work equally well if we reversed these). Then the formula says that

$$
\begin{align*}
\int e^x \cos(x)dx &= e^x \sin(x) - \int \sin(x) e^xdx.
\end{align*}
$$

This does not seem much better than the original problem. However, with some persistence and algebra, this will work. Let $$I = \int e^x \cos(x)dx$$ be the original integral, and let $$J = \int \sin(x) e^x dx$$ be the new integral. So the above calculation shows

$$
\begin{equation*} I = e^x \sin(x) - J \end{equation*}
$$

Using integration by parts on $$J$$, we pick

$$
\begin{align*}
u &= e^x & du &= e^x \, dx
dv &= \sin x \, dx & v &= -\cos x.
\end{align*}
$$

Then it follows that

$$
\begin{align*}
J &= \int \sin(x) e^x dx
&= e^x (- \cos(x)) - \int (-\cos(x)) e^x dx
&= -e^x \cos(x) + \int e^x \cos(x) dx
&= -e^x \cos(x) + I.
\end{align*}
$$

So the problem has come back to the original integral $$I$$. This might seem like cause for despair, but putting together the previous calculations shows

$$
\begin{align*}
I &= e^x \sin(x) - J
&= e^x \sin(x) - (-e^x \cos(x) + I)
&= e^x \sin(x) + e^x \cos(x) - I.
\end{align*}
$$

Now, solving for $$I$$ gives

$$
\begin{align*}
2I &= e^x \sin(x) + e^x \cos x +C
I &= \frac{1}{2}(e^x \sin(x) + e^x \cos(x)) + C.
\end{align*}
$$

**Example**

Compute

$$
\int e^{2x} \sin(3x) \, dx.
$$

<button class="toggle" data-box="#box3a">Answer</button>

<div id="box3a" class="answer-hidden"></div>
{: id="box3a" class="answer-hidden"}


The algebra is similar to the above example, but care must be taken with the constants. Let

$$
I = \int e^{2x} \sin(3x) \, dx.
$$

Let

$$
\begin{align*}
u &= e^{2x} & du &= 2e^{2x} \, dx
dv &= \sin(3x) \, dx & v &= -\frac{1}{3}\cos(3x).
\end{align*}
$$

Then

$$
\begin{align*}
I &= -\frac{1}{3}e^{2x}\cos(3x) - \int \left(-\frac{1}{3}\cos(3x)\right) 2e^{2x} \, dx
&= -\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{3} \int e^{2x}\cos(3x) \, dx.
\end{align*}
$$

Now, let

$$
J = \int e^{2x} \cos(3x) \, dx.
$$

Selecting

$$
\begin{align*}
u &= e^{2x} & du &= 2e^{2x} \, dx
dv &= \cos(3x) \, dx & v &= \frac{1}{3}\sin(3x),
\end{align*}
$$

we have

$$
\begin{align*}
J &= \frac{1}{3}e^{2x}\sin(3x) - \frac{2}{3} \int e^{2x}\sin(3x) \, dx
&= \frac{1}{3}e^{2x}\sin(3x) - \frac{2}{3}I.
\end{align*}
$$

Putting this all together, we have

$$
\begin{align*}
I &= -\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{3}J
&= -\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{3} \left( \frac{1}{3}e^{2x}\sin(3x) - \frac{2}{3}I \right)
&= -\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{9} e^{2x}\sin(3x) - \frac{4}{9} I.
\end{align*}
$$

Solving for $$I$$ gives

$$
\begin{align*}
\frac{13}{9}I &= -\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{9} e^{2x}\sin(3x)
I &= \frac{9}{13} \left(-\frac{1}{3}e^{2x}\cos(3x) + \frac{2}{9}e^{2x}\sin(3x) \right)
&= \frac{1}{13}e^{2x} \left(-3 \cos(3x) + 2 \sin(3x) \right).
\end{align*}
$$

Remember that any indefinite integral has an integration constant, so the final answer is

$$
\int e^{2x} \sin(3x) \, dx = \frac{1}{13}e^{2x} \left(-3 \cos(3x) + 2 \sin(3x) \right) + C.
$$

There are integrals that require several applications of integration by parts before they are finished. Unfortunately, it is not always clear when it will work and when it will not. Doing a lot of practice can help develop the intuition to tell the difference.

As the next example shows, sometimes an integral that looks like a perfect candidate for integration by parts does not yield to this method.

**Example**

Compute

$$
\int e^x \cosh x \, dx.
$$

<button class="toggle" data-box="#box3a1">Answer</button>

<div id="box3a1" class="answer-hidden"></div>
{: id="box3a1" class="answer-hidden"}


This looks so similar to the above examples, that it is reasonable to expect that two applications of integration by parts will allow us to algebraically find this integral. Unfortunately, there is a problem that will soon present itself. Let

$$
I = \int e^x \cosh x \, dx.
$$

If we set

$$
\begin{align*}
u &= e^x & du &= e^x \, dx
dv &= \cosh x \, dx & v &= \sinh x,
\end{align*}
$$

we find

$$
\begin{align*}
I &= e^x \sinh x - \int e^x \sinh x
&= e^x \sinh x - J,
\end{align*}
$$

where we have set

$$
J = \int e^x \sinh x \, dx.
$$

Letting

$$
\begin{align*}
u & = e^x & du &= e^x \, dx
dv &= \sinh x \, dx & v &= \cosh x,
\end{align*}
$$

we find

$$
\begin{align*}
J &= e^x \cosh x - \int e^x \cosh x \, dx
&= e^x \cosh x - I.
\end{align*}
$$

Putting it all together,

$$
\begin{align*}
I &= e^x \sinh x - J
&= e^x \sinh x - (e^x \cosh x - I)
&= e^x \sinh x - e^x \cosh x + I.
\end{align*}
$$

Here is where our problem arises. We cannot solve for $$I$$ because there is a positive $$I$$ on both sides. This problem is due to the fact that (unlike sine and cosine), the hyperbolic sine and cosine do not introduce negative signs when integrated or differentiated, respectively.

So what do we do? Rewrite our integral using the definition of $$\cosh x$$ and it becomes easy:

$$
\begin{align*}
\int e^x \cosh x \, dx &= \int e^x \cdot \left( \frac{e^x + e^{-x}}{2} \right)
&= \frac{1}{2} \int \left(e^{2x}+1\right) \, dx
&= \frac{1}{2} \left(\frac{1}{2}e^{2x} + x \right) + C
&= \frac{1}{4}e^{2x} + \frac{1}{2}x + C.
\end{align*}
$$

Reduction formulae

A final application of integration by parts is to prove what are known as reduction formulae. These formulae express one integral in terms of another slightly simpler integral. One can use a reduction formula to repeatedly simplify an integral, eventually reaching a known integral. These formulae are invariably derived by using integration by parts and some algebra.

**Example**

For a fixed integer $$n \geq 0$$, show that

$$
\int x^n \cos x \, dx = x^n \sin x + nx^{n-1}\cos x - n(n-1) \int x^{n-2} \cos x \, dx.
$$

Use this formula to find

$$
\int x^2 \cos x dx.
$$

<button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


Let

$$
\begin{align*}
u &= x^n & du &= nx^{n-1} \, dx
dv &= \cos x \, dx & v &= \sin x.
\end{align*}
$$

Then according to the formula,

$$
\int x^n \cos x \, dx = x^n \sin x - \int n x^{n-1}\sin x \, dx.
$$

Now, since we want to get our integral in terms of an integral involving $$\cos x$$ and a power of $$x$$, we can apply integration by parts to

$$
\int x^n \sin x \, dx.
$$

Here, we let

$$
\begin{align*}
u &= x^n & du &= nx^{n-1} \, dx
dv &= \sin x \, dx & v &= -\cos x.
\end{align*}
$$

This gives

$$
\int x^n \sin x \, dx = -x^n \cos x + \int n x^{n-1}\cos x \, dx.
$$

Now, using this in our earlier equation (though with $$n$$ replaced by $$n-1$$), we find

$$
\begin{align*}
\int x^n \cos x \, dx &= x^n \sin x - \int nx^{n-1}\sin x \, dx
&= x^n \sin x - n \int x^{n-1}\sin x \, dx
&= x^n \sin x - n \left(-x^{n-1}\cos x + \int (n-1)x^{n-2} \cos x \, dx \right)
&= x^n \sin x + n x^{n-1}\cos x - n(n-1)\int x^{n-2}\cos x \, dx.
\end{align*}
$$

The formula says that

$$
\begin{align*}
\int x^2 \cos x \, dx &= x^2 \sin x + 2x \cos x - 2 \int \cos x \, dx
&= x^2 \sin x + 2x \cos x -2 \sin x+ C
&= x^2 \sin x + 2x \cos x - 2 \sin x + C.
\end{align*}
$$

**Example**

Similar algebra as in the above example shows that for $$n \geq 0$$

$$
\int x^n \sin x \, dx = -x^n \cos x + n x^{n-1} \sin x - n(n-1) \int x^{n-2} \sin x \, dx.
$$

**Example**

Find a reduction formula for

$$
\int x^n e^x \, dx.
$$

Use it to evaluate

$$
\int x^2 e^x \, dx.
$$

<button class="toggle" data-box="#box3c">Answer</button>

<div id="box3c" class="answer-hidden"></div>
{: id="box3c" class="answer-hidden"}


Letting

$$
\begin{align*}
u &= x^n & du &= nx^{n-1} \, dx
dv &= e^x \, dx & v &= e^x,
\end{align*}
$$

we find that

$$
\int x^n e^x = x^n e^x - n \int x^{n-1} e^x \, dx.
$$

Applying this when $$n=2$$ (then applying it again) gives

$$
\begin{align*}
\int x^2 e^x &= x^2 e^x - 2 \int x e^x \, dx
&= x^2 e^x - 2 \left(xe^x - \int e^x \, dx\right)
&= x^2 e^x - 2xe^x + 2e^x + C.
\end{align*}
$$

**Example**

Show that for $$n \geq 2$$,

$$
\int \sec^n(x) \, dx = \frac{1}{n-1} \sec^{n-2}(x) \tan(x) + \frac{n-2}{n-1} \int \sec^{n-2}(x) \, dx.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


In integrating a power of a trigonometric function, it can be hard to pick how many factors become $$u$$ and how many become $$dv$$. The fact that $$dv$$ is supposed to be easy to integrate can guide this selection. Since $$\int \sec^2 x dx = \tan x$$, letting $$dv = \sec^2x dx$$ should work well.

Thus, $$u = \sec^{n-2} (x)$$ and $$dv = \sec^2xdx$$, which means $$du = (n-2) \sec^{n-3}(x) \sec(x) \tan(x)dx$$ (by the chain rule), and $$v = \tan x$$. Recalling the Pythagorean identity $$\tan^2x = \sec^2x-1$$, one finds that

$$
\begin{align*}
\int \sec^n(x) dx &= \sec^{n-2}(x)\tan(x) - \int (n-2)\sec^{n-2}(x) \tan^2(x)dx
&= \sec^{n-2}(x) \tan(x) - (n-2) \int \sec^{n-2}(x)(\sec^2(x)-1)dx
&= \sec^{n-2}(x) \tan(x) - (n-2) \int (\sec^{n}(x) - \sec^{n-2}(x)) dx
&= \sec^{n-2}(x) \tan(x) - (n-2)\int \sec^{n}(x)dx + (n-2) \int \sec^{n-2}(x)dx
\end{align*}
$$

Now, solving for $$\int \sec^n(x)dx$$ gives

$$
\begin{equation*} \int \sec^n(x) dx = \frac{1}{n-1} \sec^{n-2}(x) \tan(x) + \frac{n-2}{n-1} \int \sec^{n-2}(x) dx, \end{equation*}
$$

as desired.
Additional examples

**Example**

Compute

$$
\int x \sin(x) \, dx.
$$

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


The logical choice (either by the LIPET mnemonic, or by picking $$u$$ to be something which gets simpler when differentiated) for parts is

$$
\begin{align*}
u &= x & du &= dx
dv &= \sin(x) \, dx & v &= -\cos(x)
\end{align*}
$$

Therefore,

$$
\begin{align*}
\int x \sin(x) \, dx &= -x \cos(x) - \int -\cos(x) \, dx
&=-x \cos(x) + \int \cos(x) \, dx
&= -x \cos(x) + \sin(x) + C.
\end{align*}
$$

**Example**

Compute

$$
\int \arctan x \, dx.
$$

Hint: recall that $$
\frac{d}{dx} \arctan x = \frac{1}{1+x^2}.
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


As in some earlier examples, the only choice we have is to set

$$
\begin{align*}
u &= \arctan x & du &= \frac{1}{1+x^2} \, dx
dv &= dx & v &= x.
\end{align*}
$$

Therefore,

$$
\begin{align*}
\int \arctan x \, dx &= x \arctan x - \int \frac{x}{1+x^2} \, dx.
\end{align*}
$$

This second integral can be solved with a substitution of

$$
\begin{align*}
u &= 1+x^2
du &= 2x \, dx.
\end{align*}
$$

So $$dx = \frac{du}{2x}$$. Making the substitution gives

$$
\begin{align*}
\int \frac{x}{1+x^2} \, dx &= \int \frac{x}{u} \cdot \frac{du}{2x}
&= \frac{1}{2} \int \frac{du}{u}
&= \frac{1}{2} \ln u + C
&= \frac{1}{2} \ln (1+x^2) + C.
\end{align*}
$$

Putting it all together, we find

$$
\begin{align*}
\int \arctan x \, dx &= x \arctan x - \int \frac{x}{1+x^2} \, dx
&= x \arctan x - \frac{1}{2} \ln(1+x^2) + C.
\end{align*}
$$


## Exercises

Compute the following integrals:

- $$ \displaystyle \int x e^{x/2} \, dx $$
- $$ \displaystyle \int x^2e^{x/2} \, dx $$
- $$ \displaystyle \int 3x \ln x \, dx $$
- $$ \displaystyle \int 3x^2 \ln x \, dx $$
- $$ \displaystyle \int x^2 \cos\frac{x}{2} \, dx $$
- $$ \displaystyle \int e^{2x}\sin 3x \, dx $$
- $$ \displaystyle \int \ln x \, dx $$
- $$ \displaystyle \int \ln^2 x \, dx $$
- $$ \displaystyle \int \sin(\ln x) \, dx $$
- $$ \displaystyle \int \arcsin(2x) \, dx $$ 

To solve the integral $$ \displaystyle \int e^x\cos x\, dx $$ , we used the method of integration by parts twice. Based on how we solved the integral of $$ e^x\cosh x $$, we can try the same with the cosine version, using the fact that $$ \displaystyle \cos x = \frac{1}{2}(e^{ix}+e^{-ix}) $$ . Try! The integration is the easy part...the hard part is getting the algebra to work out (hello again, Euler's formula...)

- Compute $$ \displaystyle \int \sin(2x) \cos(3x) \, dx $$ 