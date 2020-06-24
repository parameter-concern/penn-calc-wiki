---
title: Linearization
description: First order Taylor approximations
lecture_number: 12
topic_number: 2
layout: lecture
mathjax: true
hidden_answers: true
---
One of the main uses of the derivative is linearization, which uses the first two terms (the constant and linear term) of the Taylor series as an approximation. In many applications, this gives a very good approximation, as we will see in some examples.
Linear variation visualized

There are several geometric examples where it is possible to see the linear variation as the change in area as a parameter is changed by a small amount.
Square

The area of a square of side length $$x$$ is given by $$A(x) = x^2$$. When that is varied by a small amount $$h$$, the result is

$$
A(x+h) = (x+h)^2 = x^2+2xh+h^2.
$$

The linear variation is $$2xh$$, which can be seen in the diagram as the rectangles along the right and top edges of the square. There are two of them, each with area $$xh$$. The final bit of area, the purple square in the diagram, has area $$h^2$$, which is higher order.
Triangle

The area of a right triangle with legs length $$x$$ is $$A(x) = \frac{1}{2}x^2$$. When the leg is varied by $$h$$, the result is

$$
A(x+h) = \frac{1}{2}x^2 + xh + \frac{1}{2}h^2.
$$

Visually, the linear variation $$xh$$ comes from the red parallelogram, of base $$h$$ and height $$x$$, running along the hypotenuse. The higher order term $$\frac{1}{2}h^2$$ comes from the small purple triangle at the tip of the triangle.
Disc

The area of a disc of radius $$x$$ is $$A(x) = \pi x^2$$. If the radius is increased by $$h$$, the result is

$$
A(x+h) = \pi (x+h)^2 = \pi x^2 + 2\pi x h + \pi h^2.
$$

Visually breaking this into the linear variation and higher order variation is a little bit harder. The best way is to imagine taking the ring formed by the increased radius and breaking it into rectangles and wedges. In the limit, the wedges can be rearranged into a disc of radius $$h$$, and the rectangles can be arranged to form a strip of length $$2\pi x$$ (the circumference of the inner circle) and width $$h$$.
Linear approximation

The equation underlying any linear approximation should be familiar, since it is just the first order Taylor series about $$x=a$$, after making the substitution $$h = x-a$$:

$$
f(a+h) \approx f(a) + f'(a)h.
$$

This will be a good linear approximation provided that $$h$$ is small, i.e., the point $$a$$ is close to the input we are trying to approximate. In general, one wants to pick $$a$$ to be an input where it is easy to compute $$f(a)$$ and $$f'(a)$$ which is as close to the desired input as possible.

**Example**

Using a linear approximation, estimate $$\sqrt{250}$$. <button class="toggle" data-box="#box0">Answer</button>

<div id="box0" class="answer-hidden"></div>
{: id="box0" class="answer-hidden"}


The function here is $$f(x) = \sqrt{x}$$. Possible choices for $$a$$ are perfect squares, because it is easy to compute the square root of squares. The nearest perfect square is $$256 = 16^2$$, so we choose $$a = 256$$. Thus, $$h = x-a = -6$$. Then

$$
\begin{align*}
f(x) &\approx f(a) + f'(a)h
\sqrt{ 250 } &\approx \sqrt{256} + \frac{1}{2\sqrt{256}}(-6)
&= 16 - \frac{6}{32}
&= 15 \frac{13}{16}
& \approx 15.8,
\end{align*}
$$

which is very close to the calculator's answer of $$15.811 \ldots $$.

**Example**

Using a linear approximation, estimate $$\sqrt{104}$$. Is this an over-approximation or an under-approximation? <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


As above, $$a=100$$ is the closest point where it is easy to compute $$\sqrt{x}$$ and derivatives. Then $$h = 4$$, so the linear approximation is

$$
\begin{align*}
f(a + h) &\approx f(a) + f'(a)h
&= \sqrt{100} + \frac{1}{2\sqrt{100}} \cdot 4
&= 10 + \frac{4}{20}
&= 10.2.
\end{align*}
$$

This is an over-approximation. One way to see why is to consider the graph of $$\sqrt{x}$$, which is concave down, so the linear approximation is above the true value. Another argument is to consider the next term of the Taylor series, which is negative (since the second derivative of $$\sqrt{x}$$ is negative).

For comparison, the value according to a calculator is $$\sqrt{104} \approx 10.198$$.

**Example**

Approximate $$\pi^{20}$$. Hint: $$\pi^2 \approx 9.86$$. <button class="toggle" data-box="#box1a">Answer</button>

<div id="box1a" class="answer-hidden"></div>
{: id="box1a" class="answer-hidden"}


From the hint, $$\pi^{20} = (\pi^2)^{10} \approx 9.86^{10}$$. Thus, we are trying to approximate $$f(x) = x^{10}$$ at $$x = 9.86$$. The nearest easy input is $$a = 10$$, so we find

