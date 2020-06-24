---
title: L'Hopital's Rule
description: Statement and examples in a Taylor series context
lecture_number: 8
topic_number: 1
layout: lecture
mathjax: true
hidden_answers: true
---
In previous modules, we saw that Taylor series are useful for computing certain limits of ratios. But sometimes, a fact known as L'Hopital's rule is easier to use than Taylor series. While L'Hopital's rule is commonly taught in a first calculus course, the justification for why it works is not usually taught. This module gives a justification for L'Hopital's rule, using Taylor series.
L'Hopital's rule

There are some limit situations where Taylor series are not particularly easy to use. For example, if the limit is being taken at a point about which the Taylor expansion is not already known, or the limit is at infinity, then using Taylor series is usually more work than it is worth. These are the situations where L'Hopital's rule can be helpful.

L'Hopital's Rule, $$\frac{0}{0}$$ case

If $$f$$ and $$g$$ are continuous functions such that $$\displaystyle \lim_{x \rightarrow a} f(x) = 0$$ and $$\displaystyle\lim_{x \rightarrow a} g(x) = 0$$, then $$\displaystyle \lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \lim_{x\rightarrow a} \frac{f'(x)}{g'(x)}$$, provided this limit exists. If this is still of the form $$\frac{0}{0}$$, then derivatives may be taken again, and so on.

<button class="toggle" data-box="#boxA">Answer</button>

<div id="boxA" class="answer-hidden"></div>
{: id="boxA" class="answer-hidden"}


The Taylor series for $$f$$ and $$g$$ about $$a$$ are given by

$$
\begin{align*}
f(x) &= f(a) + f'(a)(x-a) + \frac{f(a)}{2!}(x-a)^2+ \dotsb
g(x) &= g(a) + g'(a)(x-a) + \frac{g(a)}{2!}(x-a)^2 + \dotsb.
\end{align*}
$$

Since, by hypothesis, $$f(a) = g(a) = 0$$, it follows that

$$
\begin{align*}
\lim_{x\rightarrow a} \frac{f(x)}{g(x)} &= \lim_{x \rightarrow a} \frac{ f(a) + f'(a)(x-a) + \frac{1}{2}f(a)(x-a)^2 + \dotsb}{g(a) + g'(a)(x-a) + \frac{1}{2}g(a)(x-a)^2+\dotsb}
&= \lim_{x\rightarrow a} \frac{f'(a) (x-a) +(1/2)f(a)(x-a)^2 + \dotsb}{g'(a)(x-a) + (1/2)g(a)(x-a)^2+ \dotsb}
&= \lim_{x \rightarrow a} \frac{(x-a)\left[f'(a) + (1/2)f(a)(x-a) + \dotsb \right]}{(x-a)\left[g'(a) + (1/2)g(a)(x-a) + \dotsb \right]}
&= \lim_{x \rightarrow a} \frac{f'(a) + (1/2)f(a)(x-a) + \dotsb }{g'(a) + (1/2) g(a)(x-a) + \dotsb}.
\end{align*}
$$

Now, as $$x \rightarrow a$$, all the terms with $$x-a$$ go to 0, which leaves $$\frac{f'(a)}{g'(a)}$$. If this fraction is still $$0/0$$, then L'Hopital's rule says to take the derivative of the numerator and the denominator again. In terms of the Taylor series, this moves to the next leading terms in the numerator and denominator.

Example Using L'Hopital's rule, compute two of the limits from the last module:

$$
\begin{align*}
\lim_{x \rightarrow 0} & \frac{\sin x}{x}
\lim_{x \rightarrow 0} & \frac{1-\cos x}{x}.
\end{align*}
$$

<button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


These are both in the $$\frac{0}{0}$$ case, so differentiating numerator and denominator gives

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{\sin x}{x} &= \lim_{x \rightarrow 0} \frac{\cos x}{1}
&= 1.
\end{align*}
$$

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{1-\cos x}{x} &= \lim_{x \rightarrow 0} \frac{\sin x}{1}
&= 0.
\end{align*}
$$

