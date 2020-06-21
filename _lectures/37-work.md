---
title: Work
description: Computing work with integration
lecture_number: 37
topic_number: 4
layout: lecture
mathjax: true
---
Recall that work is the amount of energy required to perform some action. When the amount of force is constant, work is simply

(:latex:) \[ \hbox{work} = \hbox{force } \times \hbox{ distance}. \] (:latexend:)

For example, if a book weighing 22 Newtons (about 5 pounds) is lifted 2 meters, the total work done is ($22 N \times 2 m = 44 J$) (J is the Joule, which equals one Newton-meter).

Consider a situation where the force is not constant. For instance, if one were to lift a weight using a non-negligible rope, there is less rope being pulled up (and hence less force) as the weight goes further up. It is in situations like these that we need a better formula to compute work.
Work element

Computing work when the force is not constant requires integration. As in previous sections, the first step is to determine the work element ($dW$), and then integrate:

(:latex:) \[ W = \int dW. \] (:latexend:)

Because work arises in a variety of situations, there is not one simple formula for the work element. For different applications the work element will look different. In some situations, it is best to consider a small movement ($dx$), where the force can be thought of as constant for that small movement, which allows the work element to be expressed as ($dW = F \cdot dx$).
Springs

The force required to displace a spring varies with the displacement. The further the spring is stretched, the more resistant it becomes to being stretched further. Consider three types of springs:

    Linear. A spring is linear if the force of resistance grows linearly with the displacement. That is, 

(:latex:) \[ F(x) = \kappa x. \] (:latexend:)

for some constant ($\kappa$), which represents the stiffness of the spring.

    Hard. A spring is hard if the force of resistance grows faster than linearly with the displacement: 

(:latex:) \[ F(x) = \kappa x + O(x^2). \] (:latexend:)

    Soft. A spring is soft if the force of resistance grows slower than linearly with the displacement: 

(:latex:) \[ F(x) = \kappa x - O(x^2). \] (:latexend:)

Consider for any of these springs what the work element ($dW$) is. When the spring is stretched to ($x$), the force of resistance is ($F(x)$). For the next infinitesimal amount of stretching ($dx$), the force can be presumed to be constant:

Therefore, the work element (i.e. the amount of work to stretch the spring the additional amount ($dx$)) is

(:latex:) \[ dW = F(x) \, dx. \] (:latexend:)

Example

Compute the amount of work it takes to stretch a linear spring from rest (when ($x=0$)) to ($x=a$).

(:toggle hide show="Answer" box1:)

As shown above, the work element (i.e. the amount of work to stretch the spring a short distance ($dx$)) is

(:latex:) \[ dW = F(x)\,dx = \kappa x \, dx. \] (:latexend:)

It follows that

(:latex:) \begin{align*} W &= \int dW
&= \int_{x=0}^a \kappa x \, dx
&= \kappa \frac{x^2}{2} \bigg|_{x=0}^a
&= \kappa \frac{a^2}{2}. \end{align*} (:latexend:)

Example

Consider a nonlinear, soft spring which exerts a force of ($F(x) = 3x-x^2$) Newtons when the spring is stretched to ($x$) meters. Determine how much work is required to stretch the spring from 1 meter to 3 meters.

(:toggle hide show="Answer" box2:)

The work element is

(:latex:) \begin{align*} dW &= F(x) \, dx
&= (3x-x^2) \, dx. \end{align*} (:latexend:)

Thus, the total work to stretch the spring from 1 meter to 3 meters is

(:latex:) \begin{align*} W &= \int dW
&= \int_{x=1}^3 (3x-x^2) \, dx
&= \frac{3}{2}x^2 - \frac{1}{3}x^3 \bigg|_{x=1}^3
&= \left(\frac{27}{2} - 9\right) - \left(\frac{3}{2} - \frac{1}{3}\right)
&= \frac{10}{3} \hbox{ Joules}. \end{align*} (:latexend:)
Pulling up a rope

In some situations, one must do a little work to determine what ($F(x)$) is, and then one can integrate, as in the above examples.

Example

Consider a rope which is 100 feet long and density 1 pound/foot. It hangs from a wall which is 50 feet high (so 50 feet of rope runs down the length of the wall and the remaining 50 feet is coiled at the bottom of the wall). How much work (in foot-pounds) is required to pull the rope to the top of the wall?

(:toggle hide show="Answer" box3:)

As the first 50 feet of rope are brought up, there is always precisely 50 feet of rope hanging from the building (because every foot of rope brought onto the top of the building is replaced by a rope which is coiled below). These 50 feet of rope weigh 50 lbs, so that is the force required to support them. If ($x$) denotes the amount of rope which has been taken onto the roof, then

(:latex:) \[ F(x) = 50; \quad 0 \leq x \leq 50. \] (:latexend:)

