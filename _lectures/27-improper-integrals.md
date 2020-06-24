---
title: Improper integrals
description: Computing definite integrals when FTIC does not apply
lecture_number: 27
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
An improper integral is a definite integral which cannot be evaluated using the Fundamental Theorem of Integral Calculus (FTIC). This situation arises because the integral either

- has a point in its interval of integration which is not in the domain of the integrand (the function being integrated) or
- has $$\infty$$ or $$-\infty$$ as a bound of integration. 

As an example of the first type, consider

$$
\int_0^2 \frac{dx}{x}.
$$

This integral is improper because the left endpoint, 0, is not in the domain of $$\frac{1}{x}$$.

Another example of the first type is

$$
\int_0^4 \frac{dx}{\sqrt[3]{x-2}}.
$$

This is improper because the point 2 is in the interval of integration but is not in the domain of $$\frac{1}{\sqrt[3]{x-2}}$$.

For an example of the second type, consider

$$
\int_0^\infty \frac{dx}{1+x^2}.
$$

This is improper because the upper bound is $$\infty$$.

For an example of the danger of trying to apply the Fundamental Theorem of Integral Calculus when it does not apply, consider

$$
\int_{x=-1}^1 \frac{1}{x^2} \, dx.
$$

This is an improper integral (hence FTIC does not apply) because the point $$x=0$$ is not in the domain of $$\frac{1}{x^2}$$. If we were to try to apply FTIC anyway, we would find

$$
\begin{align*}
\int_{x=-1}^1 \frac{1}{x^2} \, dx &= -\frac{1}{x} \bigg\vert_{x=-1}^1
&= -1 - 1
&= -2.
\end{align*}
$$

This is problematic since $$\frac{1}{x^2} > 0$$ for all $$x$$ (hence should have a positive integral by the dominance property).
Dealing with improper integrals

To deal with an improper integral of the first type, first consider the integral $$\int_a^b f(x) \, dx$$, where $$a$$ is not in the domain of $$f(x)$$, but $$f$$ is continuous on the rest of the interval $$(a,b]$$. In this situation, one replaces the lower bound with a variable $$T$$ which is slightly larger than $$a$$, and then takes the limit as $$T$$ approaches $$a$$ from the right (this is denoted by $$T \rightarrow a^+$$).

$$
\begin{equation*} \int_a^b f(x) \, dx = \lim_{T \rightarrow a^+} \int_T^b f(x) \, dx. \end{equation*}
$$

This replacement allows the integral $$\int_T^b f(x) \, dx$$ to be computed using FTIC, since $$f$$ is continuous on that interval. After that integral is computed (in terms of $$T$$), the limit is computed. If the limit exists, then the original integral exists and equals the result. If the limit does not exist or is infinite, then the original integral does not exist either.

**Example**

Determine whether the integral

$$
\int_0^2 \frac{dx}{x}
$$

exists, and if it exists, what its value is.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Since the left endpoint is not in the domain of $$\frac{1}{x}$$, the integral becomes

$$
\begin{align*}
\int_0^2 \frac{dx}{x} &= \lim_{T \rightarrow 0^+} \int_T^2 \frac{dx}{x}
&= \lim_{T \rightarrow 0^+} \ln x \bigg\vert^2_T
&= \lim_{T \rightarrow 0^+} \left(\ln(2) - \ln(T)\right).
\end{align*}
$$

This limit does not exist because $$\lim_{T \rightarrow 0^+} \ln(T)$$ diverges. Hence, the original integral does not exist.

If the right endpoint, $$b$$, of the integral $$\int_a^b f(x)\, dx$$ is not in the domain of $$f$$, then $$b$$ gets replaced with a variable $$T$$ slightly smaller than $$b$$, and again the integral is replaced with a limit, this time as $$T \rightarrow b^-$$ (that is, the limit as $$T$$ approaches $$b$$ from the left).

$$
\begin{equation*} \int_a^b f(x)\, dx = \lim_{T \rightarrow b^-} \int_a^T f(x) \, dx. \end{equation*}
$$

