---
title: Series
description: Infinite series as improper discrete integrals
lecture_number: 50
topic_number: 5
layout: lecture
mathjax: true
---
The previous module discussed finite sums as the discrete analog of definite integrals with finite bounds. Then, logically, the discrete analog of improper integrals with infinite bounds should be infinite sums, referred to as infinite series or just series when there is no confusion.
Definition of infinite series

Recall that when computing definite integrals with bounds at infinity, one replaces the infinite bound with a variable and then takes the limit:

(:latex:) \[ \int_{x=1}^\infty f(x)dx = \lim_{T \rightarrow \infty} \int_{x=1}^T f(x)dx. \] (:latexend:)

For infinite series, the definition is analogous:

(:latex:) \[ \sum_{n=1}^\infty a_n = \lim_{T \rightarrow \infty} \sum_{n=1}^T a_n. \] (:latexend:)

The expression ($\displaystyle \sum_{n=1}^T a_n$) is called the ($T$)th partial sum of the series ($\displaystyle \sum_{n=1}^\infty a_n$). Then a series converges if the sequence of partial sums converges. If the sequence of partial sums does not converge, we say the series diverges.

Example

Give the first few terms of the sequence of partial sums for the infinite series

(:latex:) \[ \sum_{n=1}^\infty \frac{1}{2^n}. \] (:latexend:)

(:toggle hide show="Answer" box0:)

Adding the first term, then the first two terms, then the first three terms, and so on, gives

(:latex:) \[ \frac{1}{2},\frac{1}{2}+\frac{1}{4},\frac{1}{2}+\frac{1}{4}+\frac{1}{8},\dotsb \] (:latexend:)

which becomes

(:latex:) \[ \frac{1}{2},\frac{3}{4},\frac{7}{8},\frac{15}{16},\dotsb. \] (:latexend:)

This sequence appears to be converging to 1, which is consistent with what we know this series to be (by the geometric series).
Taylor series revisited

Recall some of the Taylor series from earlier modules:

(:latex:) \begin{align*} e^x &= 1+ \frac{x}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \ldots
\sin(x) &= x - \frac{x^3}{3!} + \frac{x^5}{5!} - \ldots
\cos(x) &= 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \ldots
\frac{1}{1-x} &= 1+ x+x^2+x^3+\ldots & (|x|<1)
\ln(1+x) &= x - \frac{x^2}{2}+\frac{x^3}{3} - \ldots & (|x|<1) \end{align*} (:latexend:)

These provide many examples of series which not only converge, but can be evaluated exactly.

Example

Compute ($\frac{1}{3} + \frac{1}{9} + \frac{1}{27} + \frac{1}{81} + \ldots$).

(:toggle hide show="Answer" box1:)

Note that by the geometric series,

(:latex:) \begin{align*} \frac{1}{1-1/3} &= 1 + \frac{1}{3} + \frac{1}{9} + \ldots
&= \frac{3}{2}. \end{align*} (:latexend:)

So ($\frac{1}{3} + \frac{1}{9} + \ldots = \frac{1}{2}$).

Example

Compute ($1 - \frac{\pi^2}{2!} + \frac{\pi^4}{4!} - \frac{\pi^6}{6!} + \ldots$).

(:toggle hide show="Answer" box2:)

Note that this is the Taylor series for ($\cos(x)$) with ($x= \pi$). Thus, the series evaluates to ($\cos(\pi) = -1$).
Classifying series

There are some series which cannot be evaluated exactly, though it is known that the series converges. For example, the series

(:latex:) \begin{align*} \sum_{n=1}^\infty \frac{1}{n^3} &= 1 + \frac{1}{8} + \frac{1}{27} + \frac{1}{64} + \ldots
& \approx 1.2 \end{align*} (:latexend:)

converges, but it is not known what the exact value is (though one can calculate as many digits as one likes). This is in contrast with an apparently similar series,

(:latex:) \begin{align*} \sum_{n=1}^\infty \frac{1}{n^2} &=1+ \frac{1}{4} + \frac{1}{9} + \frac{1}{16} + \ldots
&= \frac{\pi^2}{6}, \end{align*} (:latexend:)

for which an exact value is known (though the proof of this value is beyond the scope of this course).

