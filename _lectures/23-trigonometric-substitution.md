---
title: Trigonometric substitution
description: Integration using trigonometric substitutions
lecture_number: 23
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
There is another class of integrals which usually do not involve trigonometric functions, but which can be solved by substituting the variable with a trigonometric function. This can be thought of as using the substitution formula, from Integration By Substitution, in the other direction. That is, going from the left side to right side in the equality

$$
\int f(x) \, dx = \int f(x(\theta)) \frac{dx}{d\theta} \, d\theta,
$$

where we have made the substitution $$x = x(\theta)$$. We often use $$\theta$$ when making a trigonometric substitution.

**Example**

Compute

$$
\int \frac{dx}{1+x^2}.
$$

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Consider the substitution $$x = \tan(\theta)$$. Then one finds that $$dx = \sec^2\theta\, d\theta$$. Making these substitutions and recalling the Pythagorean identity $$1+\tan^2\theta = \sec^2\theta$$, the integral becomes

$$
\begin{align*}
\int \frac{dx}{1+x^2} &= \int \frac{\sec^2\theta\, d\theta}{1+\tan^2\theta}
&= \int \frac{\sec^2\theta\, d\theta}{\sec^2\theta}
&= \int d\theta
&= \theta + C
&= \arctan(x) + C.
\end{align*}
$$

The last line comes from our original substitution:

$$
x = \tan \theta \quad \Leftrightarrow \quad \arctan x = \theta.
$$

Typical substitutions

Trigonometric substitution makes use of the Pythagorean identities. In general, the basic trigonometric substitutions are:
Form	Substitution	Identity used
$$1+x^2$$	$$x = \tan \theta$$	$$1+\tan^2 \theta = \sec^2 \theta$$
$$1-x^2$$	$$x = \sin \theta$$	$$1-\sin^2\theta = \cos^2\theta$$
$$x^2-1$$	$$x = \sec \theta$$	$$\sec^2\theta - 1 = \tan^2 \theta$$
Caveat

The form $$x^2-1$$ often leads to a messy integral involving $$\sec(\theta)$$. This can often be avoided using a hyperbolic trigonometric substitution (see below).

After a substitution has been made, the resulting integral will often involve a product of trigonometric functions, possibly raised to powers. These types of integrals are covered in more detail in Trigonometric Integrals. For now, here are a few of the useful identities in evaluating these integrals:
Power reduction
$$\sin^2(\theta) = \frac{1-\cos(2 \theta)}{2}$$
$$\cos^2(\theta) = \frac{1+\cos(2\theta)}{2}$$
Double angle
$$\sin(2\theta) = 2 \sin \theta \cos \theta$$
$$\cos(2\theta) = \cos^2\theta - \sin^2\theta$$

**Example**

Compute

$$
\int \sqrt{1-x^2} \, dx.
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


According to the above guide, the substitution to make is $$x = \sin \theta$$. Then $$dx = \cos \theta \, d\theta$$, and it follows that

$$
\begin{align*}
\int \sqrt{1-x^2} \, dx &= \int \sqrt{1-\sin^2\theta} \cos \theta \, d\theta
&= \int \sqrt{\cos^2 \theta} \cos \theta \, d\theta
&= \int \cos^2 \theta \, d\theta.
\end{align*}
$$

Now using the power reduction identity for cosine, we have

$$
\begin{align*}
\int \cos^2 \theta \, d\theta &= \int \frac{1}{2}(1+\cos(2 \theta)) \, d\theta
&= \frac{\theta}{2} + \frac{1}{4}\sin(2 \theta) + C.
\end{align*}
$$

Finally, we must get this back in terms of $$x$$. We know that $$\theta = \arcsin x$$. But to take care of $$\sin 2\theta$$, we must use the double angle formula from above. This gives

$$
\begin{align*}
\sin 2 \theta &= 2 \sin \theta \cos \theta
&= 2 x \sqrt{1-x^2}
\end{align*}
$$