Example Compute $$ \displaystyle \lim_{x \rightarrow 0} \frac{\tan x}{\arcsin x}$$. <button class="toggle" data-box="#box0b">Answer</button>

<div id="box0b" class="answer-hidden"></div>
{: id="box0b" class="answer-hidden"}


Since $$\tan 0 = \arcsin 0 = 0$$, we are in the $$\frac{0}{0}$$ case of L'Hopital's rule. Recall that

$$
\begin{align*}
\frac{d}{dx} \tan x &= \sec^2 x
\frac{d}{dx} \arcsin x &= \frac{1}{\sqrt{1-x^2}}.
\end{align*}
$$

Thus, applying L'Hopital's rule gives

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{\tan x}{\arcsin x} &= \lim_{x \rightarrow 0} \frac{ \sec^2 x }{ \frac{1}{\sqrt{1-x^2}} }
&= \frac{1}{1}
&= 1.
\end{align*}
$$

Depending on the situation, it still might be easier to use Taylor series, especially if there are compositions and products of functions (assuming we know all the relevant Taylor series).

Example Compute $$\displaystyle \lim_{x \rightarrow 0} \frac{x^2 \ln( \cos x)}{\sin^2(3x^2)} $$. <button class="toggle" data-box="#box0b1">Answer</button>

<div id="box0b1" class="answer-hidden"></div>
{: id="box0b1" class="answer-hidden"}


We know all the relevant Taylor series for the functions in this problem, so that should be an easier method. We find

$$
\begin{align*}
\lim_{x\rightarrow 0} \frac{x^2 \ln(\cos x)}{\sin^2(3x^2)} &= \lim_{x \rightarrow 0} \frac{x^2 \ln \left(1-\frac{x^2}{2!} + \hbox{ HOT}\right)}{\left(3x^2 + \hbox{ HOT}\right)^2}
&= \lim_{x \rightarrow 0} \frac{x^2 \left(-\frac{x^2}{2} - \hbox{ HOT}\right)}{9x^4 + \hbox{ HOT}}
&= \lim_{x \rightarrow 0} \frac{-\frac{x^4}{2} + \hbox{ HOT}}{9 x^4 + \hbox{ HOT}}
&= -\frac{1}{18}.
\end{align*}
$$

Using L'Hopital here would be quite a lot of work. It turns out that we would have to apply the rule four times, which involves a lot of product and chain rule.

L'Hopital's Rule, $$\frac{\infty}{\infty}$$ case

If $$\displaystyle \lim_{x\rightarrow a} f(x) = \lim_{x \rightarrow a} g(x) = \infty$$, then $$\displaystyle\lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \lim_{x\rightarrow a} \frac{f'(x)}{g'(x)}$$, again provided this limit exists.

Example Compute $$\displaystyle \lim_{x \rightarrow 0} \frac{\ln x}{\frac{1}{x^2}}$$. <button class="toggle" data-box="#box0c">Answer</button>

<div id="box0c" class="answer-hidden"></div>
{: id="box0c" class="answer-hidden"}


Note that $$\ln x \rightarrow -\infty$$ as $$x \rightarrow 0$$, and $$\frac{1}{x^2} \rightarrow \infty$$ as $$x \rightarrow 0$$. Therefore, the $$\frac{\infty}{\infty}$$ case of L'Hopital's rule applies. Applying the rule,

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{\ln x}{x^{-2}} &= \lim_{x \rightarrow 0} \frac{\frac{1}{x}}{-2 x^{-3}}
&= \lim_{x\rightarrow 0} \frac{x^2}{-2}
&= 0.
\end{align*}
$$

Example Use L'Hopital's rule to compute $$\displaystyle \lim_{x\rightarrow \pi} \frac{\sin(x)}{e^x \cos(x/2)}$$. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Since $$\sin, \cos, \exp$$ are all continuous functions, and $$\sin(\pi) = e^{\pi} \cos (\pi/2) = 0$$, the hypotheses for L'Hopital's rule are met. So it follows that

