---
title: Elements
description: Pressure, force, and other applications
lecture_number: 38
topic_number: 4
layout: lecture
mathjax: true
---
This module deals with various problems that can be modeled using integral calculus. As in the previous sections, the problem will be to find the total accumulation of some quantity ($U$), and the method will be to determine a slice of the quantity, the U element ($dU$), and integrate.
Mass
Mass of a rod

Consider the problem of determining the mass of a rod. Suppose the rod's density varies along the length of the rod (but the rod is uniform in cross section). Let ($\rho(x)$) denote the linear density (i.e. the mass per unit of length) of the rod at position ($x$):

Then the mass element ($dM$) is the density ($\rho(x)$) times the thickness of the slice ($dx$), as shown above, and it follows that the mass of the rod is

(:latex:) \begin{align*} M &= \int dM
&= \int_{x=0}^L \rho(x) dx. \end{align*} (:latexend:)
Mass of the earth

Consider the problem of finding the mass of the earth. Suppose the density of the earth ($\rho(r)$) is given as a function of the distance from the center of the earth. Assume that there are just three layers (inner core, outer core, and mantle) and that the density is constant within each layer.

What is the mass element in this case? It is important to note that in this example we are measuring the contribution of a spherical shell to the mass of the earth. This contribution is the volume of the spherical shell multiplied by the density of the shell. Mathematically,

(:latex:) \[ dM = \rho(r) \cdot dV. \] (:latexend:)

Recalling that the surface area of a sphere of radius ($r$) is ($4 \pi r^2$), we have that the volume element is

(:latex:) \[ dV = 4 \pi r^2 \, dr, \] (:latexend:)

and so the mass element is

(:latex:) \[ dM = 4 \pi \rho(r)r^2 \, dr. \] (:latexend:)

Example

Using the approximate graph of density above, estimate the mass of the earth.

(:toggle hide show="Answer" box0:)

Note that our volume is being measured in cubic kilometers, but the density ($\rho(r)$) is in grams per cubic centimeter. We need a conversion factor ($C$) to make sure the units come out correctly. A little unit conversion gives us that

(:latex:) \[ C = 1 \frac{\hbox{g}}{\hbox{cm}^3} = 10^{12} \frac{\hbox{kg}}{\hbox{km}^3}. \] (:latexend:)

So we need to multiply by this so that the units are correct (and the final answer will be in kilograms).

Splitting the integral based on the values of ($r$) for which ($\rho(r)$) is constant, we find

(:latex:) \begin{align*} M &= \int dM
&= C \int_{r=0}^{6400} 4 \pi r^2 \rho(r) \, dr
&= 4 \pi C \left(\int_{r=0}^{1200} r^2 \rho(r) \, dr + \int_{r=1200}^{3400} r^2 \rho(r) \, dr + \int_{r=3400}^{6400} r^2 \rho(r) \, dr \right)
&= 4 \pi C \left(13 \cdot \frac{r^3}{3}\bigg|_0^{1200} + 10 \cdot \frac{r^3}{3}\bigg|_{1200}^{3400} + 5 \cdot \frac{r^3}{3}\bigg|_{3400}^{6400} \right)
&\approx 6.3 \cdot 10^{24} \hbox{ kilograms} \end{align*} (:latexend:)

According to Wolfram Alpha, the mass of the earth is approximately ($5.97 \cdot 10^{24}$) kilograms, so our rough estimate is not too far off.
Torque

Imagine a rod of variable density which is attached to a hinge. The torque at the hinge depends not just on the weight of the rod but on the distribution of the weight.

If there were just a mass-less rod with a single point mass, the torque would be ($\hbox{ Force } \times \hbox{ Distance }$). This can be used to determine the torque element ($dT$) by thinking of each slice of the rod as a point mass. What is the torque on such a slice?

First, the torque element is the distance from the hinge, ($x$), times the force element ($dF$) (the force on the slice). The force element is the mass of the slice ($dM$) times the gravitational constant ($g$). Finally, as in the previous example, the mass element ($dM = \rho(x) \, dx$). Putting it all together, one finds

(:latex:) \[ dT = x \cdot g \cdot \rho(x) \, dx. \] (:latexend:)

Integrating this over the length of the rod gives the torque.
Hydrostatic force

