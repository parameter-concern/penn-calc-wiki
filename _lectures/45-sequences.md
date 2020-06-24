---
title: Sequences
description: Discrete-input functions
lecture_number: 45
topic_number: 5
layout: lecture
mathjax: true
hidden_answers: true
---
The remainder of the course is a look at discrete calculus, which is a study of all the previous sections (functions, derivatives, integrals) applied to a different kind of function: sequences. A sequence is a function, but instead of taking any real number as input, a sequence takes an integer as input.
Sequence

A sequence $$a$$ is a function from the non-negative integers $$0,1,2,3,\ldots$$ to the real numbers $$\bbr$$. The usual functional notation $$a(n)$$ is sometimes replaced with $$a_n$$. There are several ways to define a sequence. Here are three of the most common ways, demonstrated on the powers of 2.

- An explicit formula gives $$a_n$$ as a function of $$n$$, i.e. $$a_n = f(n)$$. This is usually the most convenient, since it typically gives the most information about the sequence. e.g. $$a_n = 2^n$$ for $$n \geq 0$$.
- A recursion relation gives $$a_n$$ as a function of previous terms in the sequence. Note that some initial conditions must be given as well. $$a_n = f(a_{n-1},a_{n-2},\ldots,a_{n-k})$$. e.g. $$a_n = 2a_{n-1}$$; $$a_0=1$$.
- Finally, listing terms can be used if no explicit or recursive formula is available. This is sometimes used in experimental settings so that one can study the terms and look for a pattern. e.g. $$a = (1,2,4,8,16,32,\ldots)$$. 

**Example**

Write out the first six terms of the sequence defined by $$a_n = 2a_{n-1}+1$$; $$a_0=0$$. Look for a pattern to try to find an explicit formula for $$a_n$$.

<button class="toggle" data-box="#box0a">Answer</button>

<div id="box0a" class="answer-hidden"></div>
{: id="box0a" class="answer-hidden"}


$$
\begin{align*}
a_0 &= 0
a_1 &= 2a_0+1 = 1
a_2 &= 2a_1+1 = 3
a_3 &= 2a_2+1 = 7
a_4 &= 2a_3+1 = 15
a_5 &= 2a_4+1 = 31.
\end{align*}
$$

One might notice that adding 1 to each term in the sequence gives the sequence $$(1,2,4,8,16,32,\ldots)$$, which look like the powers of 2. So it appears that $$a_n = 2^n-1$$ for $$n \geq 0$$.
Limits of sequences

Recall that limits of functions came in two flavors. First, there were limits of the form $$\lim_{x \rightarrow c} f(x)$$. The second type of limits were of the form $$\lim_{x \rightarrow \infty} f(x)$$.

Only the second type of limit is sensible for a sequence. (To see why the first type of limit does not make sense for sequences, go back to the definition of a limit.) The definition of $$\lim_{n \rightarrow \infty} a_n$$ for sequences is the same as for continuous functions:

The Limit of a Sequence

We say that

$$
\lim_{n \rightarrow \infty} a_n = L
$$

if for any $$\epsilon>0$$ there exists $$M$$ such that for all $$n > M$$,

$$
\verta_n - L\vert<\epsilon.
$$

In other words, the sequence $$a_n$$ has limit $$L$$ if $$a_n$$ gets arbitrarily close to $$L$$ for sufficiently large $$n$$. If the limit $$L$$ exists, then the sequence $$a_n$$ is said to converge to $$L$$.

Intuitively, a sequence $$a_n$$ has a limit if for any band around $$L$$, there is some point where all the terms of $$a_n$$ are within the band around $$L$$:

Recall that Newton's method defined a sequence of numbers defined by the recursion relation

$$
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}.
$$

Here, the sequence hopefully converged to a root of the function $$f(x)$$. This gives an example of an application where it is useful to know about the convergence of a sequence.

**Example**

Let $$a_n = 4 + \frac{(-1)^n}{n}$$. Find $$\lim_{n \rightarrow \infty} a_n$$, if the limit exists. If the limit does not exist, explain why.

<button class="toggle" data-box="#box0b">Answer</button>

<div id="box0b" class="answer-hidden"></div>
{: id="box0b" class="answer-hidden"}


We claim the limit is 4. We know that

$$
\lim_{n \rightarrow \infty} \frac{1}{n} = 0.
$$

Therefore, for any $$\epsilon > 0$$ we can choose $$M$$ so that $$\frac{1}{M} < \epsilon$$. Then for any $$n > M$$, we have

$$
\begin{align*}
\verta_n - 4\vert &= \left\vert 4 + \frac{(-1)^n}{n} - 4 \right\vert
&= \left\vert \frac{(-1)^n}{n}\right\vert
&= \frac{1}{n}
& < \frac{1}{M}
& < \epsilon,
\end{align*}
$$

