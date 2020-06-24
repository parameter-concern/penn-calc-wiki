---
title: Fair probability
description: Uniform distribution
lecture_number: 42
topic_number: 4
layout: lecture
mathjax: true
hidden_answers: true
---
Probability is the study of the likelihood of certain events occurring in a random experiment. A simple example is a coin flip. There are two outcomes: heads (H) or tails (T). If the coin is fair, then the probability of each outcome is $$\frac{1}{2}$$, written $$P(H) = P(T) = \frac{1}{2}$$. Another example is a roll of a standard die. There are six outcomes: 1 through 6. If the die is fair then the probability of each outcome is $$\frac{1}{6}$$.

In these types of problems, one can find the probability of an event occurring by counting the number of desired outcomes and dividing by the total number of outcomes.

**Example**

What is the probability that a pair of dice sums to seven or eleven?

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


By listing the desired outcomes, one finds that $$(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)$$ are the possible pairings which give 7, and $$(6,5)$$ and $$(5,6)$$ are the possible pairings which give 11. So there are 8 desired outcomes. The total number of outcomes is $$6 \times 6$$ (six outcomes for the first die paired with each of the six outcomes for the other die). So the probability is

$$
\frac{\#\hbox{ desired}}{\#\hbox{ total}} = \frac{8}{36} = \frac{2}{9}.
$$

**Example**

Alice and Bob play a game where they take turns flipping a fair coin, with Alice going first. The first player to get heads wins. What is the probability that Alice wins?

Hint: find the probability that Alice wins on her first flip, and the probability that she wins on her second flip, and the probability that she wins on her third flip, etc. Add up all these (infinitely many) probabilities to find the probability that she wins.

Second hint: For Alice to win on her second flip, it means that both Alice and Bob got tails on their respective first flips (otherwise the game would have ended in the first round). So the probability of Alice winning on her second flip is

$$
P(\hbox{A got tails})\cdot P(\hbox{B got tails}) \cdot P(\hbox{A got heads}) = \frac{1}{2}\cdot \frac{1}{2} \cdot \frac{1}{2} = \left(\frac{1}{2}\right)^3.
$$

<button class="toggle" data-box="#box2c">Answer</button>

<div id="box2c" class="answer-hidden"></div>
{: id="box2c" class="answer-hidden"}


Proceeding as the hint suggests, we look for a pattern.

$$
P(\hbox{A wins on 1st flip}) = P(\hbox{A gets heads}) = \frac{1}{2}.
$$

And then

$$
\begin{align*}
& P(\hbox{A wins on 2nd flip})
&= P(\hbox{A gets tails}) \cdot P(\hbox{B gets tails}) \cdot P(\hbox{A gets heads})
&= \frac{1}{2} \cdot \frac{1}{2}\cdot \frac{1}{2}
&= \left(\frac{1}{2}\right)^3.
\end{align*}
$$

Next,

$$
\begin{align*}
& P(\hbox{A wins on 3rd flip})
&= P(\hbox{A gets tails}) \cdot P(\hbox{B gets tails}) \cdot P(\hbox{A gets tails}) \cdot P(\hbox{B gets tails}) \cdot P(\hbox{A gets heads})
&= \frac{1}{2} \cdot \frac{1}{2}\cdot \frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2}
&= \left(\frac{1}{2}\right)^5.
\end{align*}
$$

In general, for Alice to win on the $$n$$th flip, she must get a head on that flip, and both Alice and Bob must have gotten tails on each of their previous $$n-1$$ flips. Thus, there are a total of $$2(n-1) + 1 = 2n-1$$ coin flips that must come out in a precise way, and the probability of each of these is $$\frac{1}{2}$$, so we have

$$
P(\hbox{A wins on $n$th flip}) = \left(\frac{1}{2}\right)^{2n-1}.
$$

Adding these up for all $$n$$, and using the geometric series, gives