The next application is to compute the total force exerted by a tank of fluid on a surface submerged in the tank, often called the hydrostatic force. For a tangible example, consider a large aquarium with a circular glass viewing window (see the diagram below). If the viewing window has radius ($r$), and the top of the viewing window is at depth ($h$), then the problem is to find the total force of the water on the viewing window.

As always, the method will be to find the force element ($dF$) (the force on a small strip of the window), and then use integration to find the total force.

Recall that if pressure is constant across a surface, the force on the surface is ($\hbox{area }\times \hbox{ pressure}$). Hydrostatic pressure is given by

(:latex:) \[ P = \hbox{weight density of fluid }\times \hbox{ depth}. \] (:latexend:)

Note the units: ($\frac{N}{m^3} \cdot m = \frac{N}{m^2}$), which is the correct unit for pressure (force per unit of area). Since the density of the fluid is assumed to be constant, the pressure only depends on the depth.Therefore, the most logical choice for the force element is a horizontal strip, since the depth, and hence the pressure, will be constant across the strip. Letting ($dA$) denote the area of the strip, we find that the force element is given by

(:latex:) \[ dF = P \, dA = \rho x \, dA, \] (:latexend:)

where ($\rho$) is the weight density of the fluid and ($x$) is the depth of the strip.

Example

Compute the total force exerted on the circular viewing window in the aquarium shown above.

(:toggle hide show="Answer" box1a:)