After the first 50 feet of rope have been brought to the roof, there is now 50 feet of rope dangling with nothing left coiled below. Therefore, as we bring up these last 50 feet, there is less and less rope hanging, and so the weight of the rope (and hence the force we exert) is decreasing. It decreases linearly, since the rope has constant density. Each foot of rope we bring up decreases the weight by 1 lb, and so

(:latex:) \[ F(x) = 100 - x; \quad 50 \leq x \leq 100 \] (:latexend:)

(to see that this is right, note that it is linear and matches at the endpoints). We can graph the force as a function of the amount of rope we have brought up:

Now, we can find the work by integrating the work element

(:latex:) \begin{align*} W &= \int dW
&= \int_{x=0}^{100} F(x) \, dx. \end{align*} (:latexend:)

Note that this is the area under the graph of the force (highlighted above), which is easier to compute than to do it algebraically. Splitting it into a square and a triangle, the area (and hence the work) is

(:latex:) \[ 50 \hbox{ lb} \times 50 \hbox{ ft} + \frac{1}{2} 50 \hbox{ lb} \times 50 \hbox{ ft} = 3750 \hbox{ ft-lb}. \] (:latexend:)
Work element by slices

In other situations, such as pumping liquid, digging a hole, or piling gravel, a fruitful method for determining the work involved is to consider a slice of the material which is being moved. Determining the weight of the slice, and multiplying by the distance the slice has to be lifted gives the amount of work required for that slice. That is precisely the work element. Integrating over all the slices in the object gives the total amount of work to move that object.

Example: pumping liquid

Consider an inverted conical tank (so the tip of the cone points downward) with base radius 5 feet and height 10 feet. Water is pumped into the tank through a valve at the tip of the cone:

How much work is required to fill the tank with water? Leave the weight density of water as the constant ($\rho$).

(:toggle hide show="Answer" box4:)

Consider a slice of the water in the tank. Let ($x$) be the distance of the slice from the tip of the tank. That is, ($x$) is the distance that the slice of water has to be lifted. Let ($r$) be the radius of the slice:

Above, we said that it is the weight of the slice multiplied by the distance the slice had to be moved. But the weight of a slice is just the volume of the slice times the density of the slice. Letting ($\rho$) denote the weight density of the substance (in this case water), we have

(:latex:) \begin{align*} dW &= \hbox{ weight of slice } \times { distance slice travels }
&= \rho \cdot dV \cdot \hbox{ distance slice travels }. \end{align*} (:latexend:)

In the problem at hand, we have

(:latex:) \[ dV = \pi r^2 \, dx, \] (:latexend:)

and the distance the slice is lifted is ($x$), by the way we labeled our diagram. To finish, we must get ($r$) in terms of ($x$), which requires a little bit of geometry. If we flatten our cone and look at it from the side, we get similar triangles:

Therefore,

(:latex:) \[ \frac{r}{x} = \frac{5}{10} = \frac{1}{2}, \] (:latexend:)

and so ($r = \frac{x}{2}$). Putting this together, we have

(:latex:) \begin{align*} dW &= \rho \cdot dV \cdot \hbox{ distance slice travels}
&= \rho (\pi r^2 \, dx) x
&= \pi \rho \frac{1}{4}x^3 \, dx. \end{align*} (:latexend:)

Note that ($x$) ranges from 0 to 10, so the work required to fill the tank is

(:latex:) \begin{align*} W &= \int dW
&= \int_{x=0}^{10} \pi \rho \frac{1}{4} x^3 \, dx
&= \frac{\pi \rho}{4} \frac{x^4}{4} \bigg|_{x=0}^{10}
&= 625 \pi \rho. \end{align*} (:latexend:)

Example: digging a hole

Consider two workers digging a hole. How deep should the first worker dig so that each does the same amount of work? Let the weight density of the dirt be the constant ($\rho$), the depth of the hole is ($D$), and the cross-sectional area of the hole is the constant ($A$) (so we assume that the hole does not get any wider or narrower as the workers dig).

(:toggle hide show="Answer" box5:)

Let ($x$) be the distance down to to the layer of dirt currently being dug:

This is convenient because this is the distance that the current slice of dirt has to be lifted to get out of the hole. The area of the slice of dirt is ($A$), its thickness is ($dx$), and the density is ($\rho$), so we have

(:latex:) \begin{align*} dW &= \hbox{ weight of slice } \times \hbox{ distance slice moves }
&= (\rho \cdot dV) \cdot x
&= (\rho A \, dx) \cdot x
&= \rho A x \, dx. \end{align*} (:latexend:)

Note that ($x$) varies from 0 to ($D$) as the hole gets dug. Thus, the total work required to dig the hole is

(:latex:) \begin{align*} W &= \int dW
&= \int_{x=0}^D \rho A x \, dx
&= \frac{1}{2} \rho A D^2. \end{align*} (:latexend:)

