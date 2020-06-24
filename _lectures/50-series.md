---
title: Series
description: Infinite series as improper discrete integrals
lecture_number: 50
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
The previous module discussed finite sums as the discrete analog of definite integrals with finite bounds. Then, logically, the discrete analog of improper integrals with infinite bounds should be infinite sums, referred to as infinite series or just series when there is no confusion.
Definition of infinite series

Recall that when computing definite integrals with bounds at infinity, one replaces the infinite bound with a variable and then takes the limit:

$$
\int_{x=1}^\infty f(x)dx = \lim_{T \rightarrow \infty} \int_{x=1}^T f(x)dx.
$$

For infinite series, the definition is analogous:

$$
\sum_{n=1}^\infty a_n = \lim_{T \rightarrow \infty} \sum_{n=1}^T a_n.
$$

The expression $$\displaystyle \sum_{n=1}^T a_n$$ is called the $$T$$th partial sum of the series $$\displaystyle \sum_{n=1}^\infty a_n$$. Then a series converges if the sequence of partial sums converges. If the sequence of partial sums does not converge, we say the series diverges.

**Example**

Give the first few terms of the sequence of partial sums for the infinite series

$$
\sum_{n=1}^\infty \frac{1}{2^n}.
$$

<button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


Adding the first term, then the first two terms, then the first three terms, and so on, gives

$$
\frac{1}{2},\frac{1}{2}+\frac{1}{4},\frac{1}{2}+\frac{1}{4}+\frac{1}{8},\dotsb
$$

which becomes

$$
\frac{1}{2},\frac{3}{4},\frac{7}{8},\frac{15}{16},\dotsb.
$$

This sequence appears to be converging to 1, which is consistent with what we know this series to be (by the geometric series).
Taylor series revisited

Recall some of the Taylor series from earlier modules:

$$
\begin{align*}
e^x &= 1+ \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \ldots
\sin(x) &= x - \frac{x^3}{3!} + \frac{x^5}{5!} - \ldots
\cos(x) &= 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \ldots
\frac{1}{1-x} &= 1+ x+x^2+x^3+\ldots & (\vertx\vert<1)
\ln(1+x) &= x - \frac{x^2}{2}+\frac{x^3}{3} - \ldots & (\vertx\vert<1)
\end{align*}
$$

These provide many examples of series which not only converge, but can be evaluated exactly.

**Example**

Compute $$\frac{1}{3} + \frac{1}{9} + \frac{1}{27} + \frac{1}{81} + \ldots$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Note that by the geometric series,

$$
\begin{align*}
\frac{1}{1-1/3} &= 1 + \frac{1}{3} + \frac{1}{9} + \ldots
&= \frac{3}{2}.
\end{align*}
$$

So $$\frac{1}{3} + \frac{1}{9} + \ldots = \frac{1}{2}$$.

**Example**

Compute $$1 - \frac{\pi^2}{2!} + \frac{\pi^4}{4!} - \frac{\pi^6}{6!} + \ldots$$.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Note that this is the Taylor series for $$\cos(x)$$ with $$x= \pi$$. Thus, the series evaluates to $$\cos(\pi) = -1$$.
Classifying series

There are some series which cannot be evaluated exactly, though it is known that the series converges. For example, the series

$$
\begin{align*}
\sum_{n=1}^\infty \frac{1}{n^3} &= 1 + \frac{1}{8} + \frac{1}{27} + \frac{1}{64} + \ldots
& \approx 1.2
\end{align*}
$$

converges, but it is not known what the exact value is (though one can calculate as many digits as one likes). This is in contrast with an apparently similar series,

$$
\begin{align*}
\sum_{n=1}^\infty \frac{1}{n^2} &=1+ \frac{1}{4} + \frac{1}{9} + \frac{1}{16} + \ldots
&= \frac{\pi^2}{6},
\end{align*}
$$

for which an exact value is known (though the proof of this value is beyond the scope of this course).

