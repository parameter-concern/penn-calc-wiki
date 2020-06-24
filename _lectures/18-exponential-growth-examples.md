---
title: Exponential growth examples
description: More examples of exponential growth and decay
lecture_number: 18
topic_number: 3
layout: lecture
mathjax: true
hidden_answers: true
---
Recall from the last module that the differential equation $$\frac{dx}{dt} = ax$$ has solution $$x = Ce^{at}$$, where $$C$$ is some constant. The constant $$C$$ can be thought of as an initial condition, the value of the function at time $$t=0$$. When $$a>0$$, the function has exponential growth. When $$a<0$$, the function has exponential decay:

This module is devoted to several examples of exponential growth and decay.
Radioactive decay

Carbon-14 is a radioactive isotope of carbon which exists in organic materials. It is known that the rate at which carbon-14 atoms decay is proportional to the number of carbon-14 atoms present. If $$I$$ represents the number of atoms, then the differential equation is

$$
\frac{dI}{dt} = -\lambda I,
$$

where $$\lambda$$ is positive (and so the number of atoms is decreasing).
Population growth

For bacteria with an abundant food supply, the population $$P$$ satisfies

$$
\frac{dP}{dt} = bP,
$$

for some positive $$b$$. But as the food supply dwindles, or overcrowding occurs, the population growth will necessarily slow (or else the bacteria would eventually consume the earth). Thus, this is not usually an accurate population model.
Interest accumulation

Consider a bank account with initial deposit (also called the principal) $$P$$, annual interest rate $$r$$, and which is compounded $$n$$ times a year (so $$n=1$$ gives simple interest, $$n=4$$ is quarterly interest, etc.). Then the value of the account at the end of $$k$$ years is $$P\left(1+\frac{r}{n}\right)^{nk}$$. What happens as $$n$$ gets bigger and bigger? Recall that $$\displaystyle \lim_{n \rightarrow \infty}\left(1+\frac{\alpha}{n}\right)^n = e^\alpha$$. Then it follows that

$$
\begin{align*}
\lim_{n \rightarrow \infty} P\left(1+\frac{r}{n}\right)^{nk} &= \lim_{n \rightarrow \infty} P\left[\left(1+\frac{r}{n}\right)^n\right]^k
&= P e^{rk}.
\end{align*}
$$

This is called continuous compounding. So an account with continuous compounding is worth $$Pe^{rk}$$ after $$k$$ years, where $$P$$ is the initial investment, and $$r$$ is the annual interest rate.
Rule of 70

The Rule of 70 is a mental math trick that approximates the number of years it takes for a continuously compounded account to double in value. The rule says that

