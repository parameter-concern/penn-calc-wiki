---
title: Tables and computers
description: Using tables of integrals and mathematics software
lecture_number: 29
topic_number: 3
layout: lecture
mathjax: true
---
This module discusses some of the shortcuts available by using tables of integrals and mathematical software. Many integrals can be easily computed by a computer algebra system, but it is still important to know the underlying concepts so as to be able to use these tools efficiently and accurately.
Tables of integrals

Most calculus textbooks have an appendix containing one hundred or more integral formulas. All of these formulas can be derived using the techniques of the previous modules (possibly with some additional technical algebra), and it is a good exercise to try to derive some of them.

Using the table is sometimes difficult, because finding the correct form can be tricky. And even with the correct form, an integral may not match the form precisely. It may take some algebra and a u-substitution to match the form.

Example Use the formula

(:latex:) \begin{equation*} \int \frac{dx}{x^2\sqrt{x^2-a^2}} = \frac{\sqrt{x^2-a^2}}{a^2x} + C \end{equation*} (:latexend:)

to evaluate the integral

(:latex:) \[ \int \frac{dx}{(4x^2+4x+1)\sqrt{4x^2+4x-3}}. \] (:latexend:)

(:toggle hide show="Answer" box1:)

Although it is not exactly in the correct form, completing the square should get it closer. Indeed, factoring and completing the square gives

(:latex:) \begin{align*} \int \frac{dx}{(4x^2+4x+1)\sqrt{4x^2+4x-3}} &= \int \frac{dx}{(2x+1)^2\sqrt{(2x+1)^2-4}}. \end{align*} (:latexend:)

Now, making the u-substitution ($u = 2x+1$) (hence ($dx = \frac{1}{2} \,du$)) gives

(:latex:) \begin{align*} \int \frac{dx}(2x+1)^2\sqrt{(2x+1)^2-4}} &= \frac{1}{2} \int \frac{du}{u^2 \sqrt{u^2 - 4}}
&= \frac{1}{2} \frac{\sqrt{u^2-4}}{4u} + C
&= \frac{1}{2} \cdot \frac{\sqrt{\left(2x+1\right)^2-4}}{4\left(2x+1\right) + C. \end{align*} (:latexend:)

Other table entries are more inductive in nature, like the reduction formulas mentioned in the integration by parts module.

Example

Use the formulas

(:latex:) \begin{equation*} \int \sec ax\, dx = \frac{1}{a} \ln |\sec ax + \tan ax| + C, \end{equation*} (:latexend:)

and (for ($n \geq 2$))

(:latex:) \begin{align*} \int \sec^nax\, dx &= \frac{\sec^{n-2}ax \tan ax}{a(n-1)} + \frac{n-2}{n-1} \int \sec^{n-2}ax\,dx + C \end{align*} (:latexend:)

to find

(:latex:) \[ \int \sec^3(x)\,dx. \] (:latexend:)

(:toggle hide show="Answer" box2:)

Reducing using the second formula, and then using the first formula gives

(:latex:) \begin{align*} \int sec^3x &= \frac{\sec x \tan x}{2} + \frac{1}{2} \int \sec x\,dx
&= \frac{\sec x \tan x}{2} + \frac{1}{2} \ln |\sec x + \tan x| + C. \end{align*} (:latexend:)
Mathematical software

Expensive computer algebra systems such as Maple and Mathematica can quickly and accurately dispense with most integrals that can be done by hand. One free alternative, from the makers of Mathematica, is Wolfram Alpha, which for most purposes is as good as its more costly relatives, and in many cases it can explain the intermediate steps of longer computations (though it now only provides three such explanations per day for a user without a paid subscription).

Note that the form of the answer given by computer systems may look different from what one gets by hand or by a table, so care should be taken when comparing answers.

Example

Compute ($\int \sec^3(x)\,dx$) using Wolfram Alpha, or other computer algebra system. Note the syntax of the entry (though it is pretty good at parsing other forms of entry). Also note that the answer given is in a different form than that found in the earlier example.

Answer

Example

There are limits to what a computer algebra system can do. Consider the integral

(:latex:) \[ \int_{x=0}^{\pi/2} \frac{\sin^n x}{\sin^n x + \cos^n x} \, dx. \] (:latexend:)

It turns out that the value of this integral is ($\frac{\pi}{4}$) for all ($n$), although Wolfram Alpha is not be able to compute it.

But if we enter small particular values of ($n$) into Wolfram Alpha, then it does give the answer, although sometimes only in decimal form. 