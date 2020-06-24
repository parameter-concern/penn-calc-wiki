---
title: Differentials
description: Implicit differentiation and related rates
lecture_number: 15
topic_number: 2
layout: lecture
mathjax: true
hidden_answers: true
---
This module deals with differentials, e.g. $$dx$$ or $$du$$. A formal treatment of differential forms is beyond the scope of this course. For now, the best way to think about the differential $$dx$$ or $$du$$ is to think of them as rates of change, and relate them with the chain rule:

$$
\begin{equation*} du = \frac{du}{dx}dx. \end{equation*}
$$

In words, the rate of change of $$u$$ equals the rate of change of $$u$$ with respect to $$x$$ times the rate of change of $$x$$. This is not a perfect interpretation, but it will serve our purposes for this course.
The differential as an operator

Think of the differential $$d$$ as an operator which can be applied to an equation $$f=g$$ to give back $$df = dg$$. This process allows one to find the derivative of functions which are defined implicitly, i.e., functions which cannot be "solved for $$y$$" as $$y=f(x)$$. This method is called implicit differentiation.

**Example**

Find $$\frac{dy}{dx}$$ of the circle $$x^2+y^2=r^2$$.

<button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


Taking the differential (remembering the chain rule) and doing some algebra gives

$$
\begin{align*}
2x(dx) + 2y(dy) &= 0
2y(dy) &= -2x(dx)
\frac{dy}{dx} &= \frac{-2x}{2y}
&= -\frac{x}{y}.
\end{align*}
$$

So $$\frac{dy}{dx} = -\frac{x}{y}$$.

**Example**

In economics, the marginal rate of substitution (MRS) of X for Y is the rate at which a consumer is willing to exchange good Y for good X to maintain an equal level of satisfaction (called utility in economics jargon).

Let $$U(X,Y)$$ denote a particular consumer's utility function. As a particular example, let X be coffee, in ounces, and Y be doughnuts. Then the curve $$U(X,Y) = C$$ represents all the different combinations of coffee and doughnuts where the consumer is equally happy. For example, if the utility function is

$$
U(X,Y) = Y^2(X-3),
$$

then the following shows the graph of the curve $$U(X,Y) = 4$$. The two plotted points show that this consumer is equally satisfied with 4 ounces of coffee and 2 doughnuts as with 7 ounces of coffee and 1 doughnut.

The MRS, then, is the rate of exchange of Y for X (doughnuts for coffee) so that utility stays the same (i.e. we stay on the curve). Mathematically, this is

$$
\hbox{MRS} = -\frac{dY}{dX}.
$$

Find MRS for the utility function given above, $$U(X,Y) = Y^2(X-3)$$. Then calculate the MRS at the points $$(4,2)$$ and $$(7,1)$$ and interpret the results. <button class="toggle" data-box="#box1b">Answer</button>

<div id="box1b" class="answer-hidden"></div>
{: id="box1b" class="answer-hidden"}


Using implicit differentiation, we find

$$
\begin{align*}
Y^2(X-3) &= C
2Y\, dY \,(X-3) + Y^2 \, dX &= 0.
\end{align*}
$$

Now solving for $$-\frac{dY}{dX}$$ we find

$$
\hbox{MRS} = -\frac{dY}{dX} = \frac{Y^2}{2Y(X-3)} = \frac{Y}{2(X-3)}.
$$

Evaluating at $$(4,2)$$ gives a MRS of 1, which means that at that point the consumer is willing to substitute 1 doughnut for an ounce of coffee. At $$(7,1)$$ the MRS is $$\frac{1}{8}$$, which means that the consumer is only willing to give up $$\frac{1}{8}$$ of a doughnut for an additional ounce of coffee.

In a sense the MRS is a measure of how a consumer reacts to the scarcity of one good relative to another and how that affects her willingness to exchange the goods.

**Example**

Find the derivative of the function $$y=f(x)$$ defined implicitly by the equation

$$
\begin{equation*} ye^x+x\ln(y) = e. \end{equation*}
$$

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Taking the differential (remembering the product rule) gives