Yet another similar series, called the harmonic series,

$$
\begin{equation*} \sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \ldots, \end{equation*}
$$

diverges, as will be shown in the next module.

There are two questions then. First, does a series converge or not? Second, if it does converge, to what does it converge? This course deals mostly with the first question, in this module and the next few modules. More advanced analysis classes can help answer the second question.
When intuition fails

Determining the convergence of a series using intuition can be dangerous. As one example of how intuition can fail, consider what happens when we plug $$x=1$$ into the series for $$\ln(1+x)$$:

$$
\ln 2 = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \frac{1}{6} + \dotsb.
$$

Although $$x=1$$ is not in the radius of convergence for this series, it turns out that this series still converges. Now, consider what happens if we multiply both sides by $$\frac{1}{2}$$:

$$
\frac{1}{2} \ln 2 = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \dotsb.
$$

Adding this equation together with the above one, some of the terms cancel and some combine to show that

$$
\frac{3}{2}\ln 2 = 1 + \frac{1}{3} - \frac{1}{2} + \frac{1}{5} + \frac{1}{7} - \frac{1}{4} + \frac{1}{9} + \frac{1}{11} - \frac{1}{6} + \dotsb
$$

Now, notice that this series has all the terms of the series for $$\ln 2$$, but in slightly different order. And yet, the series evaluates to a different value. That is certainly counter intuitive. Perhaps even more alarming, the terms of the series for $$\ln 2$$ can be rearranged so that the resulting series evaluates to any real number. The takeaway is that we must tread carefully and not trust intuition but instead rely on logic.
The nth term test for divergence

The first, and usually simplest, test for divergence of a series is the nth term test.

The nth term test for divergence

If $$\displaystyle \lim_{n \rightarrow \infty} a_n \neq 0$$, then the series $$\displaystyle \sum_{n=0}^\infty a_n$$ diverges.

<button class="toggle" data-box="#boxproof">Answer</button>

<div id="boxproof" class="answer-hidden"></div>
{: id="boxproof" class="answer-hidden"}


We give a proof by contrapositive. That is, we prove that if $$\displaystyle \sum_{n=0}^\infty a_n$$ converges, then $$\displaystyle \lim_{n \rightarrow \infty} a_n = 0$$.

Assume $$\displaystyle \sum_{n=0}^\infty a_n$$ converges. Then by the definition of convergence, we know that the sequence of partial sums $$s_T$$ defined by

$$
s_T = \sum_{n=1}^T a_n
$$

converges also. Therefore,

$$
\lim_{T \rightarrow \infty} s_T = \lim_{T \rightarrow \infty} s_{T-1} = L
$$

for some $$L$$. Then we have

$$
\lim_{T \rightarrow \infty} \left( s_T - s_{T-1} \right) = 0,
$$

by linearity of the limit. But notice that

$$
\begin{align*}
s_T - s_{T-1} &= \sum_{n=1}^T a_n - \sum_{n=1}^{T-1} a_n
&= \left(a_1 + a_2 + \dotsb +a_{T-1} + a_T \right) - \left(a_1 + a_2 + \dotsb + a_{T-1} \right)
&= a_T.
\end{align*}
$$

Putting this together with the above limit, we find

$$
\begin{align*}
\lim_{T \rightarrow \infty} \left( s_T - s_{T-1} \right) &= \lim_{T \rightarrow \infty} a_T
&= 0,
\end{align*}
$$

which is what we were trying to prove.

This test applies to all series, and it is easy to apply (just take the limit of the terms of the series). However, many of the series encountered in this course will have terms which go to 0 in the limit, in which case the test is inconclusive (see the caveat below).

**Example**

Show that the series

$$
\sum_{n=0}^\infty \frac{4^n - 3^n}{4^n + 2^n}
$$

diverges.

<button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


Here,

$$
a_n = \frac{4^n-3^n}{4^n + 2^n}.
$$