as desired. For this course, we will not typically be this formal, but it is useful to see this type of argument at least a few times.

**Example**

Let $$a_n = (-1)^n$$. Find $$\lim_{n \rightarrow \infty} a_n$$, if the limit exists. If the limit does not exist, explain why.

<button class="toggle" data-box="#box0c">Answer</button>

<div id="box0c" class="answer-hidden"></div>
{: id="box0c" class="answer-hidden"}


From the intuitive understanding of a limit, it is clear that the terms of this sequence are not getting closer together, and so the limit does not exist.

More formally, suppose the limit, say $$L$$, existed. Then from the definition of the limit of a sequence, we could find a number $$M$$ such that

$$
\verta_n - L\vert < \frac{1}{3}
$$

for all $$n > M$$. Since the terms of the sequence are $$-1$$ and $$1$$, this would imply

$$
\vert-1-L\vert < \frac{1}{3}
$$

This implies

$$
\begin{align*}
-\frac{1}{3} < & -1-L < \frac{1}{3}
\frac{2}{3} < &-L < \frac{4}{3}
-\frac{2}{3} > &L > \frac{-4}{3}.
\end{align*}
$$

Similarly,

$$
\vert1-L\vert < \frac{1}{3}
$$

which implies by similar algebra that

$$
\frac{4}{3} > L > \frac{2}{3}.
$$

Since $$L$$ cannot be simultaneously positive and negative, we have reached a contradiction. And so we see that the limit $$L$$ cannot exist.
Methods for computing limits

Many of the methods for computing limits of continuous functions carry over to computing limits of sequences. In particular, all of the big-O notation still applies.

**Example**

Compute the limit of the sequence $$a_n = 3n - \sqrt{9n^2+6n}$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


A little factoring from the radical, and using the binomial series gives

$$
\begin{align*}
a_n &= 3n - \sqrt{9n^2+6n}
&= 3n - 3n \sqrt{1 + \frac{2}{3n}}
&= 3n \left(1- \sqrt{1+\frac{2}{3n}}\right)
&= 3n \left(1-(1+\frac{1}{2}\frac{2}{3n} + O(1/n^2))\right)
&= -1 + O\left(\frac{1}{n}\right).
\end{align*}
$$

So the limit is $$-1$$.
Monotone, bounded sequences

In general, it can be difficult to find the limit of a sequence, but for certain sequences it is possible to prove that the limit exists.

A sequence is monotone increasing if it is non-decreasing, i.e., $$a_0 \leq a_1 \leq a_2 \leq \ldots$$. A sequence is monotone decreasing if it is non-increasing, i.e., $$a_0 \geq a_1 \geq a_2 \geq \ldots$$. A sequence that is either monotone increasing or monotone decreasing is monotone.

A sequence is bounded above if there exists some real number $$B$$ such that $$a_n \leq B$$ for all $$n\geq 0$$. Similarly, a sequence is bounded below if there exists a real number $$C$$ such that $$a_n \geq C$$ for all $$n \geq 0$$. A sequence is bounded if it is both bounded above and bounded below.

Monotone Convergence Theorem

If a sequence $$a_n$$ is bounded and monotone, then the sequence converges.

**Example**

Let $$a_n$$ be the sequence defined by $$a_n = \frac{5+a_{n-1}}{2}$$; $$a_0 = 1$$. Show that the sequence converges by using the Monotone Convergence Theorem.

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


It is not obvious that this sequence is either bounded or monotone. Writing out the first few terms, though, gives $$a = (1,3,4,4.5,4.75,\ldots)$$. It appears that the sequence is increasing, and that $$a_n \leq 5$$ for all $$n \geq 0$$.

To show that the sequence is increasing, use induction. The first few terms are increasing, so assume that $$a_{n-1} \leq a_n$$ for some $$n$$. Then adding 5 and dividing by 2 throughout gives $$\frac{5+a_{n-1}}{2} \leq \frac{5+a_n}{2}$$, which implies $$a_n \leq a_{n+1}$$ by the recursive definition of $$a_n$$. Thus, the sequence is increasing.

To see that $$a_n \leq 5$$, again use induction. Assume $$a_n\leq 5$$ for some $$n$$. Then adding 5 and dividing by 2 gives $$ \frac{5+a_n}{2} \leq \frac{5+5}{2} = 5$$. This means $$a_{n+1} \leq 5$$ by the definition of $$a_n$$. Thus, $$a_n \leq 5$$ for all $$n$$. Finally, note that any increasing sequence is bounded below. So the sequence is bounded.

Thus, by the Monotone Convergence Theorem, the sequence $$a_n$$ converges.
Recursion relations and limits