$$
\begin{equation*} (dy)e^x+y(e^xdx)+(dx)\ln(y) + x\left(\frac{1}{y}dy\right)= 0. \end{equation*}
$$

Ultimately, the goal is to solve for $$\frac{dy}{dx}$$, so collecting all the terms with $$dy$$ on the left and the terms with $$dx$$ on the right gives

$$
\begin{equation*} \left(e^x+\frac{x}{y}\right)dy = \left(-ye^x-\ln(y)\right)dx. \end{equation*}
$$

Finally, dividing through gives

$$
\begin{equation*} \frac{dy}{dx} = \frac{-ye^x-\ln(y)}{e^x+x/y}. \end{equation*}
$$

Related rates

The differential is often used in related rates problems. A related rates problem typically has a physical description and asks for the rate at which some quantity is changing. The description must be translated into an implicit relation between the variables involved, and then implicit differentiation is used to find the desired derivative.

**Example**

Suppose a 10 foot ladder is leaning against a wall. The base of the ladder starts sliding away from the wall at a rate of 4 feet per second. At the moment when the base of the ladder is 6 feet away from the wall, at what rate is the top of the ladder sliding down the wall? <button class="toggle" data-box="#box3">Answer</button>

<div id="box3" class="answer-hidden"></div>
{: id="box3" class="answer-hidden"}


Let $$x$$ be the distance from the base of the ladder to the wall and $$y$$ be the distance from the top of the ladder to the floor. Then by the Pythagorean theorem, $$x^2+y^2 = 10^2$$. At the moment in question, $$x=6$$ so $$y=8$$.

The differential of this equation gives

$$
\begin{equation*} 2xdx+2ydy = 0, \end{equation*}
$$

and solving for $$\frac{dy}{dx}$$ gives $$\frac{dy}{dx} = -\frac{x}{y} = -\frac{6}{8} = -\frac{3}{4}$$. But the question asked for $$\frac{dy}{dt}$$, not $$\frac{dy}{dx}$$. But by the Chain rule,

$$
\begin{equation*} \frac{dy}{dt} = \frac{dy}{dx}\cdot \frac{dx}{dt}. \end{equation*}
$$

Since $$\frac{dy}{dx} = -\frac{3}{4}$$ and $$\frac{dx}{dt} = 4$$ (given in the problem), it follows that

$$
\begin{equation*} \frac{dy}{dt} = \frac{dy}{dx}\cdot \frac{dx}{dt} = \left(-\frac{3}{4}\right) \cdot 4 = -3. \end{equation*}
$$

So the top of the ladder is sliding down the wall at a rate of 3 feet per second.

**Example**

Consider the shape of a stream of water as it flows from a faucet. The stream has a circular cross-section which gets narrower lower in the stream, and the goal is to find how the radius of that cross-section is changing with respect to time.

Assume on the one hand that the water is flowing at a constant rate $$C$$. On the other hand, the area of the cross section times the velocity through that cross section equals the flow:

Dividing by $$\pi$$ and taking the differential gives

$$
\begin{align*}
r^2 v &= C
2r \, dr \, v + r^2 \, dv &= 0
dr &= -\frac{r^2}{2rv} \, dv = -\frac{r}{2v} \, dv.
\end{align*}
$$

So $$
\frac{dr}{dv} = -\frac{r}{2v}.
$$

Now, using the chain rule and a few facts from physics gives that

$$
\begin{align*}
\frac{dr}{dt} &= \frac{dr}{dv} \frac{dv}{dt}
&= -\frac{r}{2v} \frac{dv}{dt}
&= -\frac{rg}{2v}
&= -\frac{rg}{2(v_0 + gt)}.
\end{align*}
$$

This is known as a differential equation (in particular, a separable differential equation). One can solve this equation to get an explicit expression for $$r$$ in terms of $$t$$; see the module on separable differential equations.
Relative rates of change

We can normalize the differential $$ du $$ by dividing by $$u$$. This gives $$\frac{du}{u}$$. This is known as the relative rate of change. Note that

