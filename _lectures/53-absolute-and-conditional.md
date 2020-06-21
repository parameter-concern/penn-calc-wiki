---
title: Absolute and conditional
description: Two types of series convergence
lecture_number: 53
topic_number: 5
layout: lecture
mathjax: true
---
Up until now, the convergence tests covered by this course have only covered series with positive terms. What happens when a series has some positive and some negative terms? This module describes some tools for determining the convergence or divergence of such a series.
Alternating series test

One particular type of series is fairly simple to test for convergence. A series ($\sum a_n$) is alternating if it is of the form ($\sum (-1)^n b_n$), where ($b_n$) is a positive sequence. In other words, a series is alternating if its terms are alternately positive and negative.

Alternating Series Test

An alternating series ($\sum (-1)^n b_n$) with decreasing terms converges if and only if ($\lim_{n \rightarrow \infty} b_n = 0$).

The intuition behind this test is that if the terms are alternating, decreasing, and go to zero, then the partial sums of the series gradually zero in on the true value. The first partial sum is greater than the true value, the second partial sum is less than the true value, and so on:

Example

The series

(:latex:) \[ 1-\frac{1}{2}+\frac{1}{3}-\frac{1}{4}+\ldots \] (:latexend:)

is alternating. Its terms are decreasing, and the terms go to zero, so by the alternating series test, the series converges.

Example

Determine if

(:latex:) \[ \sum_{n=0}^\infty (-1)^n \frac{1}{2^n} \] (:latexend:)

converges.

(:toggle hide show="Answer" box1:)

The series is alternating, the terms are decreasing, and ($\lim_{n \rightarrow \infty} \frac{1}{2^n} = 0$). Thus, by the alternating series test, the series converges.

Alternatively, we can observe that this series is geometric:

(:latex:) \begin{align*} \sum_{n=0}^\infty (-1)^n \frac{1}{2^n} &= \sum_{n=0}^\infty \left(-\frac{1}{2}\right)^n
&= \frac{1}{1-(-1/2)}
&= \frac{2}{3}. \end{align*} (:latexend:)

Example

Determine if

(:latex:) \[ \sum_{n=2}^\infty (-1)^n \frac{\ln(n)}{n} \] (:latexend:)

converges.

(:toggle hide show="Answer" box2:)

The series is alternating, terms are decreasing, and

(:latex:) \[ \lim_{n \rightarrow \infty} \frac{\ln(n)}{n} = 0. \] (:latexend:)

And so by the alternating series test, the series converges.
Conditional and absolute convergence

Consider the two previous examples. Note that both ($\sum (-1)^n \frac{1}{2^n}$) and ($\sum (-1)^n \frac{\ln(n)}{n}$) converge. However, if these series were not alternating, then ($\sum \frac{1}{2^n}$) still converges (it is geometric), whereas ($\sum \frac{\ln(n)}{n}$) does not converge (comparison with the harmonic series ($\sum \frac{1}{n}$)).

These series demonstrate a distinction between two types of convergence.

Absolute and Conditional Convergence

The series ($\sum a_n$) converges absolutely if ($\sum |a_n|$) converges.

A series ($\sum a_n$) converges conditionally if ($\sum a_n$) converges, but ($\sum |a_n|$) diverges.

In other words, a series is conditionally convergent if it is convergent but not absolutely convergent.

Example

Using this terminology, the series

(:latex:) \[ \sum_{n=0}^\infty (-1)^n \frac{1}{2^n} \] (:latexend:)

converges absolutely, but

(:latex:) \[ \sum_{n=2}^\infty (-1)^n \frac{\ln(n)}{n} \] (:latexend:)

converges conditionally.

Example

Find the values of ($p$) for which the alternating p-series

(:latex:) \[ \sum_{n=1}^\infty (-1)^n \frac{1}{n^p} \] (:latexend:)

diverges, converges conditionally, and converges absolutely.

(:toggle hide show="Answer" box3:)

When ($p \leq 0$), the terms of the series do not go to 0. That is,

(:latex:) \[ \lim_{n \rightarrow \infty} \frac{1}{n^p} \neq 0. \] (:latexend:)

So by the nth term test for divergence, the series diverges for these values of ($p$).

When ($0 < p \leq 1$), the terms of the series are decreasing, alternating, and going to 0. So by the alternating series test, the series converges for this range of ($p$). However, if absolute values are taken, then the resulting series, ($\sum \frac{1}{n^p}$), does not converge by the p-series test. Thus, for ($0<p \leq 1$), the series converges conditionally.