$$
\begin{align*}
\lim_{x\rightarrow \pi} \frac{\sin(x)}{e^x \cos(x/2)} &= \lim_{x\rightarrow \pi} \frac{[\sin(x)]'}{[e^x \cos(x/2)]'}
&= \lim_{x \rightarrow \pi} \frac{\cos(x)}{e^x \cos(x/2) -(1/2)e^x\sin(x/2)}
&= \frac{-1}{0 - (1/2)e^{\pi} \sin(\pi/2)}
&= 2e^{-\pi}.
\end{align*}
$$

Note that although we know the Taylor series for these functions at $$x=0$$, the limit here is as $$x \rightarrow \pi$$. Thus, we cannot use the Taylor series approach, because a Taylor series about $$x=0$$ does not give a good approximation when $$x$$ is not close to 0.
Other indeterminate forms

Some limits do not initially look like cases where L'Hopital's rule applies, but with some algebra they can be rearranged into one of the applicable cases. These are called indeterminate forms.
Case: $$\infty - \infty$$

First, consider $$\displaystyle \lim_{x \rightarrow a} f(x) - g(x)$$, where $$\displaystyle \lim_{x \rightarrow a} f(x) = \lim_{x\rightarrow a} g(x) = \infty$$. Usually, one or both of $$f$$ and $$g$$ are ratios of other functions. In this case, getting a common denominator usually transforms the limit into one where L'Hospital's rule or a Taylor series approach applies.

Example Compute $$\displaystyle \lim_{x \rightarrow 0} \frac{1}{\sin^2 x} - \frac{1}{x^2}$$. <button class="toggle" data-box="#box1a">Answer</button>

<div id="box1a" class="answer-hidden"></div>
{: id="box1a" class="answer-hidden"}


Getting a common denominator, and then Taylor expanding gives

$$
\begin{align*}
\lim_{x \rightarrow 0} \frac{1}{\sin^2x} - \frac{1}{x^2} &= \lim_{x\rightarrow 0} \frac{x^2 - \sin^2x}{x^2 \sin^2x }
&= \lim_{ x\rightarrow 0} \frac{x^2 - \left(x-\frac{1}{3!}x^3 + \dotsb \right)^2}{x^2 \left(x- \frac{1}{3!}x^3 + \dotsb\right)^2}
&= \lim_{x \rightarrow 0} \frac{x^2 - \left(x^2 - \frac{2}{3!}x^4 + \dotsb\right)}{x^2 \left(x^2 - \frac{2}{3!}x^3 + \dotsb\right)}
&= \lim_{x \rightarrow 0} \frac{\frac{2}{6}x^4 + \dotsb}{x^4 + \dotsb}
&= \frac{1}{3}.
\end{align*}
$$
Case: $$\infty \cdot 0$$

Next, consider $$\displaystyle \lim_{x \rightarrow a} f(x)g(x)$$ where $$\displaystyle \lim_{x \rightarrow a} f(x) = \infty$$ and $$\displaystyle \lim_{x \rightarrow a}g(x) = 0$$. Since $$\infty \cdot 0$$ is not defined, it is not clear what this limit is. However, the product can be turned into one of the following ratios where L'Hopital's rule applies:

$$
\begin{align*}
\lim_{x \rightarrow a} f(x)g(x) &= \lim_{x \rightarrow a} \frac{g(x)}{1/f(x)} \lim_{x \rightarrow a} f(x)g(x) &= \lim_{x \rightarrow a} \frac{f(x)}{1/g(x)}
\end{align*}
$$

since dividing by the reciprocal of a number is the same as multiplying. Now, note that $$\displaystyle \lim_{x \rightarrow a} 1/f(x) = 0$$, since $$\displaystyle \lim_{x \rightarrow a} f(x) = \infty$$. Thus, $$ \displaystyle \lim_{x \rightarrow a} \frac{g(x)}{1/f(x)}$$ is now in the $$\frac{0}{0}$$ case of L'Hopital's rule.