In the last line above, we knew $$\sin \theta = x$$ from the original substitution. We found $$\cos \theta$$ by drawing a right triangle which relates $$x$$ and $$\theta$$ according to the substitution $$\sin \theta = x$$:

Putting this all together and doing a little simplification, we find

$$
\int \sqrt{1-x^2} = \frac{1}{2}\arcsin x + \frac{1}{2} x \sqrt{1-x^2} + C.
$$

**Example**

Compute

$$
\int \frac{dx}{\sqrt{1-x^2}}.
$$

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


By the above table, the substitution $$x = \sin \theta$$ should be used (hence $$\theta = \arcsin(x)$$). Then $$dx = \cos \theta \, d\theta$$, so the integral becomes

$$
\begin{align*}
\int \frac{dx}{\sqrt{1-x^2}} &= \int \frac{\cos \theta\, d\theta}{\sqrt{1-\sin^2\theta}}
&= \int \frac{\cos \theta\, d\theta}{\sqrt{\cos^2\theta}}
&= \int d \theta
&= \theta + C
&= \arcsin(x)+C.
\end{align*}
$$

Forms with other constants

There are other forms which are similar to the above forms but have different constants involved. These are dealt with using similar substitutions which make the constants cancel and factor so that the same identities can be used.

**Example**

Compute

$$
\int \frac{dx}{x^2\sqrt{x^2+4}}
$$

<button class="toggle" data-box="#box3a">Answer</button>

<div id="box3a" class="answer-hidden"></div>
{: id="box3a" class="answer-hidden"}


The form $$x^2+4$$ in the denominator reminds us of the substitution we made earlier for $$x^2+1$$, which was the substitution $$x = \tan \theta$$. This is the correct impulse, but unfortunately it does not work quite right here since there is no nice simplification for $$\tan^2 \theta + 4$$.

We can fix this by adjusting the coefficients. The idea is that we could factor out a 4 if we had

$$
4 \tan^2 \theta + 4 = 4(\tan^2 \theta + 1).
$$

To get that extra factor of 4, we can make the substitution $$x = 2 \tan \theta$$. Then $$dx = 2 \sec^2 \theta \, d\theta$$, and the integral becomes

$$
\begin{align*}
\int \frac{dx}{x^2 \sqrt{x^2+4}} &= \int \frac{2 \sec^2 \theta \, d \theta}{4 \tan^2 \theta \sqrt{4 \tan^2 \theta + 4}}
&=\int \frac{2 \sec^2 \theta \, d \theta}{4 \tan^2 \theta \sqrt{4(\tan^2 \theta + 1)}}
&= \frac{1}{4} \int \frac{\sec^2 \theta \, d \theta}{\tan^2 \theta \sec \theta}.
\end{align*}
$$

The last equality above comes from again using the identity $$\tan^2 \theta + 1 = \sec^2 \theta$$. Doing a little simplification and rewriting in terms of sine and cosine gives

$$
\begin{align*}
\frac{1}{4} \int \frac{\sec \theta \, d \theta}{\tan^2 \theta} &= \frac{1}{4} \int \frac{1}{\cos \theta} \cdot \frac{\cos^2 \theta}{\sin^2 \theta} \, d\theta
&= \frac{1}{4} \int \frac{\cos \theta \, d \theta}{\sin^2 \theta}.
\end{align*}
$$

This we can handle with a substitution of $$u = \sin \theta$$ and $$du = \cos \theta \, d \theta$$, which gives

$$
\begin{align*}
\frac{1}{4} \int \frac{\cos \theta \, d \theta}{\sin^2 \theta} &= \frac{1}{4} \int \frac{du}{u^2}
&= \frac{1}{4}\left(-\frac{1}{u}\right) + C
&= -\frac{1}{4u} + C
&= -\frac{1}{4 \sin \theta} + C
\end{align*}
$$