Applying the nth term test, we find

$$
\begin{align*}
\lim_{n \rightarrow \infty} a_n &= \lim_{n \rightarrow \infty} \frac{4^n-3^n}{4^n + 2^n}
&= \lim_{n \rightarrow \infty} \frac{4^n(1-(3/4)^n)}{4^n(1+(1/2)^n)}
&= \lim_{n \rightarrow \infty} \frac{1-(3/4)^n}{1+(1/2)^n}
&= 1 \neq 0,
\end{align*}
$$

because both $$\left(\frac{3}{4}\right)^n \rightarrow 0$$ and $$\left(\frac{1}{2}\right)^n \rightarrow 0$$. Therefore, by the nth term test, the series diverges.

**Example**

Show that the series

$$
\begin{equation*} \sum_{n=0}^\infty (-1)^n = 1-1+1-1+1-\ldots \end{equation*}
$$

diverges.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Since $$\lim_{n \rightarrow \infty} (-1)^n$$ does not exist (the sequence oscillates), the series diverges by the $$n$$th term test.

**Example**

Show that the series

$$
\begin{equation*} \sum_{n=1}^\infty \cos\left(\frac{1}{n}\right) = \cos(1) + \cos(1/2) + \cos(1/3) + \ldots \end{equation*}
$$

diverges.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Note that $$\lim_{n \rightarrow \infty} \cos\left(\frac{1}{n}\right) = \cos(0) = 1 \neq 0$$. Thus, by the nth term test, the series diverges.
Caveat

This is not a test for convergence! In particular, if $$\displaystyle \lim_{n \rightarrow \infty} a_n = 0$$, then the test is inconclusive (the series might converge or diverge). If the test is inconclusive, one of the other tests from the upcoming modules must be used.

In logical terms, this says that the converse of the nth term test does not hold. On the other hand, the contrapositive does hold:

$$
\sum_{n=0}^\infty a_n \hbox{ converges } \quad \Rightarrow \quad \lim_{n \rightarrow \infty} a_n = 0
$$

(The contrapositive of a true statement is always true, but the converse is not always true).

**Example**

What does the nth term test say about the series $$\sum_{n=2}^\infty \frac{\ln(n)}{n}$$?

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


Note that $$\lim_{n\rightarrow \infty} \frac{\ln(n)}{n} = 0$$, either by using l'Hospital's rule or by recalling that $$\ln(n)$$ grows much more slowly than $$n$$. Thus, the nth term test is inconclusive.

**Example**

What does the nth term test say about the series

$$
\sum_{n=1}^\infty \arctan n?
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


Note that

$$
\lim_{n \rightarrow \infty} \arctan n = \frac{\pi}{2} \neq 0,
$$

and so by the nth term test, the series diverges.

**Example**

Suppose the series

$$
\sum_{n=1}^\infty a_n = L,
$$

converges, and that $$a_n > 0$$ for all $$n$$. What, if anything, can be said about the convergence of the series

$$
\sum_{n=1}^\infty \frac{1}{a_n}?
$$

<button class="toggle" data-box="#box7">Answer</button>

<div id="box7" class="answer-hidden"></div>
{: id="box7" class="answer-hidden"}


By the contrapositive of the nth term test mentioned above, we know that since the series

$$
\sum_{n=1}^\infty a_n
$$

converges, we know that

$$
\lim_{n \rightarrow \infty} a_n = 0.
$$

But this implies that

$$
\lim_{n \rightarrow \infty} \frac{1}{a_n} = \infty
$$

so by the nth term test, we know that the series

$$
\sum_{n=1}^\infty \frac{1}{a_n}
$$

diverges.

## Exercises

- Determine whether the following series converges or diverges 

$$
\sum_{n=2}^{\infty} \frac{n^3}{n \ln(n^{100})}
$$

$$
\sum_{n=1}^{\infty} \frac{2^n}{n^{100}}
$$