$$
\begin{align*}
f(9.86) &\approx f(10) + f'(10)(-.14)
&= 10^{10} + 10 (10)^9 (-.14)
&= 10^{10} \left(1-.14 \right)
&= 8.6 \cdot 10^9.
\end{align*}
$$

The true answer is approximately $$8.77 \cdot 10^9$$, so this estimate is within 2%.

**Example**

Approximate $$e^{30}$$. Hint: $$e^{3} \approx 20.1$$, and $$2^{10} \approx 1000$$. <button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


From the first hint, $$e^{30} = (e^3)^{10} \approx (20.1)^{10}$$, so consider the linear approximation for $$f(x) = x^{10}$$ near $$a=20$$:

$$
\begin{align*}
f(x) & \approx f(20) + f'(20)(x-20)
x^{10} &\approx 20^{10} + 10 \cdot 20^9 (x-20)
\end{align*}
$$

So it follows that

$$
\begin{align*}
e^{30} & \approx (20.1)^{10}
& \approx 20^{10} + 10 \cdot 20^9 \cdot (.1)
& \approx 20^{10}\left[1+(.5)(.1)\right]
& \approx 2^{10} \cdot 10^{10} \cdot 1.05
& \approx 1.05 \cdot 10^{13}
\end{align*}
$$

(the last step used the second hint that $$2^{10} \approx 10^3$$). The true answer is approximately $$e^{30} \approx 1.068 \cdot 10^{13}$$, so the error is less than 2%.
Newton's method

Another application of linearization gives a way of approximating the root of a function. This is called Newton's method.

Given a continuous, differentiable function $$f$$, the goal is to find a root (i.e. a value $$a$$ such that $$f(a)=0$$). Suppose $$x$$ is an initial guess of a root. Then $$x+h$$ will be a root for some small value of $$h$$. Linearizing, and ignoring the higher order terms, gives

$$
\begin{align*}
f(x+h) &= f(x) + f'(x)h + O(h^2)
&\approx f(x) + f'(x)h.
\end{align*}
$$

Since we supposed that $$x+h$$ was a root of $$f$$, it follows that $$f(x+h)=0$$. Therefore, setting the above equal to 0 and solving for $$h$$ gives

$$
f(x) + f'(x)h = 0 \quad \Rightarrow \quad h = -\frac{f(x)}{f'(x)}.
$$

Thus, an even closer guess of a root is

$$
x + h = x - \frac{f(x)}{f'(x)}.
$$

By taking this new guess of a root, and repeating the above process, one (hopefully) gets a better and better approximation of a root.

More formally, this is what is called a difference equation. Given an initial guess, called $$x_0$$, of a root of the function, one uses the update rule

$$
\begin{equation*} x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)} \end{equation*}
$$

to get $$x_1$$, and then $$x_2$$, and so on.

The resulting sequence hopefully converges to a root of $$f$$. Graphically, what is happening is as follows:

- Pick a guess $$x_0$$.
- Find the tangent line to $$f$$ through the point $$(x_0,f(x_0))$$.
- Let $$x_1$$ be the point where the tangent line intersects the $$x$$-axis.
- Repeat steps 2 and 3 (see the figure). 

Caveat

This sequence is only defined if $$f'(x_n)$$ exists and is non-zero for every $$x_n$$ in the sequence. Even if the sequence is defined, it may not converge to anything. But if the sequence is defined and it does converge, say to $$L$$, then $$L$$ is a root of $$f$$.

**Example**

Find the update rule for approximating $$\frac{1}{a}$$, the reciprocal of a number $$a$$. <button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


First, we must find a function which has $$\frac{1}{a}$$ as a root. We might try $$f(x) = x-\frac{1}{a}$$, but unfortunately (after a little algebra) this leads to the update rule

$$
x_{n+1} = \frac{1}{a},
$$

which is not particularly helpful, since that is the quantity we are trying to approximate.

Another try would be $$f(x) = a- \frac{1}{x}$$. This will work. Note that $$f'(x) = \frac{1}{x^2}$$, so the update rule is