$$
\frac{du}{u} = d(\ln u).
$$

**Example**

For a given resistor in an electrical circuit, Ohm's law says that

$$
V = IR,
$$

where $$V$$ is voltage across the resistor, $$I$$ is the current, and $$R$$ is the resistance of the resistor. If the voltage across a variable resistor is fixed, find the relationship between the relative rates change of resistance and current. <button class="toggle" data-box="#box4">Answer</button>

<div id="box4" class="answer-hidden"></div>
{: id="box4" class="answer-hidden"}


Beginning with Ohm's law and taking the differential gives

$$
\begin{align*}
V &= IR
dV &= R \, dI + I \, dR.
\end{align*}
$$

Now, note that $$dV = 0$$ since voltage was assumed to be constant. Then dividing through by $$IR$$ gives

$$
\begin{align*}
R \, dI + I \, dR &= 0
\frac{R \, dI}{IR} + \frac{I \, dR}{IR} &= 0
\frac{dI}{I} + \frac{dR}{R} &= 0
\frac{dI}{I} = -\frac{dR}{R}.
\end{align*}
$$

Thus, the relative rates of change of resistance and current are equal and opposite.

**Example**

In a geometric solid (say, a sphere or a cube), how does the relative rate of change in volume compare to that of surface area?

<button class="toggle" data-box="#box5">Answer</button>

<div id="box5" class="answer-hidden"></div>
{: id="box5" class="answer-hidden"}


For a sphere of radius $$r$$, the volume and area (and their differentials) are

$$
\begin{align*}
V &= \frac{4}{3}\pi r^3 & dV &= 4\pi r^2 \, dr
A &= 4\pi r^2 & dA &= 8\pi r \, dr.
\end{align*}
$$

Then the relative rates of change of volume and area are

$$
\begin{align*}
\frac{dV}{V} &= \frac{4\pi r^2 \, dr}{\frac{4}{3}\pi r^3}
&= 3 \frac{dr}{r}.
\end{align*}
$$

and

$$
\begin{align*}
\frac{dA}{A} &= \frac{8 \pi r \, dr}{4 \pi r^2}
&= 2 \frac{dr}{r}.
\end{align*}
$$

Thus, the relative rate of change of volume is $$\frac{3}{2}$$ that of area. Written another way,

$$
\frac{dV/V}{dA/A} = \frac{3}{2}.
$$

For a cube of side length $$s$$, it turns out the same holds. The volume and area are

$$
\begin{align*}
V &= s^3 & dV &= 3s^2 \, ds
A &= 6 s^2 & dA &= 12 s \, ds.
\end{align*}
$$

The relative rates are $$\frac{dV}{V} = 3 \frac{ds}{s}$$ and $$\frac{dA}{A} = 2 \frac{ds}{s}$$, so once again

$$
\frac{dV/V}{dA/A} = \frac{3}{2}.
$$

**Example**

In economics, the demand curve for a good is the quantity $$Q$$ of the good that a consumer would purchase as a function of the price $$P$$ of the good. The demand curve slopes downward since a consumer will typically buy less of a good if it is more expensive (the exception being a Giffen good).

The price elasticity of demand, $$E$$, for a good is the rate of change of relative quantity fluctuation with respect to relative price fluctuation. Informally, it can be thought of as the percent change in quantity resulting from a percent change in price. One can also think of $$E$$ as a measure of how price sensitive a consumer is for that good at that price. Mathematically,

$$
E = -\frac{dQ/Q}{dP/P}.
$$

The negative sign is there to force elasticity to be positive (without it, $$\frac{dQ/Q}{dP/P}$$ would always be negative due to the downward slope of the demand curve).

A good is said to be elastic at a certain price if $$E>1$$ (that is, a consumer is highly sensitive to price changes). A good is inelastic at a certain price if $$E<1$$. An example of an elastic good is wine, since a small increase in the relative price of wine can result in a consumer substituting a different alcohol for it. An example of an inelastic good is toilet paper, since regardless of price changes, a consumer is likely to require about the same amount of toilet paper:

