---
title: More differential equations
description: Linear first order differential equations
lecture_number: 19
topic_number: 3
layout: lecture
mathjax: true
---
Recall that an ordinary differential equation is an equation involving a function and its derivatives. The solution to a differential equation is a function which satisfies the equation. An earlier module introduced a few basic differential equations. This module deals with a few different families of differential equations and the methods of solving them.
Autonomous differential equations

A differential equation is called autonomous if the derivative of the function ($x(t)$) is independent of ($t$), i.e. the equation is of the form

(:latex:) \[ \frac{dx}{dt} = f(x). \] (:latexend:)

Logically, a nonautonomous differential equation is one where the derivative equals a function of both ($x$) and ($t$):

(:latex:) \[ \frac{dx}{dt} = f(x,t). \] (:latexend:)

In general, nonautonomous differential equations can be very difficult, but certain types yield to a little algebra and integration. These include separable differential equations and linear first order differential equations, which are covered here.
Separable differential equations

A separable differential equation is one where, with a little algebra, we are able to express the differential equation in the form

(:latex:) \begin{equation*} \frac{dx}{dt} = f(x)g(t). \end{equation*} (:latexend:)

This may involve some algebra. Note in particular that any autonomous equation is separable (think of ($g(t) = 1$)). Once a differential equation is factored this way, it can be solved by using the chain rule and some algebra:

(:latex:) \begin{align*} dx &= \frac{dx}{dt} \, dt
dx &= f(x)g(t) \, dt
\frac{dx}{f(x)} &= g(t) \, dt. \end{align*} (:latexend:)

(This is why these equations are called separable--the variables can be separated to opposite sides of the equation). To solve this equation, one must find the functions whose derivatives are ($\frac{1}{f(x)}$) and ($g(t)$), respectively. In other words, one integrates both sides.

Example

Solve the differential equation