$$
\begin{equation*} \text{\# years for the account to double } = \frac{70}{100r}. \end{equation*}
$$

In other words, the number of years is 70 divided by the annual percentage. Verify the Rule of 70. <button class="toggle" data-box="#box1">Answer</button>

<div id="box1" class="answer-hidden"></div>
{: id="box1" class="answer-hidden"}


The problem asks for $$k$$ when the balance has doubled. That is, find $$k$$ such that

$$
\begin{equation*} 2P = Pe^{rk}. \end{equation*}
$$

Dividing by $$P$$ and taking logarithms gives $$rk = \ln(2)$$, so $$k = \frac{\ln(2)}{r}$$. Since $$\ln(2) \approx .7$$, this shows that

$$
\begin{align*}
k &= \frac{\ln(2)}{r}
&\approx \frac{.7}{r}
&\approx \frac{70}{100r},
\end{align*}
$$

as desired.
Linguistics

Historical linguists study (among other things) word usage and the rate at which words fall out of use. Let $$W(t)$$ be the number of words which are in active use in English after $$t$$ years. One model predicts that $$\frac{dW}{dt} = -\lambda W$$, hence $$W = Ce^{-\lambda t}$$, and $$C$$ is the number of common words at time 0.

**Example**

Suppose the writing of John Milton (from around 1667) consists of 20% words which are unfamiliar to us today. Use the above model to estimate the fraction of words that Shakespeare's audience (from around 1600) recognized of Chaucer's writing (from around 1400).

<button class="toggle" data-box="#box2">Answer</button>

<div id="box2" class="answer-hidden"></div>
{: id="box2" class="answer-hidden"}


Let $$t$$ denote time measured in years. Let $$WM(t)$$ denote the number of words from Milton's time which are in common use at time $$t$$. Then

$$
WM(t) = WM(1667) e^{-\lambda (t-1667)}
$$

(the $$t-1667$$ is used in the exponent because we are interested in the number of years since Milton). Let $$WC(t)$$ denote the number of words from Chaucer's time which are in common use at time $$t$$. Then

$$
WC(t) = WC(1400)e^{-\lambda(t-1400)}.
$$

From the given information, we have that

$$
\frac{WM(2013)}{WM(1667)} = \frac{4}{5}.
$$

And according to the above formula, we have

$$
\frac{WM(1667)e^{-\lambda \cdot 346}}{WM(1667)} = \frac{4}{5}.
$$

The factors of $$WM(1667)$$ cancel, leaving

$$
e^{-\lambda \cdot 346} = \frac{4}{5}.
$$

Taking the logarithm of both sides and dividing by $$-346$$ gives

$$
\lambda = \frac{-\ln(4/5)}{346} \approx 6.5 \times 10^{-4}.
$$

Knowing $$\lambda$$ allows us to compute the fraction of words from Chaucer's time that would be recognized in Shakespeare's time:

$$
\begin{align*}
\frac{WC(1600)}{WC(1400)} &= \frac{WC(1400)e^{-\lambda(200)}}{WC(1400)}
&= e^{-\lambda(200)}
&\approx .88
\end{align*}
$$

So, according to this model, approximately 88% of words from Chaucer's work would have been understood in Shakespeare's time.

This model ignores the creation of new words as well as the fact that definitions of existing words can evolve over time. So it is probably not the most accurate model. It is worth noting that even if the mathematics are correct, if the underlying model is not very good, then the resulting answer will not be very good either.
Zombies

Suppose in the zombie apocalypse that the rate of change of the infected population $$Z(t)$$ is proportional to the uninfected population $$U(t)$$. Let $$P$$ be the total population (assumed to be constant). Then

$$
\frac{dZ}{dt} = rU = r(P-Z),
$$

since $$U = P-Z$$ (the number of uninfected is the total population less the infected). Taking the derivative of $$U = P-Z$$ gives

$$
\begin{align*}
\frac{dU}{dt} &= \frac{dP}{dt} - \frac{dZ}{dt}
&= - \frac{dZ}{dt}
&= -rU,
\end{align*}
$$

since $$P$$ was assumed to be constant. Thus, $$U(t) = U_0 e^{-rt}$$, where $$U_0$$ is the initial uninfected population. And so the zombie population is given by

$$
Z(t) = P - U_0e^{-rt}.
$$

Note the population is doomed, as $$Z(t) \rightarrow P$$ as $$t \rightarrow \infty$$.

Although a zombie apocalypse is unlikely, this model is still useful for other phenomena involving how quickly something spreads. This includes the spread of disease, propaganda, and technology. Another example is heat transfer, discussed in detail below.
Newton's law of cooling

Newton's law of cooling says that the rate of change of the temperature of a body is proportional to the difference of the temperatures of the body and ambient environment. Let $$T$$ be the temperature of the body and $$A$$ be the ambient temperature. Then

$$
\begin{equation*} \frac{dT}{dt} = k(A-T), \end{equation*}
$$

for some positive constant $$k$$. Separating gives

$$
\begin{equation*} \frac{dT}{T-A} = -k\,dt, \end{equation*}
$$

and integrating and exponentiating gives $$T-A = Ce^{-kt}$$. Thus the solution is $$T = A+Ce^{-kt}$$. Note that $$k$$ must be positive for this to model to make sense. Indeed, as $$t \rightarrow \infty$$, the temperature of the body should approach the ambient temperature, which will only happen if $$k>0$$. Also, note that $$C =T_0-A$$ is the initial difference in temperature.

## Exercises

- After drinking a cup of coffee, the amount $$C$$ of caffeine in a person's body obeys the differential equation 

$$ \displaystyle \frac{dC}{dt}= -\alpha C $$
where the constant $$\alpha$$ has an approximate value of 0.14 hours-1
How many hours will it take a human body to metabolize half of the initial amount of caffeine?

- The amount $$I$$ of a radioactive substance in a given sample will decay in time according to the following equation: 

$$ \displaystyle \frac{dI}{dt} = -\lambda I $$
Nuclear engineers and scientists tend to be concerned with the "half-life" of a substance, that is, the time it takes for the amount of radioactive material to be halved.
Find the half-life of a substance in terms of its decay constant $$\lambda$$.

- In a highly viscous fluid, a falling spherical object of radius $$r$$ decelerates right before reaching the bottom of the container. A simple model for this behavior is provided by the equation 

$$\displaystyle \frac{dh}{dt} = - \frac{\alpha}{r}h , $$
where $$h$$ is the height of the object measured from the bottom, and $$\alpha$$ is a constant that depends on the viscosity of the fluid.
Find the time it would take the object to drop from $$h = 6r$$ to $$h = 2r$$ in terms of $$\alpha$$ and $$r$$.

- On a cold day you want to brew a nice hot cup of tea. You pour boiling water (at a temperature of 212o F) into a mug and drop a tea bag in it. The water cools down in contact with the cold air according to Newton's law of cooling: 

$$ \displaystyle \frac{dT}{dt} = \kappa (A - T) $$
where $$T$$ is the temperature of the water, $$A = 32$$oF the ambient temperature, and $$\kappa = 0.36$$ min-1.
The threshold for human beings to feel pain when entering in contact with something hot is around 107o F. How many seconds do you have to wait until you can safely take a sip?

- On the night of April 14, 1912, the British passenger liner RMS Titanic collided with an iceberg and sank in the North Atlantic Ocean. The ship lacked enough lifeboats to accommodate all of the passengers, and many of them died from hypothermia in the cold sea waters. Hypothermia is the condition in which the temperature of a human body drops below normal operating levels (around 36oC). When the core body temperature drops below 28oC, the hypothermia is said to have become severe: major organs shut down and eventually the heart stops. 

If the water temperature that night was -2oC, how long did it take for passengers of the Titanic to enter severe hypothermia? Recall from lecture that heat transfer is described by Newton's law of cooling:
$$ \displaystyle \frac{dT}{dt} = \kappa (A - T) $$
where $$T$$ is the body temperature of a passenger, $$A$$ the water temperature, and $$\kappa = 0.016$$ min-1.

- The birthrate of a population (number of births per year $$ \times $$ 100 / number of population) is 20%, and the mortality rate (number of deaths per year $$ \times $$ 100/ number of population) is 5%. If the initial population is 10,000, find the function $$P(t)$$, the population as a function of time. How long does it take for the population to double?
- Let $$y(t)$$ denote the number of atoms of a particular radioactive isotope of carbon at year $$t$$. We know that the rate at which $$y(t)$$ decreases is proportional to $$y$$ itself. (a) What differential equation does $$y(t)$$ satisfy? (b) If it takes 5 years for the number to decrease to half of its initial number, what is the constant involved in your answer of part (a)? 