Now, we must do one final bit of right triangle trigonometry to get $$\sin \theta$$ in terms of $$x$$. By the original substitution we have $$\tan \theta = \frac{x}{2}$$, and this can be expressed by the following triangle:

It follows that $$\sin \theta = \frac{x}{\sqrt{x^2+4}}$$. Putting it all together, we have

$$
\begin{align*}
\int \frac{dx}{x^2 \sqrt{x^2+4}} &= -\frac{1}{4 \sin \theta} + C
&= -\frac{\sqrt{x^2+4}}{4x} + C.
\end{align*}
$$

**Example**

Compute

$$
\int \frac{dx}{4+9x^2}.
$$

<button class="toggle" data-box="#box3b">Answer</button>

<div id="box3b" class="answer-hidden"></div>
{: id="box3b" class="answer-hidden"}


This is another example which looks like $$x = \tan \theta$$ is the right type of substitution to make. However, again we need to adjust the coefficient since $$4+9\tan^2\theta$$ does not simplify nicely.

The key is to get the constants to cancel and factor. The substitution $$x = \frac{2}{3}\tan\theta$$ will work, and in this case $$\theta = \arctan(\frac{3}{2}x)$$. Then $$dx = \frac{2}{3}\sec^2\theta d\theta$$, and the integral becomes

$$
\begin{align*}
\int \frac{dx}{4+9x^2} &= \frac{2}{3} \int \frac{\sec^2\theta\, d\theta}{4+9(4/9)\tan^2\theta}
&= \frac{2}{3} \int \frac{\sec^2\theta\, d\theta}{4(1+\tan^2\theta)}
&= \frac{2}{3} \int \frac{\sec^2\theta\, d\theta}{4 \sec^2\theta}
&= \frac{2}{3} \cdot \frac{1}{4} \int d\theta
&= \frac{1}{6} \theta + C
&= \frac{1}{6} \arctan(\frac{3}{2}x) + C.
\end{align*}
$$

The following table summarizes the substitutions to be made when other constants are involved. The identities used are the same Pythagorean identities given in the above table.
Form	Substitution
$$a^2x^2+b^2$$	$$x = \frac{b}{a}\tan \theta$$
$$b^2-a^2x^2$$	$$x = \frac{b}{a}\sin \theta$$
$$a^2x^2-b^2$$	$$x = \frac{b}{a}\sec \theta$$
Completing the square

Sometimes it is not obvious at first that an integral is of the form where a trigonometric substitution is helpful. It may take a little bit of algebra to see what the right substitution is. This common algebraic tool is known as completing the square, which simply rewrites a quadratic expression as the square of a binomial plus a constant. To review the algebra involved in this process, check Wikipedia:Completing the square.

**Example**

Compute

$$
\int \frac{dx}{\sqrt{3+2x-x^2}}
$$

<button class="toggle" data-box="#box3c">Answer</button>

<div id="box3c" class="answer-hidden"></div>
{: id="box3c" class="answer-hidden"}


Start by completing the square for the quadratic:

$$
\begin{align*}
3+2x-x^2 &= -x^2+2x+3
&= -(x^2-2x) + 3
&= -(x^2-2x+1) + 4
&= -(x-1)^2 + 4
&= 4-(x-1)^2.
\end{align*}
$$

So we can rewrite the integral as

$$
\begin{align*}
\int \frac{dx}{\sqrt{3+2x-x^2}} &= \int \frac{dx}{\sqrt{4-(x-1)^2}}

&= \int \frac{du}{\sqrt{4-u^2}},
\end{align*}
$$

where we substituted $$u = x-1$$ and $$du = dx$$. This can now be dealt with using a trigonometric substitution of $$u = 2 \sin \theta$$ (remember, the extra factor of 2 is there so that the 4 will factor out). So $$du = 2 \cos \theta \, d \theta$$, and the integral becomes