Again, the integral equals this limit, if it exists. If the limit does not exist, then the integral does not exist.

**Example**

Determine whether the integral

$$
\int_1^3 \frac{dx}{(x-3)^2}
$$

exists. If it exists, find its value.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


The integral becomes

$$
\begin{align*}
\int_1^3 \frac{dx}{(x-3)^2} &= \lim_{T \rightarrow 3^-} \int_1^T \frac{dx}{(x-3)^2}
&= \lim_{T \rightarrow 3^-} -\frac{1}{x-3} \bigg\vert^T_1
&= \lim_{T \rightarrow 3^-} -\frac{1}{T-3} - (-\frac{1}{-2}).
\end{align*}
$$

This limit does not exist since $$\lim_{T \rightarrow 3^-} \frac{1}{T-3}$$ diverges. Hence, the integral does not exist.

For integrals where a point inside the interval of integration is not in the domain of the integrand, the integral is first split at the bad point, and then each integral is evaluated separately using the above techniques. So, consider $$\int_a^b f(x) \, dx$$ where the point $$c$$ is not in the domain of $$f$$ and $$a<c<b$$. Then

$$
\begin{align*}
\int_a^b f(x) \, dx &= \int_a^c f(x) \, dx + \int_c^b f(x) \, dx
&= \lim_{T \rightarrow c^-} \int_a^T f(x) \, dx + \lim_{U \rightarrow c^+} \int_U^b f(x) \, dx.
\end{align*}
$$

Both of the resulting limits must exist for the original integral to exist.

**Example**

Determine if the integral

$$
\int_{-1}^1 \frac{dx}{x^{4/5}}
$$

exists.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


The only point not in the domain of the function $$\frac{1}{x^{4/5}}$$ is 0. Thus, the integral becomes