$$
\begin{align*}
x_{n+1} &= x_n - \frac{f(x_n)}{f'(x_n)}
&= x_n - \frac{a-\frac{1}{x_n}}{\frac{1}{x_n^2}}
&= x_n - \left(x_n^2 a - x_n\right)
&= 2x_n - a x_n^2.
\end{align*}
$$

Note that this rule does not involve division, but only multiplication and subtraction.

**Example**

Find the update rule for using Newton's method to approximate $$\sqrt{a}$$. Use the update rule twice with initial guess $$x_0 = 3$$ to estimate $$\sqrt{11}$$. <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


The first step is to find a function whose root is $$\sqrt{a}$$. A good choice is $$f(x) = x^2-a$$. Then according to Newton's method, the update rule is

$$
\begin{align*}
x_{n+1} &= x_n - \frac{f(x_n)}{f'(x_n)}
&= x_n - \frac{x_n^2-a}{2x_n}
&= x_n - \frac{x_n}{2} + \frac{a}{2x_n}
&= \frac{x_n}{2} + \frac{a}{2x_n}.
\end{align*}
$$

Using the update rule with $$x_0 = 3$$ and $$a = 11$$ gives

$$
\begin{align*}
x_1 &= \frac{x_0}{2} + \frac{11}{2x_0}
&= \frac{3}{2} + \frac{11}{6}
&= \frac{20}{6}
&= \frac{10}{3}
\end{align*}
$$

Updating one more time gives

$$
\begin{align*}
x_2 &= \frac{x_1}{2} + \frac{11}{2x_1}
&= \frac{5}{3} + \frac{11}{\frac{20}{3}}
&= \frac{199}{60}
& \approx 3.3166
\end{align*}
$$

The calculator gives that $$\sqrt{11} \approx 3.3166$$, so we get a good approximation with only a little bit of work. One could repeat the update rule several more times to get an even better approximation.

**Example**

Find the update rule for finding $$\sqrt[3]{a}$$. Use the update rule once with the initial guess of $$x_0 = 5$$ to estimate $$\sqrt[3]{100}$$. <button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


The function in this case is $$f(x) = x^3-a$$. Then $$f'(x) = 3x^2$$, and so the update rule is

$$
\begin{align*}
x_{n+1} &= x_n - \frac{f(x_n)}{f'(x_n)}
&= x_n - \frac{x_n^3-a}{3x_n^2}
&= x_n - \frac{1}{3}x_n + \frac{a}{3x_n^2}
&= \frac{2}{3}x_n + \frac{a}{3x_n^2}.
\end{align*}
$$

Using this to estimate $$\sqrt[3]{100}$$ with the initial guess $$x_0 = 5$$, one finds

$$
\begin{align*}
x_1 &= \frac{2}{3}\cdot x_0 + \frac{100}{3 x_0^2}
&= \frac{10}{3} + \frac{4}{3}
&= \frac{14}{3}
& \approx 4.666
\end{align*}
$$

If we compare this to the answer from a calculator, we find that $$\sqrt[3]{100} \approx 4.64$$, and so even after just one step, we are within 1% of the true answer.

## Exercises

- Use a linear approximation to estimate $$\sqrt[3]{67}$$. Round your answer to four decimal places. Hint: what is $$4^3$$?
- Use a linear approximation to estimate the cosine of an angle of $$66^\mathrm{o}$$. Round your answer to four decimal places. Hint: remember that $$\displaystyle 60^\mathrm{o} = \frac{\pi}{3}$$, and hence $$\displaystyle 6^\mathrm{o} = \frac{\pi}{30}$$.
- Use Newton's method to determine the intersection of $$e^{-x}$$ and $$x$$.
- The golden ratio $$\displaystyle \varphi = \frac{1+\sqrt{5}}{2}$$ is a root of the polynomial $$x^2-x-1$$. If you use Newton's method to estimate its value, what is the appropriate update rule for the sequence $$x_n$$ ?
- To approximate $$\sqrt{10}$$ using Newton's method, what is the appropriate update rule for the sequence $$x_n$$ ?
- You want to build a square pen for your new chickens, with an area of $$1200\,\mathrm{ft}^2$$. Not having a calculator handy, you decide to use Newton's method to approximate the length of one side of the fence. If your first guess is $$30\,\mathrm{ft}$$, what is the next approximation you will get?
- You are in charge of designing packaging materials for your company's new product. The marketing department tells you that you must put them in a cube-shaped box. The engineering department says that you will need a box with a volume of $$500\,\mathrm{cm}^3$$. What are the dimensions of the cubical box? Starting with a guess of $$8\,\mathrm{cm}$$ for the length of the side of the cube, what approximation does one iteration of Newton's method give you? Round your answer to two decimal places.
- Without using a calculator, approximate $$9.98^{98}$$. Here are some hints. First, $$9.98$$ is close to $$10$$, and $$10^{98}=1\,{\rm E}\,98$$ in scientific notation. What does linear approximation give as an estimate when we decrease from $$10^{98}$$ to $$9.98^{98}$$?
- A diving-board of length $$L$$ bends under the weight of a diver standing on its edge. The free end of the board moves down a distance $$D = PL^3/3EI $$ where $$P$$ is the weight of the diver, $$E$$ is a constant of elasticity (that depends on the material from which the board is manufactured), and $$I$$ is a moment of inertia. (These last two quantities will again make an appearance in Lectures 13 and 41, but do not worry about what exactly they mean now...) Suppose our board has a length $$L = 2\,\mathrm{m}$$, and that it takes a deflection of $$D = 20\,\mathrm{cm}$$ under the weight of the diver. Use a linear approximation to estimate the deflection that it would take if its length was increased by $$20\,\mathrm{cm}$$. 