When ($1<p$), the series converges absolutely by the p-series test.

Example

Determine if

(:latex:) \[ \sum_{n=1}^\infty (-1)^n \frac{e^n}{n^5} \] (:latexend:)

converges, and if so, whether it is conditional or absolute convergence.

(:toggle hide show="Answer" box4:)

The series is alternating, but notice that the terms do not go to 0, since ($e^n>n^5$). Therefore, by the nth term test for divergence, this series diverges.

Example

Determine if (:latex:) \[ \sum_{n=1}^\infty (-1)^n \frac{n!}{n^n} \] (:latexend:)

converges, and if so, whether it is conditional or absolute convergence.

(:toggle hide show="Answer" box5:)

The series is alternating, and note that ($n^n>n!$), which leads us to believe that the series converges. In fact, the series converges absolutely, i.e.

(:latex:) \[ \sum \frac{n!}{n^n} \] (:latexend:)

converges, as the ratio test shows, along with some careful algebra:

(:latex:) \begin{align*} \rho &= \lim_{n \rightarrow \infty} \frac{(n+1)!}{(n+1)^{n+1}} \cdot \frac{n^n}{n!}
&= \lim_{n \rightarrow \infty} \frac{(n+1)n^n}{(n+1)^{n+1}}
&= \lim_{n \rightarrow \infty} \frac{n^n}{(n+1)^n}
&= \lim_{n \rightarrow \infty} \left(\frac{n}{n+1}\right)^n
&= \lim_{n \rightarrow \infty} \frac{1}{\left(\frac{n+1}{n}\right)^n}
&= \lim_{n \rightarrow \infty} \frac{1}{(1+1/n)^n}
&= \frac{1}{e} < 1. \end{align*} (:latexend:)

So ($\rho<1$), and so the series converges absolutely.
Absolute convergence test

Some series are not strictly alternating, but have some positive and some negative terms, sporadically. In this situation, it can be difficult to determine whether the series converges directly, but the following test sometimes makes the determination easier.

Absolute Convergence Test

If the series ($\sum |a_n|$) converges, then ($\sum a_n$) converges. In other words, if a series converges absolutely, then the series converges.

(:toggle hide show="Justification" boxact:)

Consider the series ($\sum (a_n + |a_n|)$). Note that

(:latex:) \[ 0 \leq a_n + |a_n| \leq 2|a_n| \] (:latexend:)

So ($\sum (a_n + |a_n|) \leq \sum 2|a_n|$), and by the comparison test we find ($\sum (a_n + |a_n|)$) converges. Then

(:latex:) \begin{align*} \sum a_n &= \sum ((a_n+|a_n|)-|a_n|)
&= \sum (a_n + |a_n|) - \sum |a_n| \end{align*} (:latexend:)

converges too, being the difference of two convergent, positive series.

Example

Determine if

(:latex:) \[ \sum_{n=1}^\infty \frac{\sin(n)}{n^2} \] (:latexend:)

converges or diverges.

(:toggle hide show="Answer" box7:)

($\sin(n)$) is a messy function because it is sometimes positive and sometimes negative, but not in a simple alternating pattern. However, one nice thing about ($\sin(n)$) is that, in absolute value, it is bounded by 1. So

(:latex:) \begin{equation*} \sum_{n=1}^\infty \left| \frac{\sin(n)}{n^2} \right| \leq \sum_{n=1}^\infty \frac{1}{n^2}. \end{equation*} (:latexend:)

Since ($\sum \frac{1}{n^2}$) converges by p-series test, it follows by the comparison test that ($\sum \left| \frac{\sin(n)}{n^2} \right|$) converges. Hence ($\sum \frac{\sin(n)}{n^2}$) converges absolutely, and so it converges by the absolute convergence test.
EXERCISES

    Determine whether the following series converges or not. If it converges, is it conditionally convergent or absolutely convergent? 

(:latex:) \[ \sum_{n=2}^{\infty} (-1)^n \frac{1}{n \ln(n)} \] (:latexend:)

(:latex:) \[ \sum_{n=1}^{\infty} (-1)^n \frac{n^{1/2}}{((n+1)(n+2)(n+3))^{1/2}} \] (:latexend:)

    Determine whether the following series is convergent or divergent 

(:latex:) \[ \sum_{n=1}^{\infty} \cos(n) \frac{\ln(n)}{n!} \] (:latexend:) 