Similarly, $$\displaystyle \lim_{x \rightarrow a} \frac{f(x)}{1/g(x)}$$ is in the $$\frac{\infty}{\infty}$$ form of l'Hopital's rule, and so it can be applied here too.

Deciding which of the above forms to use depends on the situation, but in many situations either form will work.

Example Compute $$\displaystyle \lim_{x \rightarrow 0^+} x \ln x$$. (Here we use the one-sided limit $$x \rightarrow 0^+$$ becuase $$\ln$$ is only defined on the positive real numbers). <button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden"></div>
{: id="box1b" class="answer-hidden"}


This is of the form $$0 \cdot (-\infty)$$. In this case, it is easier to flip $$x$$ into the denominator, because it is easier to take the derivative of $$x^{-1}$$ than it is to take the derivative of $$(\ln x)^{-1}$$. So, we find

$$
\begin{align*}
\lim_{x \rightarrow 0^+} x \ln x &= \lim_{x \rightarrow 0^+} \frac{ \ln x}{x^{-1}},
\end{align*}
$$

which is of the form $$\frac{-\infty}{\infty}$$, so applying L'Hopital's rule gives

$$
\begin{align*}
\lim_{x \rightarrow 0^+} \frac{ \ln x}{x^{-1}} &= \lim_{x \rightarrow 0^+} \frac{x^{-1}}{-x^{-2}}
&= \lim_{x \rightarrow 0^+} -x
&= 0.
\end{align*}
$$
Case: $$\infty^0$$

Another indeterminate form arises when raising one function of $$x$$ to a power which involves another function of $$x$$. Suppose $$\displaystyle \lim_{x \rightarrow a} f(x) = \infty$$ and $$\displaystyle \lim_{x \rightarrow a} g(x) = 0$$. Then what is $$\displaystyle \lim_{x \rightarrow a} f(x)^{g\left(x\right)}$$?

On the one hand, it seems that raising $$\infty$$ to any power should be $$\infty$$. On the other hand, raising anything to the 0th power should be 1. To find what the answer actually is, let

$$
 y = \lim_{x \rightarrow a} f(x)^{g\left(x\right)}, $$

and take the $$\ln$$ of both sides. Now, recall that $$\ln$$ is a continuous function. Therefore, from the rules of limits in the last module, taking $$\ln$$ of a limit is the same as the limit of the $$\ln$$:

$$
\begin{align*}
\ln(y) &= \ln\left(\lim_{x\rightarrow a} f(x)^{g\left(x\right)}\right)
&= \lim_{x \rightarrow a} \ln \left(f(x)^{g\left(x\right)}\right)
&= \lim_{x \rightarrow a} g(x) \ln(f(x))
\end{align*}
$$