To find the depth ($\tilde D$) where the work done is half, we set

(:latex:) \[ \int_{x=0}^{\tilde D} \rho A x \, dx = \frac{1}{2}W = \frac{1}{4} \rho A D^2. \] (:latexend:)

Computing the integral on the left, we find

(:latex:) \[ \frac{1}{2} \rho A \tilde D^2 = \frac{1}{4} \rho A D^2. \] (:latexend:)

Solving for ($\tilde D$) gives

(:latex:) \[ \tilde D = \frac{1}{\sqrt{2}} D. \] (:latexend:)

Example: gravel pyramid

Compute the amount of work required to build a pyramid of gravel. Assume the gravel is infinitesimal with weight density ($\rho$), and that the pyramid has a square base of side length ($s$), and height ($h$):

(:toggle hide show="Answer" box6:)

If we think of building the pyramid slice by slice, let ($y$) be the distance from the base of the pyramid to the slice. This is convenient because this is the distance that the slice must be lifted to be put in place. Also, let ($x$) be the side length of the slice:

Then using similar triangles, as shown on the right above, we find that

(:latex:) \[ \frac{x}{s} = \frac{h-y}{h}. \] (:latexend:)

So we find that

(:latex:) \[ x = \frac{h-y}{h}s. \] (:latexend:)

Thus, the volume of a slice is just the area ($x^2$) multiplied by the thickness ($dy$), and so we have

(:latex:) \begin{align*} dW &= \rho dV \, y
&= \rho (x^2 \, dy) \, y
&= \rho \left(\frac{h-y}{h}s\right)^2 y \, dy
&= \frac{\rho s^2}{h^2} (h-y)^2 y \, dy. \end{align*} (:latexend:)

Because ($y$) ranges from 0 to ($h$), we have

(:latex:) \begin{align*} W &= \int dW
&= \frac{\rho s^2}{h^2}\int_{y=0}^h (h-y)^2 y \, dy
&= \frac{\rho s^2}{h^2} \int_{y=0}^h (h^2y-2hy^2+y^3) \, dy
&= \frac{\rho s^2}{h^2} \left(\frac{1}{2}h^2y^2 - \frac{2}{3}hy^3 + \frac{1}{4}y^4\right) \bigg|_{y=0}^h
&= \frac{\rho s^2}{h^2} \left(\frac{1}{2}h^4 - \frac{2}{3}h^4 + \frac{1}{4}h^4\right)
&= \frac{\rho s^2}{h^2} \cdot \frac{1}{12}h^4
&= \frac{\rho s^2 h^2}{12}. \end{align*} (:latexend:)

Example: rope revisited

Consider the rope example from above, but this time suppose ($l$) total feet of rope are hanging from a ($h$) foot building, where ($l \geq h$), and let ($\rho$) be the weight density of the rope. Compute the work required to lift the rope to the top of the building.

For a different perspective, this time, use a work element which equals the amount of work required to lift an infinitesimal length of rope to the top of the building (this will depend on whether the infinitesimal length of rope is hanging at the beginning or is part of the coil at the bottom of the building). Then integrate along the entire length of rope.

(:toggle hide show="Answer" box7:)

Let ($L$) be the distance along the rope of the infinitesimal piece being considered:

So ($L$) is the distance that the infinitesimal piece must be lifted to get to the top of the building. The weight of the infinitesimal piece is density multiplied by length, and so the work element for a piece of rope which is hanging is

(:latex:) \[ dW = \rho L \, dL; \quad 0 \leq L \leq h. \] (:latexend:)

For a piece of rope which is part of the coil at the bottom, the distance it must be lifted is always ($h$), so the work element there is

(:latex:) \[ dW = \rho h \, dL; \quad h \leq L \leq l. \] (:latexend:)

So the work can be computed by integrating these work elements over their respective ranges and then adding:

(:latex:) \begin{align*} W &= \int dW
&= \int_{L=0}^h \rho L \, dL + \int_{L = h}^l \rho h \, dL
&= \rho \frac{1}{2} L^2 \bigg|_{L=0}^h + \rho h L \bigg|_{L=h}^l
&= \frac{\rho h^2}{2} + \rho h (l-h). \end{align*} (:latexend:)

Another way to think about this is to treat the coiled rope at the bottom of the wall as a single solid object. The rope in the coil has length ($l-h$), and so its weight is ($\rho(l-h)$). The distance the coil (as a unit) must be lifted is ($h$). It follows that the work to lift the coiled portion of the rope is ($\rho h(l-h)$), the result of the second integral above.
EXERCISES

    Consider a conical tank of height 10m. The vertex of the cone is at the bottom, and the base of cone (which is at height 10m) has radius 2m. Let ($\rho$) denote the weight density of water. The water inside the tank has height 4m. How much work would it take to pull all the water to the top of the tank? 