$$
\begin{align*}
P(\hbox{A wins}) &= \sum_{n=1}^\infty \left(\frac{1}{2}\right)^{2n-1}
&= \frac{1}{2} + \left(\frac{1}{2}\right)^3 + \left(\frac{1}{2}\right)^5 + \dotsb
&= \frac{1}{2} \cdot \left( 1 + \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^4 + \dotsb \right)
&= \frac{1}{2} \cdot \left(1 + \frac{1}{4} + \left(\frac{1}{4}\right)^2 + \dotsb \right)
&= \frac{1}{2} \cdot \frac{1}{1-1/4}
&= \frac{2}{3}.
\end{align*}
$$

Uniform distribution

The above examples refer to a fair coin and a fair die. A discrete experiment (i.e. the possible outcomes can be listed) is said to have the uniform distribution if the experiment is fair in the sense that every outcome is equally likely.

What about experiments which are not discrete? For instance, a spinner gives a point along the circumference of a circle, and the individual points of the circle cannot be enumerated. Throwing a dart at a circular dartboard likewise has as many outcomes as there are points in the interior of the disk. What does it mean for such an experiment to be fair, i.e., what does the uniform distribution mean in an experiment with continuous outcomes?

To answer this question, consider the probability of a range of outcomes of the experiment. So, for instance, what is the probability of the spinner landing in the first quarter of the circle? If the experiment is fair, then this probability should be the same as landing in any other quarter of the circle: $$\frac{1}{4}$$:

Thus an experiment is fair (i.e. has the uniform distribution) if for any set of outcomes $$D$$,

$$
\begin{equation*} P(D) = \frac{\hbox{volume of $D$}}{\hbox{total volume of all outcomes}}. \end{equation*}
$$

Here "volume" depends on the dimension of the experiment. For instance, the spinner has dimension 1 (where volume is really just the length) since any point on the circumference can be specified by a single value (say, the angle of the arrow relative to the positive $$x$$-axis). So a spinner is considered fair if the probability of the arrow landing in a certain range along the circumference equals the length of that range divided by the total circumference of the circle.
Length

**Example**

Find the probability that a randomly chosen angle $$\theta$$ has $$ \sin \theta>\frac{1}{2}$$?

<button class="toggle" data-box="#box1a">Answer</button>

<div id="box1a" class="answer-hidden"></div>
{: id="box1a" class="answer-hidden"}


We can visualize the sine of the angle by considering a unit circle, and noting that sine is the $$y$$-coordinate of a point on the circle:

Then one finds that the angles for which $$\sin \theta>\frac{1}{2}$$ are

$$
\frac{\pi}{6}< \theta < \frac{5 \pi}{6}.
$$

The length of this portion of the circumference of the circle is $$\frac{4 \pi}{6}$$, and so the probability of a random angle $$\theta$$ satisfying $$\sin \theta > \frac{1}{2}$$ is

$$
\begin{align*}
P &= \frac{4 \pi/6}{2 \pi}
&= \frac{1}{3}.
\end{align*}
$$

**Example**

Find the probability that a randomly chosen angle $$\theta$$ has $$\tan \theta > 0$$.

<button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden"></div>
{: id="box1b" class="answer-hidden"}


Note that tangent is positive when sine and cosine have the same sign, i.e. if sine and cosine are both positive or if sine and cosine are both negative. This corresponds to the first and third quadrants of the unit circle:

The length of each these arcs is $$\frac{\pi}{2}$$, and so the probability that $$\tan \theta > 0$$ is

$$
\begin{align*}
P &= \frac{2 \cdot \pi/2}{2 \pi}
&= \frac{1}{2}
\end{align*}
$$

Area

In two dimensions, volume is really area, and so when computing the probability that a randomly chosen point in a region $$R$$ in the plane lies within the region $$D$$, we have

$$
P = \frac{\hbox{Area of $D$}}{\hbox{Area of $R$}}.
$$

**Example**

A dartboard is circular with radius 9 inches:

The bullseye is a small circle at the center of the board. Find the radius of the bullseye so that the probability of hitting it is $$\frac{1}{100}$$ (assuming a throw hits the board uniformly at random).

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Ignoring the unnecessary detail of the dartboard, let the radius of the bull's eye be $$r$$. Then