Yet another similar series, called the harmonic series,

(:latex:) \begin{equation*} \sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \ldots, \end{equation*} (:latexend:) diverges, as will be shown in the next module.

There are two questions then. First, does a series converge or not? Second, if it does converge, to what does it converge? This course deals mostly with the first question, in this module and the next few modules. More advanced analysis classes can help answer the second question.
When intuition fails

Determining the convergence of a series using intuition can be dangerous. As one example of how intuition can fail, consider what happens when we plug ($x=1$) into the series for ($\ln(1+x)$):

(:latex:) \[ \ln 2 = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \frac{1}{6} + \dotsb. \] (:latexend:)

Although ($x=1$) is not in the radius of convergence for this series, it turns out that this series still converges. Now, consider what happens if we multiply both sides by ($\frac{1}{2}$):

(:latex:) \[ \frac{1}{2} \ln 2 = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \dotsb. \] (:latexend:)

Adding this equation together with the above one, some of the terms cancel and some combine to show that

(:latex:) \[ \frac{3}{2}\ln 2 = 1 + \frac{1}{3} - \frac{1}{2} + \frac{1}{5} + \frac{1}{7} - \frac{1}{4} + \frac{1}{9} + \frac{1}{11} - \frac{1}{6} + \dotsb \] (:latexend:)

Now, notice that this series has all the terms of the series for ($\ln 2$), but in slightly different order. And yet, the series evaluates to a different value. That is certainly counter intuitive. Perhaps even more alarming, the terms of the series for ($\ln 2$) can be rearranged so that the resulting series evaluates to any real number. The takeaway is that we must tread carefully and not trust intuition but instead rely on logic.
The nth term test for divergence

The first, and usually simplest, test for divergence of a series is the nth term test.

The nth term test for divergence

If ($\displaystyle \lim_{n \rightarrow \infty} a_n \neq 0$), then the series ($\displaystyle \sum_{n=0}^\infty a_n$) diverges.

(:toggle hide show="Proof" boxproof:)

We give a proof by contrapositive. That is, we prove that if ($\displaystyle \sum_{n=0}^\infty a_n$) converges, then ($\displaystyle \lim_{n \rightarrow \infty} a_n = 0$).

Assume ($\displaystyle \sum_{n=0}^\infty a_n$) converges. Then by the definition of convergence, we know that the sequence of partial sums ($s_T$) defined by

(:latex:) \[ s_T = \sum_{n=1}^T a_n \] (:latexend:)

converges also. Therefore,

(:latex:) \[ \lim_{T \rightarrow \infty} s_T = \lim_{T \rightarrow \infty} s_{T-1} = L \] (:latexend:)

for some ($L$). Then we have

(:latex:) \[ \lim_{T \rightarrow \infty} \left( s_T - s_{T-1} \right) = 0, \] (:latexend:)

by linearity of the limit. But notice that

(:latex:) \begin{align*} s_T - s_{T-1} &= \sum_{n=1}^T a_n - \sum_{n=1}^{T-1} a_n
&= \left(a_1 + a_2 + \dotsb +a_{T-1} + a_T \right) - \left(a_1 + a_2 + \dotsb + a_{T-1} \right)
&= a_T. \end{align*} (:latexend:)

Putting this together with the above limit, we find

(:latex:) \begin{align*} \lim_{T \rightarrow \infty} \left( s_T - s_{T-1} \right) &= \lim_{T \rightarrow \infty} a_T
&= 0, \end{align*} (:latexend:)

which is what we were trying to prove.

This test applies to all series, and it is easy to apply (just take the limit of the terms of the series). However, many of the series encountered in this course will have terms which go to 0 in the limit, in which case the test is inconclusive (see the caveat below).

Example

Show that the series

(:latex:) \[ \sum_{n=0}^\infty \frac{4^n - 3^n}{4^n + 2^n} \] (:latexend:)

diverges.

(:toggle hide show="Answer" box2b:)

Here,

(:latex:) \[ a_n = \frac{4^n-3^n}{4^n + 2^n}. \] (:latexend:)

Applying the nth term test, we find