$$
\begin{align*}
\int \frac{du}{\sqrt{4-u^2}} &= \int \frac{2 \cos \theta \, d \theta}{\sqrt{4-4\sin^2 \theta}}
&= \int \frac{2 \cos \theta \, d \theta}{\sqrt{4}\sqrt{1-\sin^2 \theta}}
&= \int \frac{2 \cos \theta \, d \theta}{2 \cos \theta}
&= \int d \theta
&= \theta + C.
\end{align*}
$$

Solving our original substitution for $$\theta$$, we see that

$$
\begin{align*}
\theta &= \arcsin\left(\frac{u}{2}\right)
&= \arcsin\left(\frac{x-1}{2}\right).
\end{align*}
$$

So the final answer is

$$
\int \frac{dx}{\sqrt{3+2x-x^2}} = \arcsin \left(\frac{x-1}{2}\right) + C.
$$

Hyperbolic trigonometric substitutions

Recall that the hyperbolic trigonometric functions $$\sinh(x)$$ and $$\cosh(x)$$ are defined by

$$
\begin{align*}
\sinh(\theta) &= \frac{e^\theta - e^{-\theta}}{2}
\cosh(\theta) &= \frac{e^\theta+e^{-\theta}}{2}.
\end{align*}
$$

These functions satisfy the Pythagorean identity $$ \cosh^2(\theta) - \sinh^2(\theta) = 1$$. Also, note that $$ \frac{d}{d\theta} \cosh(\theta) = \sinh(\theta) $$, and $$\frac{d}{d\theta} \sinh(\theta) = \cosh(\theta)$$. This means hyperbolic substitutions are another option for dealing with the following forms:
Form	Substitution	Identity used
$$1+x^2$$	$$x = \sinh \theta$$	$$1+\sinh^2 \theta = \cosh^2 \theta$$
$$x^2-1$$	$$x = \cosh \theta$$	$$\cosh^2\theta - 1 = \sinh^2\theta$$

This often gives a simpler answer than the $$x = \sec \theta$$ substitution suggested above, but the trade-off is that the answer will involve hyperbolic functions. Here are some of the other identities for the hyperbolic functions, which are similar to those for regular trigonometric functions:
Double Angle
$$\sinh(2 \theta) = 2\sinh(\theta)\cosh(\theta)$$
$$\cosh(2\theta) = \cosh^2(\theta) + \sinh^2(\theta)$$
$$\cosh(2\theta) = 2\cosh^2(\theta) - 1$$
$$\cosh(2\theta) = 2\sinh^2(\theta) + 1$$
Power reduction
$$\sinh^2(\theta) = \frac{\cosh(2\theta)-1}{2}$$
$$\cosh^2(\theta) = \frac{\cosh(2\theta)+1}{2}$$

**Example**

Compute

$$
\int \frac{dx}{\sqrt{1+x^2}}.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Using a regular trigonometric substitution, we would set $$x = \tan \theta$$, and $$dx = \sec^2 \theta \, d\theta$$, which, after the usual algebra, gives

$$
\begin{align*}
\int \frac{dx}{\sqrt{1+x^2}} &= \int \frac{ \sec^2 \theta \, d \theta}{\sqrt{1+\tan^2 \theta}}
&= \int \sec \theta \, d\theta.
\end{align*}
$$

But the integral of secant is not easy to remember, nor easy to rederive. If instead, we make the hyperbolic trigonometric substitution $$ x = \sinh u$$, so $$ dx = \cosh u \, du$$, then we have

$$
\begin{align*}
\int \frac{dx}{\sqrt{1+x^2}} &= \int \frac{\cosh u \, du}{\sqrt{1+\sinh^2 u}}
&= \int \frac{\cosh u \, du}{\cosh u}
&= \int du
&= u + C
&= \arcsinh x + C.
\end{align*}
$$

So the hyperbolic trigonometric substitution led to a much easier integral to evaluate. The trade-off is that the final result involves the inverse hyperbolic trigonometric functions, as opposed to more familiar functions.

**Example**

Compute

$$
\int \sqrt{1+x^2}\,dx.
$$