$$
\begin{align*}
\int_1}^1 \frac{dx}{x^{4/5}} &= \int_{-1}^0 \frac{dx}{x^{4/5}}+\int_0^1 \frac{dx}{x^{4/5}}
&= \lim_{T \rightarrow 0^ \int_1}^T \frac{dx}{x^{4/5}} + \lim_{U \rightarrow 0^+} \int_u^1 \frac{dx}{x^{4/5}}
&= \lim_{T \rightarrow 0^ 5x^{1/5} \bigg\vert^T_1} + \lim_{U \rightarrow 0^+} 5x^{1/5} \bigg\vert^1_u
&= \lim_{T \rightarrow 0^ \left(5T^{1/5} - 5(-1)^{1/5} \right) + \lim_{U \rightarrow 0^+} \left(5 - 5u^{1/5}\right)
&= 0 +5 + 5-0
&= 10.
\end{align*}
$$

So the integral exists and equals 10.
Bounds at infinity

For integrals with one bound at infinity, the integral is defined as follows.

$$
\begin{equation*} \int_a^\infty f(x) \, dx = \lim_{T \rightarrow \infty} \int_a^T f(x) \, dx. \end{equation*}
$$

Similarly,

$$
\begin{equation*} \int_{-\infty}^a f(x) \, dx = \lim_{T \rightarrow -\infty} \int_T^a f(x) \, dx. \end{equation*}
$$

In the case of bounds of $$\infty$$ and $$-\infty$$, one can first split the integral at any real number $$c$$, and then compute each integral as above:

$$
\begin{align*}
\int_{-\infty}^\infty f(x) \, dx &= \int_{-\infty}^c f(x) \, dx + \int_c^\infty f(x) \, dx
&= \lim_{T \rightarrow -\infty} \int_T^c f(x) \, dx + \lim_{U \rightarrow \infty} \int_c^U f(x) \, dx.
\end{align*}
$$

As before, both of these limits must exist for the original integral to exist. It is not equivalent to computing a single limit such as

$$
\lim_{T \rightarrow \infty} \int_{-T}^T f(x) \, dx.
$$

**Example**

Determine if the integral

$$
\int_0^\infty \frac{dx}{1+x^2}
$$

exists. If it exists, find its value.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Because the top bound is $$\infty$$, the integral becomes

$$
\begin{align*}
\int_0^\infty \frac{dx}{1+x^2} &= \lim_{T \rightarrow \infty} \int_0^T \frac{dx}{1+x^2}
&= \lim_{T \rightarrow \infty} \arctan(x)\bigg\vert^T_0
&= \lim_{T \rightarrow \infty} \arctan(T) - \arctan(0)
&= \lim_{T \rightarrow \infty} \arctan(T)
&= \frac{\pi}{2}.
\end{align*}
$$

So the integral exists and equals $$\frac{\pi}{2}$$.
The p-integral

One class of improper integrals is common enough to get its own name: the p-integral. This is the name given to integrals of the form

$$
\int \frac{1}{x^p} \, dx = \int x^{-p} \, dx.
$$

There are two versions of this integral that are of interest to us. First, with a limit at infinity, and second with a limit at 0.

**Example**

Show that

$$
\begin{equation*} \int_{x=1}^\infty x^{-p} \, dx = \begin{cases} \frac{1}{p-1} & \hbox{if $p>1$}
\infty & \hbox{if $p \leq 1$.} \end{cases} \end{equation*}
$$

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


First, if $$p \neq 1$$, then we can use the power rule on $$x^{-p}$$. Here we find

$$
\begin{align*}
\int_{x=1}^\infty x^{-p} \, dx &= \lim_{T \rightarrow \infty} \frac{x^{-p+1}}{-p+1} \bigg\vert_{x=1}^T
&= \lim_{T \rightarrow \infty} \frac{T^{-p+1}}{1-p} - \frac{1}{1-p}.
\end{align*}
$$

Note that $$T^{-p+1}$$ diverges to infinity if $$p<1$$, since in this case we have a positive power of $$T$$, which goes to infinity as $$T$$ goes to infinity. On the other hand, $$T^{-p+1}$$ goes to 0 if $$p>1$$, since in that case it is a negative power of $$T$$. Putting this together with the above equations, we have

$$
\begin{equation*} \int_{x=1}^\infty x^{-p} \, dx = \begin{cases} \frac{1}{p-1} & \hbox{if $p>1$}
\infty & \hbox{if $p < 1$.} \end{cases} \end{equation*}
$$

Finally, consider the case $$p=1$$. In this case,

$$
\begin{align*}
\int_{x=1}^\infty \frac{1}{x} \, dx &= \lim_{T \rightarrow \infty} \ln x \bigg\vert_1^T
&= \lim_{T \rightarrow \infty} \ln T
&= \infty.
\end{align*}
$$

And so the cases are as claimed above.

**Example**

Consider the p-integral with a limit at 0:

$$
\int_{x=0}^1 x^{-p} \, dx.
$$

This integral is improper because 0 is not in the domain of $$x^{-p}$$. Show that

$$
\begin{equation*} \int_{x=0}^1 x^{-p} \, dx = \begin{cases} \infty & \hbox{if $p \geq 1$}
\frac{1}{1-p} & \hbox{if $p < 1$.} \end{cases} \end{equation*}
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


As in the previous example, we first consider when $$p \neq 1$$ and use the power rule:

$$
\begin{align*}
\int_{x=0}^1 x^{-p} \, dx &= \lim_{T \rightarrow 0^+} \frac{x^{1-p}}{1-p} \bigg\vert_{x=T}^1
&=\lim_{T \rightarrow 0^+} \frac{1}{1-p} - \frac{T^{1-p}}{1-p}.
\end{align*}
$$

Now, note that the limit is as $$T \rightarrow 0^+$$. So we have $$T^{1-p}$$ diverges if $$p>1$$ (since a negative power of $$T$$ diverges as $$T \rightarrow 0^+$$), and converges to 0 if $$p<1$$. Putting this together with the previous computation gives

$$
\begin{equation*} \int_{x=0}^1 x^{-p} \, dx = \begin{cases} \frac{1}{1-p} & \hbox{if $p<1$}
\infty & \hbox{if $p > 1$.} \end{cases} \end{equation*}
$$

Finally, if $$p=1$$, then

$$
\begin{align*}
\int_{x=0}^1 \frac{1}{x} \, dx &= \lim_{T \rightarrow 0^+} \ln x \bigg\vert_{x=T}^1
&= \lim_{T \rightarrow 0^+} 0 - \ln T
\end{align*}
$$

which diverges to infinity. Thus, the original integral diverges for all $$p \geq 1$$, as claimed.
Converge or diverge

In some contexts, it is enough to know whether an integral converges (has a finite answer) or diverges (goes to infinity or does not exist). Using the knowledge of the above p-integrals, and some asymptotic tools from earlier in the course, can help quickly determine whether certain improper integrals converge or diverge.

**Example**

Determine if

$$
\int_{x=0}^1 \frac{dx}{\sqrt{x^2+x}}
$$

converges or diverges.

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


This is not a function for which we can easily find an antiderivative. However, since we are interested in the behavior of the function near 0 (that is where the blow-up occurs), we can do a little bit of algebra to see that

$$
\begin{align*}
\frac{1}{\sqrt{x^2+x}} &= \frac{1}{\sqrt{x}} \cdot \frac{1}{\sqrt{x+1}}
&= \frac{1}{\sqrt{x}} \cdot (1+x)^{-1/2}
&= \frac{1}{\sqrt{x}} \left(1+ O(x)\right),
\end{align*}
$$

by the binomial expansion. Therefore, the leading order term of this function as $$x \rightarrow 0$$ is $$\frac{1}{\sqrt{x}}$$. This is a convergent p-integral, because $$p=\frac{1}{2}$$ and from the above example

$$
\int_{x=0}^1 \frac{dx}{x^p}
$$

converges when $$p<1$$.

**Example**

Determine if

$$
\int_{x=1}^\infty \frac{dx}{\sqrt{x^2+x}}
$$

converges or diverges.

<button class="toggle" data-box="#box8">Answer</button>

<div id="box8" class="answer-hidden"></div>
{: id="box8" class="answer-hidden"}


We must do a slightly different analysis for this integral, since we are interested in the behavior as $$x \rightarrow \infty$$. Because we want to take advantage of the binomial series again (which requires its argument to be less than 1), we do the following algebra:

$$
\begin{align*}
\frac{1}{\sqrt{x^2+x}} &= \frac{1}{\sqrt{x^2}} \cdot \frac{1}{\sqrt{1+x^{-1}}}
&= \frac{1}{x} \left(1+\frac{1}{x}\right)^{-1/2}
&= \frac{1}{x} \left(1+ O\left(\frac{1}{x}\right)\right).
\end{align*}
$$

So for this integral, the leading order term is $$\frac{1}{x}$$, which is the p-integral with $$p=1$$. This diverges, as the above example shows, and so the original integral diverges.

**Example**

Determine if

$$
\int_{x=-\infty}^\infty \frac{2x}{1+x^2} \, dx
$$

converges or diverges.

<button class="toggle" data-box="#box9">Answer</button>

<div id="box9" class="answer-hidden"></div>
{: id="box9" class="answer-hidden"}


As mentioned above, it is not valid to do this with a single limit such as

$$
\lim_{T \rightarrow \infty} \int_{x=-T}^T \frac{2x}{1+x^2} \, dx.
$$

The integral must be split and treated as two separate integrals with limits at infinity:

$$
\int_{x=-\infty}^\infty \frac{2x}{1+x^2} \, dx = \lim_{S \rightarrow -\infty} \int_{x=S}^0 \frac{2x}{1+x^2} \, dx + \lim_{T \rightarrow \infty} \int_{x=0}^T \frac{2x}{1+x^2} \, dx.
$$

Again, a little bit of asymptotic analysis with the help of the geometric series helps determine the behavior of this function:

$$
\begin{align*}
\frac{2x}{1+x^2} &= \frac{2x}{1+x^2} \cdot \frac{x^{-2}}{x^{-2}} \\ &= \frac{2}{x} \cdot \frac{1}{1+x^{-2}}
&= \frac{2}{x} \left(1+ O(x^{-2})\right).
\end{align*}
$$

Here, the geometric series was used to write

$$
\frac{1}{1+x^{-2}} = 1 - x^{-2} + x^{-4} - \dotsb = 1+ O(x^{-2}),
$$

which is justified since $$x \rightarrow \infty$$ and so $$x^{-2}$$ is very small. So the original integrand behaves like $$\frac{2}{x}$$, which diverges when integrated to infinity. Therefore

$$
\lim_{T \rightarrow \infty} \int_{x=0}^T \frac{2x}{1+x^2} \, dx
$$

diverges, and (but for a sign change) the same reasoning shows

$$
\lim_{S \rightarrow -\infty} \int_{x=S}^0 \frac{2x}{1+x^2} \, dx
$$

diverges too, so the original integral diverges.

## Exercises

- Use a Talyor expansion of the integrand at $$x=0$$ to determine whether the following integrals converge or diverge: 

$$ \displaystyle \int_{x=0}^1 \frac{e^{-x}}{x} \, dx $$
$$ \displaystyle \int_{x=0}^1 \frac{\cos^2 x}{\sqrt{x}} \, dx $$

- Use the asymptotics of the integrand as $$x\to\infty$$ to determine whether the following integrals converge or diverge: 

$$ \displaystyle \int_{x=1}^{+\infty} \frac{\sqrt[3]{x + 3}}{x^3} \, dx $$
$$ \displaystyle \int_{x=1}^{+\infty} \frac{1-5^{-x}}{x} \, dx $$

- Compute the following integrals, if they converge, by evaluating a limit. 

$$ \displaystyle \int_{x=0}^{+\infty} e^{-x} \sin x \, dx $$
$$ \displaystyle \int_{x=1}^2 \frac{dx}{\sqrt{x - 1}} $$
$$ \displaystyle \int_{x=0}^4 \frac{2 \, dx}{\sqrt{16 - x^2}} $$

- The following integral is improper both at $$x=1$$ and at $$x\to\infty$$: 

$$ \displaystyle \int_{x=1}^{+\infty} \frac{1}{\sqrt{x^3 -1} } \, dx $$
First, as $$x\to\infty$$, show that the integrand is $$x^{-3/2} + O(x^{-9/2}) $$, so that it converges at this limit.
Next, as $$x\to 1^+$$, show that the integrand is $$(3(x-1)^{-1/2} + O((x-1)^{1/2}) $$, so that it converges at this limit also.

- Consider the following two integrals: 

$$ \displaystyle I_1 = \int_{x=2}^{+\infty} \frac{dx}{\sqrt{x^3 - 8}}, \qquad I_2 = \int_{x=2}^{+\infty} \frac{1}{\sqrt{(x-2)^3}} \, dx $$
One converges and one does not. Which is which and why?

- Until now we have used asymptotic analysis to relate an improper integral to a $$p$$-integral. But sometimes the leading order term is not a power. Identify the leading order term as $$x \to +\infty$$ of the integrand of 

$$ \displaystyle \int_{x=1}^{+\infty} \frac{1}{\sinh x} \, dx $$
and determine whether the integral converges or diverges.

- For $$p \geq 0$$ an integer, consider the following integral: 

$$ \displaystyle I_p = \int_{x=1}^{+\infty} \frac{dx}{\ln^p x} $$
Show that this diverges for any value of $$p$$.
Hint 1: think about the growth of $$\ln^p x$$ as $$x \to +\infty$$ as compared to polynomial growth.
Hint 2: recall from Lecture 25 that if $$g(x) \geq f(x)$$ for every $$x \in [a,b]$$, then
$$ \displaystyle \int_{x=a}^b g(x) \,dx \geq \int_{x=a}^b f(x) \,dx $$
This is also true if the domain of integration is unbounded and the integrals are defined...

- Determine whether the following integral converges or diverges. 

$$ \displaystyle \int_2^{\infty} \frac{1}{(x^5-4x^3)^{1/4}} \, dx $$ 