When a sequence is defined by a recursion relation and the limit of the sequence exists, one can find the limit by simply taking the limit of both sides of the recursion relation and solving. This is best demonstrated by example.

**Example**

Find the limit $$L = \lim_{n \rightarrow \infty} a_n$$, where $$a_n = \frac{5+a_{n-1}}{2}$$; $$a_0 = 1$$, as in the previous example.

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


The limit exists by the previous example, so taking limits of both sides of the recursion relation and simplifying gives

$$
\begin{align*}
\lim_{n \rightarrow \infty} a_n &= \lim_{n \rightarrow \infty} \frac{5+a_{n-1}}{2}
L &= \frac{5+ \lim_{n \rightarrow \infty} a_{n-1}}{2}
L &= \frac{5+L}{2}.
\end{align*}
$$

(Note that $$\lim a_{n-1} = \lim a_n$$ because the limit of a sequence does not depend on the indexing of the terms.) Now, solving for $$L$$ gives $$2L = 5+L$$, so $$L = 5$$.

**Example**

Find

$$
\begin{equation*} L = 1+\frac{1}{1+\frac{1}{1+\frac{1}{1+\ldots}}} \end{equation*}
$$

by expressing $$L$$ as a limit of a recursively defined sequence $$a_n$$ which begins $$(1,1+\frac{1}{1},1+\frac{1}{2},\ldots)$$. Assume that the limit exists.

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


The sequence $$a_n$$ can be defined recursively by $$a_n = 1+ \frac{1}{a_{n-1}}$$; $$a_0 = 1$$. Then taking limits of both sides gives $$L = 1+\frac{1}{L}$$. Multiplying through and collecting terms gives $$L^2-L-1 = 0$$, and solving for $$L$$ gives $$L = \frac{1\pm \sqrt{5}}{2}$$.

Note though that $$a_n > 0$$ for all $$n$$, so it must be that $$L = \frac{1+\sqrt{5}}{2}$$. This is the celebrated golden ratio.

**Example**

Find $$\sqrt{1+\sqrt{1+\sqrt{1+\dotsb}}}$$. Assume the limit exists.

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


One can express this as the limit of a recursively defined sequence $$a_n$$ given by $$a_0=1$$ and $$a_n = \sqrt{1+a_{n-1}}$$. Then letting $$L = \lim a_n$$, and taking limits of the recursion relation gives

$$
L = \sqrt{1+L}.
$$

Squaring both sides and collecting terms gives $$L^2-L-1 = 0$$, which is the same equation from the previous example. Thus, the limit is again the golden ratio $$L = \frac{1+\sqrt{5}}{2}$$.

The golden ratio, often denoted

$$
\varphi = \frac{1+\sqrt{5}}{2},
$$

appears in many settings, both man made and natural. The golden ratio is also deeply connected with the Fibonacci numbers, as we will see in this example and in the future.

**Example**

The Fibonacci sequence, $$F_n$$ is defined by the recursion relation and initial conditions

$$
F_{n+2} = F_{n+1} + F_n; \quad F_0 = 0, F_1 = 1.
$$

So the first few Fibonacci numbers are

$$
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, \ldots
$$

Show that

$$
\lim_{n \rightarrow \infty} \frac{F_{n+1}}{F_n} = \varphi.
$$

You may assume that the limit of the sequence exists. Hint: Observe that

$$
\frac{F_{n+1}}{F_n} = \frac{F_n + F_{n-1}}{F_n} = 1 + \frac{F_{n-1}}{F_n}.
$$

<button class="toggle" data-box="#box6">Answer</button>

<div id="box6" class="answer-hidden"></div>
{: id="box6" class="answer-hidden"}


Let

$$
L = \lim_{n \rightarrow \infty} \frac{F_{n+1}}{F_n}.
$$

Then, beginning with the hint and taking the limit of both sides, we have

$$
\begin{align*}
\lim_{n \rightarrow \infty} \frac{F_{n+1}}{F_n} &= \lim_{n \rightarrow \infty} \left(1 + \frac{F_{n-1}}{F_n}\right)
&= 1 + \lim_{n \rightarrow \infty} \frac{F_{n-1}}{F_n}
&= 1 + \lim_{n \rightarrow \infty} \frac{1}{F_n/F_{n-1}}
&= 1 + \frac{1}{\displaystyle \lim_{n \rightarrow \infty} F_n/F_{n-1}}.
\end{align*}
$$

But this means

$$
L = 1 + \frac{1}{L},
$$

which is an equation which we solved in an above example, where we found

$$
L = \frac{1+\sqrt{5}}{2},
$$

as desired.

## Exercises

- Compute the limit of the sequence $$a_n= 2n^2-(8n^6+6n^4)^{1/3} $$. 