Revenue, $$R$$, is given by $$R = P \cdot Q$$. How does one maximize the relative revenue with respect to relative change in price?

## Exercises

- Use implicit differentiation to find $$\displaystyle \frac{dy}{dx}$$ from the equation $$y^2 - y = \sin 2x$$.
- Find the derivative $$\displaystyle \frac{dy}{dx}$$ if $$x$$ and $$y$$ are related through $$xy = e^y$$.
- Use implicit differentiation to find $$\displaystyle \frac{dy}{dx}$$ if $$\sin x = e^{-y\cos x}$$.
- Find the derivative $$\displaystyle \frac{dy}{dx}$$ from the equation $$x\tan y - y^2\ln x = 4$$.
- Model a hailstone as a round ball of radius $$R$$. As the hailstone falls from the sky, its radius increases at a constant rate $$C$$. At what rate does the volume $$V$$ of the hailstone change?
- The volume of a cubic box of side-length $$L$$ is $$V = L^3$$. How are the relative rates of change of $$L$$ and $$V$$ related?
- Consider a box of height $$h$$ with a square base of side length $$L$$. Assume that $$L$$ is increasing at a rate of $$10\% $$ per day, but $$h$$ is decreasing at a rate of $$10\% $$ per day. Use a linear approximation to find at what (approximate) rate the volume of the box changing. "Hint:" consider the relative rate of change of the volume of the box.
- A large tank of oil is slowly leaking oil into a containment tank surrounding it. The oil tank is a vertical cylinder with a diameter of 10 meters. The containment tank has a square base with side length of 15 meters and tall vertical walls. The bottom of the oil tank and the bottom of the containment tank are concentric (the round base inside the square base). Denote by $$h_o$$ the height of the oil inside of the oil tank, and by $$h_c$$ the height of the oil in the containment tank. How are the rates of change of these two quantities related?
- The "stopping distance" $$D_\mathrm{stop}$$ is the distance traveled by a vehicle from the moment the driver becomes aware of an obstacle in the road until the car stops completely. This occurs in two phases. 

(1) The first one, the "reaction phase", spans from the moment the driver sees the obstacle until he or she has completely depressed the brake pedal. This entails taking the decision to stop the vehicle, lifting the foot from the gas pedal and onto the brake pedal, and pressing the latter down its full distance to obtain maximum braking power. The amount of time necessary to do all this is called the "reaction time" $$t_\mathrm{react}$$, and is independent of the speed at which the vehicle was traveling. Although this quantity varies from driver to driver, it is typically between $$1.5\,\mathrm{s}$$ and $$2.5\,\mathrm{s}$$. For the purposes of this problem, we will use an average value of $$2\,\mathrm{s}$$. The distance traversed by the vehicle in this time is unsurprisingly called "reaction distance" $$D_\mathrm{react}$$ and is given by the formula $$ D_\mathrm{react} = v t_\mathrm{react} $$, where $$v$$ is the initial speed of the vehicle.
(2) In the "braking phase", the vehicle decelerates and comes to a complete stop. The "braking distance" $$D_\mathrm{brake}$$ that the vehicle covers in this phase is proportional to the square of the initial speed of the vehicle: $$ D_\mathrm{brake} = \alpha v^2 $$. The constant of proportionality $$\alpha$$ depends on the vehicle type and condition, as well as on the road conditions. Consider a typical value of $$10^{-2}\,\mathrm{s^2/m}$$.
If the initial speed of the vehicle is $$108\,\mathrm{km/h} = 30\,\mathrm{m/s}$$, what is the ratio between the relative rate of change of the stopping distance and the relative rate of change of the initial speed?

- Assume that you possess equal amounts of a product $$X$$ and $$Y$$, but you value them differently. Specifically, your "utility function" is of the form $$ U(X,Y) = C X^\alpha Y^\beta $$ for $$\alpha$$, $$\beta$$, and $$C$$ positive constants. What is your marginal rate of substitution (MRS) of $$Y$$ for $$X$$? 