As mentioned above, we will use horizontal strips of the window as the area element. The force element is the amount of force on that strip of the window. Let ($x$) be the distance from the center of the window to the horizontal strip. Let up be negative, down be positive (so the top of the window is ($x = -r$) and the bottom of the window is ($x=r$):

Then the depth of the strip is ($h+r+x$), and the area of the strip is ($2 \sqrt{r^2-x^2} \, dx$). Thus the force element in this example is

(:latex:) \[ dF = (h+r+x) \rho \cdot 2\sqrt{r^2-x^2} \, dx \] (:latexend:)

where ($\rho$) is the weight density of water. So

(:latex:) \begin{align*} F &= \int dF
&= 2 \rho \int_{-r}^r (h+r+x)\sqrt{r^2-x^2}\,dx
&= 2 \rho \int_{-r}^r (h+r)\sqrt{r^2-x^2}\,dx + 2 \rho \int_{-r}^r x \sqrt{r^2-x^2}\,dx. \end{align*} (:latexend:)

Now, notice that ($x \sqrt{r^2-x^2}\,dx$) is an odd function, so its integral from ($-r$) to ($r$) is 0. Thus

(:latex:) \begin{align*} F &= 2 \rho (h+r) \int_{-r}^r \sqrt{r^2-x^2}\,dx
&= 2\rho (h+r) \frac{\pi r^2}{2}
&= \rho (h+r) \pi r^2, \end{align*} (:latexend:)

since ($\int \sqrt{r^2-x^2}\,dx$) gives half the area of a circle of radius ($r$).

It is worth observing that with a very symmetric window such as the circle in this example, one can take the area of the window, ($\pi r^2$), and multiply by the pressure at the center of the window ($\rho (h+r)$), to find the hydrostatic force:

(:latex:) \[ F = \rho \pi r^2 (h+r). \] (:latexend:)

The reason this works is that the pressure on a horizontal strip above the center of the window averages with the pressure on the strip's mirror image below the center to give the pressure at the center of the window.

Example

Compute the force on the endcap of a full cylindrical tank of radius ($R$) on its side.

(:toggle hide show="Answer" box1b:)

Using the knowledge gleaned from the previous example, we can take the area of the endcap, ($\pi R^2$), and multiply by the hydrostatic pressure at the center of the endcap, which is ($ \rho R$), to find that the force is

(:latex:) \[ F = \pi R^2 \cdot \rho R = \rho \pi R^3. \] (:latexend:)

We could also note that this is really a special case of the aquarium window example above, by setting ($h=0$) in that example.

Example

Consider a dam in the shape of a trapezoid with height ($h$), top edge ($l_1$) and bottom edge ($l_2$). Find the total force exerted on the dam by the water:

(:toggle hide show="Answer" box1c:)

As above, the force element ($dF$) is the force exerted on a horizontal strip. Let ($x$) be the distance of the horizontal strip from the top of the dam, and ($l(x)$) be the length of the strip

Since the shape is a trapezoid, ($l(x)$) is a linear function of ($x$), and from the top and the bottom of the dam, one finds that ($l(0) = l_1$) and ($l(h) = l_2$). It follows from the slope intercept form of a line that ($l(x) = l_1 + \frac{l_2-l_1}{h} x$).

So the force acting on the strip is ($dF = \rho x \,dA$), where ($\rho$) is the weight density of the water, ($x$) is the depth of the strip, and ($dA = (l_1 + \frac{l_2-l_1}{h}x) \, dx$) is the area of the strip. Putting it all together, one finds

(:latex:) \begin{align*} F &= \int dF
&=\int_0^h \rho x \left(l_1 + \frac{l_2-l_1}{h}x\right)\,dx
&=\rho \left(\frac{l_1x^2}{2} + \frac{l_2-l_1}{3h}x^3\right) \bigg|^h_0
&= \rho\left(\frac{l_1h^2}{2} +\frac{l_2-l_1}{3h}h^3\right)
&= \frac{\rho h^2}{6}(l_1+2l_2). \end{align*} (:latexend:)
Present value

Consider the problem of determining the present value of some amount of money at a future time. Turning the problem around, first consider the value of an initial amount of money ($P_0$) at a future time ($t$). Assuming a constant annual nominal interest rate ($r$) and continuous compounding, this problem was an example of exponential growth, and had solution

(:latex:) \[ P(t) = P_0 e^{rt}, \] (:latexend:)

where ($t$) is the time in years. Given some amount of money, ($P$), at time ($t$), finding its present value is a matter of solving ($P = P_0 e^{rt}$) for ($P_0$). In other words, solving for present value in this simple case is the same as finding the initial investment ($P_0$) which yields ($P$) after ($t$) years of continuous compounding interest. Solving this equation gives that the present value of a future amount ($P$) at time ($t$) is given by

(:latex:) \[ P_0 = P e^{-rt}. \] (:latexend:)

Example

Find the present value of $1000000 in 30 years, assuming an interest rate of ($r = .08$).

(:toggle hide show="Answer" box1:)

From the above equation one finds that

(:latex:) \begin{align*} P_0 &= Pe^{-rt}
&= 1000000e^{(-.08) \cdot 30}
&\approx 90717. \end{align*} (:latexend:)

Now consider an income stream, say from a job. If ($I(t)$) is the rate of income at time ($t$), what is the present value of that income stream? Let ($PV$) be the present value. Then consider the income earned over a small amount of time ($t$) years in the future:

(:latex:) \[ dI = I(t) \, dt \] (:latexend:)

(the income element). This small bit of income at time ($t$) contributes ($e^{-rt}I(t)dt$) to the present value of the income stream. Thus the present value element is given by

(:latex:) \[ dPV = e^{-rt} I(t)dt. \] (:latexend:)

Integrating this over the range of values of ($t$) (the time period of the income stream) gives the present value of that income stream.

Example

The Bigbucks lottery has an option of either a single lump sum payment today or an annuity which pays a constant amount each year for 20 years. Suppose the annuity pays $3 million a year (for 20 years), and that the interest rate will remain steady at ($r=.05$). What is the fair lump sum payout today?

(:toggle hide show="Answer" box2:)

The income stream ($I(t)$) is constant at ($3 \cdot 10^6$). Thus,

(:latex:) \begin{align*} PV &= \int dPV
&= \int_{t=0}^{20} e^{-rt} I(t)dt
&= 3 \cdot 10^6 \int_{t=0}^{20} e^{-.05 t} dt
&= 3 \cdot 10^6 \left(\frac{1}{-.05} e^{-.05t} \bigg|_{t=0}^{20}\right)
&= 3 \cdot 10^6 \cdot (-20) (e^{-1} - 1), \end{align*} (:latexend:)

which is approximately $38 million.
EXERCISES

    Consider a dam with the shape of an isosceles triangle. The base of the triangle, which is parallel to the ground, is 5m long, and the height of the triangle is 10m. The weight density of water is given by ($\rho$). Compute the force exerted on the dam by water. 