(the last step uses the fact that $$\ln(a^b) = b\ln(a)$$$. Now, this is of the form $$0 \cdot \infty$$, which was covered above. Note that when this limit is computed, it is $$\ln(y)$$ which has been found, and so the answer must be exponentiated to find $$y$$, the original limit.

Example Compute $$\displaystyle \lim_{x \rightarrow \infty} x^{1/x}$$. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


This is of the $$\infty^0$$ form. Let $$\displaystyle y = \lim_{x \rightarrow \infty} x^{1/x}$$. Then taking $$\ln$$ gives

$$
\begin{align*}
\ln(y) &= \lim_{x \rightarrow \infty} \ln\left(x^{1/x}\right)
&= \lim_{x \rightarrow \infty} \frac{1}{x}\ln(x)
&= \lim_{x \rightarrow \infty} \frac{\ln x}{x}
&= \lim_{x \rightarrow \infty} \frac{1/x}{1}
&= 0
\end{align*}
$$

(L'Hopital's rule was used in the second to last step). So $$\ln(y) = 0$$, and so $$y = 1$$ is the answer.
Case: $$0^0$$

Consider the limit $$\displaystyle f(x)^{g\left(x\right)}$$, where $$\displaystyle \lim_{x \rightarrow a} f(x) = 0$$ and $$\displaystyle \lim_{x \rightarrow a} g(x) = 0$$. Because $$0^0$$ is not defined, this is another indeterminate form. It can be dealt with as the $$\infty^0$$ case, by first taking $$\ln$$, computing the resulting limit, and then exponentiating.

Example Compute $$\displaystyle \lim_{x \rightarrow 0^+} x^x$$. <button class="toggle" data-box="#box1c">Answer</button>

<div id="box1c" class="answer-hidden"></div>
{: id="box1c" class="answer-hidden"}


Letting $$\displaystyle y = \lim_{x \rightarrow 0^+} x^x$$, and taking logarithms gives

$$
\begin{align*}
\ln y &= \lim_{x \rightarrow 0^+} x \ln x
&= 0,
\end{align*}
$$

by an example above. Thus $$y = e^0 = 1$$.
Limits going to infinity

L'Hopital also works with limits going to infinity; the same hypothesis and conclusions hold. Before doing some examples, what does it mean for $$\displaystyle \lim_{x \rightarrow \infty} f(x) = L$$?

Limit at infinity $$\displaystyle \lim_{x \rightarrow \infty} f(x) = L$$ if and only if for every $$\epsilon>0$$ there exists $$M>0$$ such that $$\vertf(x)-L\vert<\epsilon$$ whenever $$x>M$$. If there is no such $$L$$, then the limit does not exist.

Example Compute $$\displaystyle \lim_{x \rightarrow \infty} \frac{\ln x}{\sqrt{x}}$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Both the numerator and denominator go to $$\infty$$ as $$x \rightarrow \infty$$, so applying L'Hopital's rule gives

$$
\begin{align*}
\lim_{x \rightarrow \infty} \frac{\ln x}{\sqrt{x}} &= \lim_{x \rightarrow \infty} \frac{x^{-1}}{\frac{1}{2}x^{-1/2}}
&= \lim_{x \rightarrow \infty} \frac{2}{\sqrt{x}}
&= 0.
\end{align*}
$$

Example Compute $$\displaystyle \lim_{x \rightarrow \infty} \frac{e^{x}}{x^2}$$. <button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


The numerator and denominator both go to $$\infty$$ as $$x \rightarrow \infty$$, so this is the $$\frac{\infty}{\infty}$$ case of L'Hopital's rule. It follows that $$
\begin{align*}
\lim_{x\rightarrow \infty} \frac{e^x}{x^2} &= \lim_{x\rightarrow \infty} \frac{[e^x]'}{[x^2]'}
&= \lim_{x\rightarrow \infty} \frac{e^x}{2x}
&= \lim_{x \rightarrow \infty} \frac{e^x}{2}
&= \infty.
\end{align*}
$$ Note that L'Hopital's rule was used twice here since $$\lim_{x\rightarrow \infty} \frac{e^x}{2x}$$ is still the $$\frac{\infty}{\infty}$$ case.

While L'Hopital often works, there are situations where it fails to give an answer, and a little extra thought must be employed.

Example Compute $$\displaystyle \lim_{x \rightarrow \infty} \tanh x$$. <button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


Recall that $$\tanh x = \frac{\sinh x}{\cosh x}$$. Both $$\sinh x \rightarrow \infty$$ and $$\cosh x \rightarrow \infty$$ as $$x \rightarrow \infty$$. But applying L'Hopital's rule (and then applying it again) gives

$$
\begin{align*}
\lim_{x \rightarrow \infty} \tanh x &= \lim_{x \rightarrow \infty} \frac{\sinh x}{\cosh x}
&= \lim_{x \rightarrow \infty} \frac{\cosh x}{\sinh x}
&= \lim_{x \rightarrow \infty} \frac{\sinh x}{\cosh x},
\end{align*}
$$

so L'Hopital's rule clearly will not give us an answer here. Instead, writing out the definition of $$\tanh x$$ and doing a little algebra, we find

$$
\begin{align*}
\lim_{x \rightarrow \infty} \tanh x &= \lim_{x \rightarrow \infty} \frac{e^x - e^{-x}}{e^x + e^{-x}}
&= \lim_{x \rightarrow \infty} \frac{e^x(1 - e^{-2x}}{e^x(1 + e^{-2x})}
&= 1.
\end{align*}
$$

Example Compute $$ \displaystyle \lim_{x \rightarrow \infty} \frac{x \ln x}{\ln(\cosh x)}$$. <button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


Using L'Hopital's rule, we find

$$
\begin{align*}
\lim_{x \rightarrow \infty} \frac{ x \ln x}{\ln (\cosh x) } &= \lim_{x \rightarrow \infty} \frac{\frac{x}{x} + 1 \cdot \ln x}{\frac{\sinh x}{\cosh x}}
&= \lim_{x \rightarrow \infty} \frac{1+ \ln x}{\tanh x}
&= \infty,
\end{align*}
$$

since the denominator goes to 1 (from the previous example) and the numerator goes to infinity.

It is also possible to deal with limits going to infinity using Taylor series, but it involves some algebra. The idea is to use a substitution to turn the limit going to infinity into a limit going to zero. Symbolically, if $$x \rightarrow \infty$$, then let $$z = 1/x$$. It follows that $$z \rightarrow 0$$ as $$x \rightarrow \infty$$, and by replacing $$x$$ with $$1/z$$ throughout, the limit is transformed.

$$
\begin{align*}
\lim_{x \rightarrow \infty} f(x) &= \lim_{z \rightarrow 0} f(1/z).
\end{align*}
$$

This process works when the limit at 0 exists. A more general technique would only look at the one-sided limit from the right-hand side:

$$
\begin{align*}
\lim_{x \rightarrow \infty} f(x) &= \lim_{z \rightarrow 0^+} f(1/z).
\end{align*}
$$

Example Compute $$\displaystyle \lim_{x \rightarrow \infty} \frac{\sin(1/x)}{1/x}$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Using the substitution $$z = 1/x$$, the limit becomes

$$
\begin{align*}
\lim_{x \rightarrow \infty} \frac{\sin(1/x)}{1/x} &= \lim_{z \rightarrow 0} \frac{\sin(z)}{z}
&= 1,
\end{align*}
$$ as was shown in the last module.

## Exercises

Compute the following limits. Should you use l'Hopital's rule or Taylor expansion?

$$
\displaystyle \lim_{x \to 2} \frac{x^3+2x^2-4x-8}{x-2} $$

$$
\displaystyle \lim_{x \to \pi/3} \frac{1-2\cos x}{\pi -3x} $$

$$
\displaystyle \lim_{x \to \pi} \frac{4 \sin x \cos x}{\pi - x} $$

$$
\displaystyle \lim_{x \to 9} \frac{2x-18}{\sqrt{x}-3} $$

$$
\lim_{x \to 0} \frac{e^x - \sin x -1}{x^2-x^3} $$

$$
\displaystyle \lim_{x \to 1} \frac{\cos (\pi x/2)}{1 - \sqrt{x}} $$

$$
\displaystyle \lim_{x \to 4} \frac{3 - \sqrt{5+x}}{1 - \sqrt{5-x}} $$

$$
\displaystyle \lim_{x\rightarrow 0} \left(\frac{1}{x}-\frac{1}{\ln (x+1)}\right) $$

$$
\displaystyle \lim_{x \to \pi/2} \frac{\sin x \cos x}{e^x\cos 3x} $$

$$
\displaystyle \lim_{x \rightarrow +\infty} \frac {\ln x}{e^x} $$

$$
\displaystyle \lim_{x \to +\infty} x \ln\left(1+ \frac{3}{x}\right) $$

$$
\displaystyle \lim_{x \to +\infty} \frac{(\ln x)(\sinh x)}{(x-1)e^x} $$ 