<button class="toggle" data-box="#box4a">Answer</button>

<div id="box4a" class="answer-hidden"></div>
{: id="box4a" class="answer-hidden"}


Using the hyperbolic trigonometric substitution $$x = \sinh(\theta)$$ gives

$$
\begin{align*}
\int \sqrt{1+x^2}\,dx &= \int \sqrt{1+\sinh^2\theta} \cosh \theta\, d\theta
&= \int \sqrt{\cosh^2\theta} \cosh \theta\, d\theta
&= \int \cosh^2 \theta\, d\theta
&= \frac{1}{2} \int (\cosh(2\theta)+1)\,d\theta
&= \frac{1}{2}\left(\theta + \frac{1}{2}\sinh(2\theta)\right) +C
&= \frac{1}{2} \theta + \frac{1}{4} 2\sinh(\theta)\cosh(\theta) +C
&= \frac{1}{2} \sinh^{-1} x + \frac{1}{2} x \sqrt{1+x^2} + C.
\end{align*}
$$

Blow-ups

Sometimes a differential equation can be solved by using a trigonometric substitution. But this can sometimes lead to an unreasonable solution due to blow-ups or singularities, which exist for many trigonometric functions.

**Example**

Consider a financial model which predicts that marginal profits equal some positive constant plus something which is proportional to the square of net profits. Mathematically,

$$
\frac{dP}{dt} = b^2 + a^2P^2,
$$

for constants $$a$$ and $$b$$ (we square them to ensure that they are positive). Solve this differential equation and find where it has a blow-up. <button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


This is a separable equation. Separating the variables and integrating both sides gives

$$
\int \frac{dP}{b^2 + a^2P^2} = \int dt.
$$

On the left, we can use the trigonometric substitution

$$
\begin{align*}
P &= \frac{b}{a} \tan \theta
dP &= \frac{b}{a} \sec^2 \theta \, d \theta.
\end{align*}
$$

Note then that $$\theta = \arctan \frac{a}{b}P$$. This gives

$$
\begin{align*}
\int \frac{dP}{b^2+a^2P^2} &= \int \frac{\frac{b}{a}\sec^2 \theta \, d \theta}{b^2(1+\tan^2 \theta)}
&= \frac{b}{a} \int \frac{\sec^2 \theta \, d \theta}{b^2 \sec^2 \theta}
&= \frac{1}{ab} \int d \theta
&= \frac{1}{ab} \theta
&= \frac{1}{ab} \arctan \frac{a}{b}P.
\end{align*}
$$

(leaving off the constant for now). On the right side we get $$t + C$$, so

$$
\frac{1}{ab} \arctan \frac{a}{b}P = t + C.
$$

Solving this for $$P$$ gives

$$
P(t) = \frac{b}{a} \tan(abt + C).
$$

If initial profits, at $$t=0$$, are 0, then $$C=0$$, so the final answer is

$$
P(t) = \frac{b}{a} \tan(abt).
$$

Since tangent blows up at $$\frac{\pi}{2}$$, this model implies profit goes to infinity at $$t = \frac{\pi}{2ab}$$, which is a sign that this model is not perfect.

## Exercises

Compute the following integrals:

- $$ \displaystyle \int \frac{x^2}{\sqrt{4-x^2}} \, dx $$
- $$ \displaystyle \int \frac{dx}{\sqrt{x^2-2x}} $$
- $$ \displaystyle \int \frac {\sqrt{1-x^2}} {x^2} \, dx $$
- $$ \displaystyle \int (1-x^2)^{-3/2} \, dx $$
- $$ \displaystyle \int \frac{x}{\sqrt{1+x^2}} \, dx $$
- $$ \displaystyle \int \frac{dx}{x\sqrt{x^2-1}} $$
- $$ \displaystyle \int \frac{dx}{\sqrt{x^2-6x+10}} $$
- $$ \displaystyle \int \frac{dx}{\sqrt{x^2-2x-8}} $$ 