(:latex:) \begin{align*} \lim_{n \rightarrow \infty} a_n &= \lim_{n \rightarrow \infty} \frac{4^n-3^n}{4^n + 2^n}
&= \lim_{n \rightarrow \infty} \frac{4^n(1-(3/4)^n)}{4^n(1+(1/2)^n)}
&= \lim_{n \rightarrow \infty} \frac{1-(3/4)^n}{1+(1/2)^n}
&= 1 \neq 0, \end{align*} (:latexend:)

because both ($\left(\frac{3}{4}\right)^n \rightarrow 0$) and ($\left(\frac{1}{2}\right)^n \rightarrow 0$). Therefore, by the nth term test, the series diverges.

Example

Show that the series

(:latex:) \begin{equation*} \sum_{n=0}^\infty (-1)^n = 1-1+1-1+1-\ldots \end{equation*} (:latexend:)

diverges.

(:toggle hide show="Answer" box3:)

Since ($\lim_{n \rightarrow \infty} (-1)^n$) does not exist (the sequence oscillates), the series diverges by the ($n$)th term test.

Example

Show that the series

(:latex:) \begin{equation*} \sum_{n=1}^\infty \cos\left(\frac{1}{n}\right) = \cos(1) + \cos(1/2) + \cos(1/3) + \ldots \end{equation*} (:latexend:)

diverges.

(:toggle hide show="Answer" box4:)

Note that ($\lim_{n \rightarrow \infty} \cos\left(\frac{1}{n}\right) = \cos(0) = 1 \neq 0$). Thus, by the nth term test, the series diverges.
Caveat

This is not a test for convergence! In particular, if ($\displaystyle \lim_{n \rightarrow \infty} a_n = 0$), then the test is inconclusive (the series might converge or diverge). If the test is inconclusive, one of the other tests from the upcoming modules must be used.

In logical terms, this says that the converse of the nth term test does not hold. On the other hand, the contrapositive does hold:

(:latex:) \[ \sum_{n=0}^\infty a_n \hbox{ converges } \quad \Rightarrow \quad \lim_{n \rightarrow \infty} a_n = 0 \] (:latexend:)

(The contrapositive of a true statement is always true, but the converse is not always true).

Example

What does the nth term test say about the series ($\sum_{n=2}^\infty \frac{\ln(n)}{n}$)?

(:toggle hide show="Answer" box5:)

Note that ($\lim_{n\rightarrow \infty} \frac{\ln(n)}{n} = 0$), either by using l'Hospital's rule or by recalling that ($\ln(n)$) grows much more slowly than ($n$). Thus, the nth term test is inconclusive.

Example

What does the nth term test say about the series

(:latex:) \[ \sum_{n=1}^\infty \arctan n? \] (:latexend:)

(:toggle hide show="Answer" box6:)

Note that

(:latex:) \[ \lim_{n \rightarrow \infty} \arctan n = \frac{\pi}{2} \neq 0, \] (:latexend:)

and so by the nth term test, the series diverges.

Example

Suppose the series

(:latex:) \[ \sum_{n=1}^\infty a_n = L, \] (:latexend:)

converges, and that ($a_n > 0$) for all ($n$). What, if anything, can be said about the convergence of the series

(:latex:) \[ \sum_{n=1}^\infty \frac{1}{a_n}? \] (:latexend:)

(:toggle hide show="Answer" box7:)

By the contrapositive of the nth term test mentioned above, we know that since the series

(:latex:) \[ \sum_{n=1}^\infty a_n \] (:latexend:)

converges, we know that

(:latex:) \[ \lim_{n \rightarrow \infty} a_n = 0. \] (:latexend:)

But this implies that

(:latex:) \[ \lim_{n \rightarrow \infty} \frac{1}{a_n} = \infty \] (:latexend:)

so by the nth term test, we know that the series

(:latex:) \[ \sum_{n=1}^\infty \frac{1}{a_n} \] (:latexend:)

diverges.
EXERCISES

    Determine whether the following series converges or diverges 

(:latex:)\[ \sum_{n=2}^{\infty} \frac{n^3}{n \ln(n^{100})} \](:latexend:)

(:latex:)\[ \sum_{n=1}^{\infty} \frac{2^n}{n^{100}} \](:latexend:) 