(:latex:) \[ y' = 3yx^2. \] (:latexend:) (:toggle hide show="Answer" box1:)

Separating gives

(:latex:) \begin{equation*} \frac{dy}{y} = 3x^2 \,dx. \end{equation*} (:latexend:)

Integrating both sides, we have

(:latex:) \begin{align*} \int \frac{dy}{y} &= \int 3x^2 \, dx
\ln y &= x^3 + C. \end{align*} (:latexend:)

Now exponentiating both sides gives

(:latex:) \begin{align*} y &= e^{x^3+C}
&= Ce^{x^3}, \end{align*} (:latexend:)

for some constant ($C$) (remember that the ($C$) is not the same in the first and second line above, but we just rewrite it for convenience).

Example

Solve the differential equation

(:latex:) \[ \frac{dx}{dt} = e^{t-x}. \] (:latexend:) (:toggle hide show="Answer" box2:)

First, using a law of exponents on the right side, we have

(:latex:) \[ e^{t-x} = e^te^{-x}. \] (:latexend:)

Now, separating gives

(:latex:) \[ e^x \, dx = e^t \, dt. \] (:latexend:)

We might be tempted at this point to say ($x=t$) because of the symmetry of this equation. But we must integrate both sides, which introduces an integration constant:

(:latex:) \[ e^x = e^t + C. \] (:latexend:)

Now taking the logarithm gives

(:latex:) \[ x = \ln (e^t+C). \] (:latexend:)
Note

We must have the integration constant contained within the natural logarithm. In general, it is best to introduce the integration constant as soon as the integration occurs. A common mistake is to forget the constant and then at the very end of the problem add it. This is frequently incorrect, as in this case.

Example

Solve the initial value problem ($\frac{dy}{dx} = xy+x$), with ($y(0) = 3$). (:toggle hide show="Answer" box4:)

First, this differential equation does not look like it is of the form of a separable differential equation. However, with a little factoring, one finds that ($\frac{dy}{dx} = x(y+1)$). Thus,

(:latex:) \begin{equation*} \frac{dy}{y+1} = x\,dx. \end{equation*} (:latexend:)

Anti-differentiating gives ($\ln|y+1| = \frac{1}{2}x^2+C$). Then, exponentiating gives

(:latex:) \begin{equation*} |y+1| = e^{x^2/2+C} = De^{x^2/2}. \end{equation*} (:latexend:)

Apply the initial condition by plugging in ($x=0$) and ($y = 3$), which gives that ($D=4$). Thus, the solution to the initial value problem is ($y = 4e^{x^2/2}-1$). One should double check that this satisfies the differential equation.

Example

Assume that a falling body with mass ($m$) has a drag force proportional to velocity ($v(t)$). Then the downward acceleration ($mg$) is being counteracted by the upward acceleration ($\kappa v$), for some constant ($\kappa$). Thus,

(:latex:) \begin{align*} m\frac{dv}{dt} &= mg - \kappa v
&= -\kappa \left( v - \frac{mg}{\kappa} \right). \end{align*} (:latexend:)

which is separable. Solve this differential equation. (:toggle hide show="Answer" box3:)

Separating gives

(:latex:) \[ \frac{dv}{v-mg/\kappa} = - \frac{\kappa}{m} dt. \] (:latexend:)

Integrating both sides gives ($\ln(v- mg/\kappa) = -\kappa t/m + C$), and so exponentiating and solving for ($v$) gives

(:latex:) \[ v = Ce^{-\kappa t/m} + \frac{mg}{\kappa} \] (:latexend:)

(here ($C$) is replacing the constant ($e^C$) from exponentiating). Note that as ($t \rightarrow \infty$), the exponential term goes to 0, and so ($v(t) \rightarrow \frac{mg}{\kappa}$), which is the terminal velocity of the falling body (when the force of gravity and drag cancel each other).
Linear 1st order differential equations

The product rule gives a technique (integration by parts) for seemingly difficult integrals; the product rule also gives a technique for solving a certain class of non-separable differential equations called linear 1st order differential equations. This is a differential equation which can be written in the form

(:latex:) \begin{equation*} \frac{dx}{dt} = A(t)x + B(t) \end{equation*} (:latexend:)

(as for separable differential equations, this may involve a little algebra). This form gives the reason for calling these equations linear, since dropping the ($t$)'s gives

(:latex:) \begin{equation*} \frac{dx}{dt} = Ax+B, \end{equation*} (:latexend:)

which is reminiscent of the equation of a line. 1st order means that the equation only involves the function ($x$) and its derivative ($\frac{dx}{dt}$) (and no higher derivatives), along with functions of ($t$).

The standard form of a linear 1st order differential equation is achieved by bringing all the terms involving ($x$) to the left side, which gives

(:latex:) \begin{equation*} \frac{dx}{dt} - A(t) x = B. \end{equation*} (:latexend:)

Example

Identify which of these is a linear 1st order differential equation, and put it in standard form if it is. In the cases that are not, identify which condition is violated. Are all separable equations also linear 1st order?

    ($tx' + x = 0$)
    ($x' - e^tx^2 = 0$)
    ($x' = x\sin(t)$)
    ($x'' - t^2 \frac{dx}{dt}= 0$) 

(:toggle hide show="Answer" box5:)

    Linear 1st order. Standard form is ($x' + \frac{1}{t}x = 0$).
    Not linear because of the ($x^2$). Note that this is separable though.
    Linear 1st order. Standard form is ($x' - \sin(t) x = 0$).
    Not 1st order because of the presence of ($x''$). 

Number 2 shows that a differential equation can be separable even though it is not linear 1st order.
Integrating factors

The method for solving linear 1st order differential equations is to use the product rule to factor the sum of two derivatives into the derivative of a product. It is best explained by example.

Example

In part 1 from the previous example, note that ($tx' + x = (tx)'$) by the product rule. So that differential equation can be written as ($(tx)' = 0$). Integrating both sides gives ($tx = C$) for some constant ($C$). Thus the solution is ($x = \frac{C}{t}$).

However, not all linear 1st order differential equations are expressed so nicely. For instance, in example 3 above, one cannot rewrite ($x' - \sin(t)x$) as the derivative of a product of functions. This is where an integrating factor is used.

The integrating factor, denoted by ($I(t)$) in this course, is a function which is multiplied through the entire differential equation, giving

(:latex:) \[ I \frac{dx}{dt} - IAx = IB. \] (:latexend:)

($I(t)$) is chosen so that the left side of this equation can be factored as a derivative of a product using the product rule. Symbolically, the goal is to choose ($I(t)$) so that

(:latex:) \begin{equation*} I\frac{dx}{dt} - IAx = \frac{d}{dt}(Ix). \end{equation*} (:latexend:)

To find ($I$), expand the product ($\frac{d}{dt}(Ix) = I \frac{dx}{dt} + \frac{dI}{dt} x$). For this to equal the left side of the above equation, it must be that ($-I A = \frac{dI}{dt}$). This differential equation is separable, and one finds that ($\frac{dI}{I} = -A\,dt$). Integrating and exponentiating gives that

(:latex:) \begin{equation*} I(t) = e^{\int -A(t)\,dt}. \end{equation*} (:latexend:)

One need not work through all this algebra every time but can jump straight to writing down the integrating factor. Multiplying through by the integrating factor allows the left side to be rewritten by the product rule, and integrating both sides finishes the problem.

To summarize the method:

    Get the differential equation into standard form ($\frac{dx}{dt} - A(t)x = B(t)$).
    Compute the integrating factor ($I(t) = e^{-\int A(t)\,dt}$).
    Multiply the entire equation by ($I(t)$), which gives 

(:latex:) \begin{equation*} I \frac{dx}{dt} - I A x = I B. \end{equation*} (:latexend:)

    Rewrite the left side as the derivative of a product (this works because of the way ($I(t)$) was chosen): ($\frac{d}{dt}(I x) = IB$).
    Integrate both sides and then divide by ($I$).
    The final answer, then, is given by 

(:latex:) \[ x(t) = e^{\int A} \cdot \int B e^{-\int A}. \] (:latexend:)

Example

Solve the differential equation

(:latex:) \[ tx' + tx = t^2. \] (:latexend:)

Hint: ($\int te^t \,dt = te^t-e^t+C$). (:toggle hide show="Answer" box6:)

Divide through by ($t$) to get the equation in standard form: ($x' + x = t$). Compute the integrating factor

(:latex:) \[ I = e^{\int\,dt} = e^t. \] (:latexend:)

Multiplying through gives

(:latex:) \[ e^tx' + e^tx = e^tt. \] (:latexend:)

Rewriting this using the product rule gives ($(e^tx)' = te^t$). Integrating both sides and using the hint gives

(:latex:) \[ e^tx = te^t-e^t + C. \] (:latexend:)

Finally, dividing by ($e^t$) gives

(:latex:) \[ x = t-1 + \frac{C}{e^t} \] (:latexend:)

as a final answer.

Example

Suppose a 1000 gallon tank is 90% full. An additive is is pumped into the tank at a rate of 10 gallons per minute. The mixture is well stirred and drained at a rate of 5 gallons per minute.

What is the concentration of the additive when the tank is full? (:toggle hide show="Answer" box7:)

Begin by setting up a few variables to help make sense of what is happening. Let ($V(t)$) be the volume of the total mixture at time ($t$). Let ($Q(t)$) be the total amount of additive in the mixture at time ($t$). Let ($C(t)$) be the concentration of the mixture, i.e.

(:latex:) \[ C(t) = \frac{Q(t)}{V(t)}. \] (:latexend:)

The volume is not too difficult to compute. Since there are 10 gallons per minute entering the tank, and 5 gallons per minute leaving the tank, the net amount of fluid entering the tank is 5 gallons per minute. The tank begins at 90% full, which is 900 gallons. So

(:latex:) \[ V(t) = 900 + 5 t, \] (:latexend:)

and is full at ($t = 20$). Next, consider the rate at which the quantity ($Q(t)$) of additive in the tank is changing. There is 10 gallons of pure additive entering per minute and 5 gallons of mixture leaving. Therefore the amount of additive leaving is ($5C$). Putting this together gives

(:latex:) \[ \frac{d}{dt}Q = 10 - 5C = 10 - \frac{5Q}{900 + 5t}. \] (:latexend:)

Rearranging this gives

(:latex:) \[ \frac{dQ}{dt} + \frac{1}{180+t}Q = 10. \] (:latexend:)

This is a 1st order linear differential equation. Computing the integrating factor we find

(:latex:) \begin{align*} I &= \exp \left( \int \frac{1}{180+t} dt \right)
&= \exp (\ln(180+t))
&= 180 + t. \end{align*} (:latexend:)

Multiplying through gives

(:latex:) \[ (180+t) \frac{dQ}{dt} + Q = 10(180+t). \] (:latexend:)

Now, as always, the left side can be rewritten using the product rule to give

(:latex:) \[ \frac{d}{dt} \left[Q(180+t)\right] = 1800 + 10t. \] (:latexend:)

Integrating both sides gives

(:latex:) \[ Q \cdot (180+t) = 1800t + 5t^2 + K \] (:latexend:)

(using ($K$) here to avoid confusion with concentration ($C$)). We can find ($K$) by setting ($t=0$) in this equation. Since ($Q(0) = 0$) (there is no additive in the tank initially), we find ($K=0$).

Now, solving for ($Q$) and evaluating at ($t=20$) gives

(:latex:) \begin{align*} Q &= \frac{1800t + 5t^2}{180+t}
&= 190. \end{align*} (:latexend:)

So the final concentration of the full tank is

(:latex:) \[ \frac{190}{1000} = 19\%. \] (:latexend:)
EXERCISES

    Solve the differential equation ($\displaystyle \frac{dx}{dt} = \frac{x}{t}$).
    Solve the differential equation ($\displaystyle \frac{dx}{dt} = \frac{\sqrt{1-x^2}}{\sqrt{1-t^2}}$).
    Given that ($x(0)=0$) and ($\displaystyle \frac{dx}{dt} = te^x$), compute ($x(1)$).
    What integrating factor should be used to solve the linear differential equation 

($ \displaystyle t^2\frac{dx}{dt}=4t-t^5x $)

    Solve the differential equation ($\displaystyle \frac{dx}{dt} - 5x = 3$).
    Solve the differential equation ($\displaystyle \frac{dx}{dt} = \frac{x}{1+t} + 2$).
    Suppose that, in order to buy a house, you obtain a mortgage. If the lender advertises an annual interest rate ($r$), your debt ($D(t)$) will increase exponentially according to the simple O.D.E. 

($ \displaystyle \frac{dD}{dt} = rD $)
If you pay your debt at a rate of ($P$) (annual rate, paid continuously), the evolution of your debt will then (under assumptions of continual compounding and payment) obey the linear differential equation
($ \displaystyle \frac{dD}{dt} = rD - P $)
Using this model, answer the following question: if initial amount of the mortgage is for $400,000, the annual interest rate is 5%, and you pay at a rate of $40,000 every year, how many years will it take you to pay off the debt?

    German physician Ernst Heinrich Weber (1795-1878) is considered one of the fathers of experimental psychology. In his study of perception, he noticed that the perceived difference between two almost-equal stimuli is proportional to the percentual difference between them. In terms of differentials, we can express Weber's law as 

($ \displaystyle dp = k \frac{dS}{S} , $)
where ($p$) is the perceived intensity of a stimulus and ($S$) its actual strength. Observe the relative rate of change on the right hand side. In what way must the magnitude of a stimulus change in time for a human being to perceive a linear growth? Linearly? Logarithmically? Polynomially?

    Some nonlinear differential equations can be reduced to linear ones by a clever change of variables. Bernouilli equations 

($ \displaystyle \frac{dx}{dt} + p(t) x = q(t) x^\alpha, \qquad \alpha \in \mathbb{R} $)
constitute the most important case. Notice that for ($\alpha=0$) or ($\alpha=1$) the above equation is already linear. For other values of ($\alpha$), the substitution ($u = x^{1-\alpha}$) yields a linear differential equation in the variable ($u$).
Apply the above change of variables in the case
($ \displaystyle \frac{dx}{dt} + 2tx = x^3 $)
What differential equation on ($u$) do you get? 