$$
\begin{align*}
P\left((\hbox{ bullseye }\right) &= \frac{A(\hbox{ bullseye })}{A(\hbox{ board })}
&= \frac{\pi r^2}{\pi \cdot 9^2}
&= \frac{r^2}{81}.
\end{align*}
$$

Setting equal to $$\frac{1}{100}$$ and solving gives $$r = 0.9$$ inches. (In reality, the bullseye is much smaller, but the numbers worked out nicer in this example).

**Example**

Find the probability that a randomly chosen point in a square lies within the circle inscribed in the square:

<button class="toggle" data-box="#box1c">Answer</button>

<div id="box1c" class="answer-hidden"></div>
{: id="box1c" class="answer-hidden"}


If the radius of the circle is $$r$$, then the side length of the square is $$2r$$. Thus, the area of the circle is $$\pi r^2$$ and the area of the square is $$(2r)^2 = 4r^2$$. And so the probability that a point chosen at random within the square also lies within the circle is

$$
\begin{align*}
P &= \frac{\pi r^2}{4r^2}
&= \frac{\pi}{4}.
\end{align*}
$$

**Example**

Find the probability that a randomly chosen point in a circle lies in the equilateral triangle inscribed in the circle:

Hint: the area of an equilateral triangle of side length $$s$$ is

$$
A = \frac{s^2 \sqrt{3}}{4}.
$$

<button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


By doing a little bit of right triangle trigonometry:

we find that the side length of the triangle is

$$
s = r \sqrt{3}.
$$

Therefore, the area of the triangle is

$$
\begin{align*}
A &= \frac{s^2 \sqrt{3}}{4}
&= \frac{3 r^2 \sqrt{3}}{4}.
\end{align*}
$$

And so the probability of a point within the circle being within the triangle is the ratio of the areas:

$$
\begin{align*}
\frac{\hbox{Area of triangle}}{\hbox{Area of circle}} &= \frac{1}{\pi r^2} \frac{3r^2 \sqrt{3}}{4}
&= \frac{3 \sqrt{3}}{ 4 \pi}
\end{align*}
$$

There are some probability problems that do not seem geometric in nature but can be solved by graphing the possible outcomes and taking the ratio of the areas.

**Example**

Xander and Yolanda want to meet up to study calculus. Each friend will arrive at the library at some random time between 5 pm and 6pm, wait 20 minutes for the other person, and then leave if the other person does not arrive in that time. Find the probability that the friends successfully meet up.

Hint: Let $$x$$ be the number of minutes after 5 pm that Xander arrives and $$y$$ be the number of minutes after 5 pm that Yolanda arrives. Now plot the possible arrival times as a region in the plane and determine the region which corresponds to them successfully meeting up.

<button class="toggle" data-box="#box2a">Answer</button>

<div id="box2a" class="answer-hidden"></div>
{: id="box2a" class="answer-hidden"}


The possible outcomes form a square for $$0 \leq x \leq 60$$ and $$0 \leq y \leq 60$$. For the friends to meet, we must have that Yolanda arrives no later than 20 minutes after Xander and that Xander arrives no later than 20 minutes after Yolanda arrives. Mathematically,

$$
\begin{align*}
y & \leq x + 20
x & \leq y + 20
\end{align*}
$$

The two will successfully meet if and only if these two conditions are met. Graphing these inequalities, the points they have in common are shown below in dark blue:

So the probability of them meeting is the area of the dark blue region divided by the total area of the square. It is easier to determine the area of the region we do not want and subtract. There are two isosceles right triangles of side length 40, so the area of the region we do not want is

$$
\hbox{bad area } = 2 \cdot \frac{1}{2} \cdot 40 \cdot 40 = 1600
$$

Therefore, the probability of the friends meeting is

$$
\begin{align*}
P &= \frac{\hbox{area of dark blue region}}{\hbox{total area}}
&= \frac{\hbox{total area} - \hbox{light blue area}}{\hbox{total area}}
&= \frac{3600 - 1600}{3600}
&= \frac{2000}{3600}
&= \frac{5}{9}.
\end{align*}
$$

Volume

Finally, in dimension 3, volume is volume as we traditionally know it. In this case, we imagine picking a point from within a 3D region and know the probability that the point lies within some subset of that region.

**Example**

Find the probability that a randomly chosen point from within a cube lies within the inscribed sphere:

<button class="toggle" data-box="#box2b">Answer</button>

<div id="box2b" class="answer-hidden"></div>
{: id="box2b" class="answer-hidden"}


If $$r$$ is the radius of the inscribed sphere, then the side length of the cube is $$2r$$. Therefore, the volume of the sphere is $$\frac{4}{3}\pi r^3$$ and the volume of the cube is $$(2r)^3 = 8r^3$$. So the probability that a random point within in the cube lies within the sphere is

$$
\begin{align*}
P &= \frac{(4/3)\pi r^3}{8r^3}
&= \frac{\pi}{6}.
\end{align*}
$$

**Example**

What is the probability that a randomly chosen point in a ball lies within 10% of the boundary (as measured by radius)?

<button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Let $$r$$ be the radius of the ball. Then the volume of the ball (the volume of all the possible outcomes) is $$\frac{4}{3}\pi r^3$$.

To find the volume of the desired outcomes, consider the volume of the undesired outcomes: those points which lie within 90% of the center. These points form a ball of radius $$\frac{9}{10}r$$, hence their volume is $$\frac{4}{3}\pi \left(\frac{9}{10}r\right)^3$$. So the desirable outcomes have the complementary volume

$$
\begin{align*}
\hbox{ volume of desired outcomes} &= \hbox{ total volume} - \hbox{ volume of undesired outcomes}
&= \frac{4}{3} \pi r^3 - \frac{4}{3} \pi (\frac{9}{10}r)^3
&= \frac{4}{3} \pi r^3 \left(1-(9/10)^3\right).
\end{align*}
$$

Thus, the probability of a point being within 10% of the boundary is

$$
\begin{align*}
\frac{\hbox{ volume of desired outcomes}}{\hbox{ total volume}} &= \frac{\frac{4}{3}\pi r^3(1-(9/10)^3)}{\frac{4}{3}\pi r^3}
&= 1-(9/10)^3
&= 0.271
\end{align*}
$$

Buffon needle problem

The Buffon needle problem, named after the Count of Buffon, asks for the probability that a needle of length $$l$$, dropped uniformly at random onto a sheet with parallel lines spaced $$l$$ units apart, will cross a line.

To simplify the problem, consider two parameters which determine whether the needle crosses:

- $$h$$, the distance from the left tip of the needle to the next line to its right
- $$\theta$$, the angle that the needle makes with a vertical line: 

Note that $$0 \leq h \leq l$$ and $$0 \leq \theta \leq \pi$$. Now, for what values of $$h$$ and $$\theta$$ is there a crossing? Note that by right triangle trigonometry, the horizontal distance from the left end of the needle to the right end of the needle is $$l \sin \theta$$:

Thus, there is a crossing if $$h \leq l \sin \theta$$, and there is no crossing if $$h > l \sin \theta$$. Graphing this inequality shows that the region below the curve (shown in purple) is where a crossing occurs. The region above the curve is where a crossing does not occur.

Dropping a needle at random is like randomly picking a point in this rectangle. Thus, the probability of a random needle creating a crossing equals the probability of randomly picking a point below the curve in the above rectangle. That probability is given by dividing the area under the curve by the area of the entire rectangle.

$$
\begin{align*}
P(\hbox{crossing}) &= \frac{\int_0^\pi l\sin \theta \, d\theta}{l\pi}
&= \frac{1}{\pi} \left( -\cos \theta \bigg\vert^\pi_0 \right)
&= \frac{2}{\pi}.
\end{align*}
$$

