# On the description of particle system motion

Feng WU \*

CAS Key Laboratory of Mechanical Behavior and Design of Materials, Department of Modern Mechanics, University of Science and Technology of China, Hefei 23o026,China

Abstract Based on the concepts of infinitesimal and super real time-space composed of monads, the equations describing the particle flow are proposed.After the initial conditions are given,the state of the particle system at any time can be obtained by solving these equations.The physical properties of the granular matter, such as the moving velocity, the rotation angle, the angular velocity of rotation, the temperature, the pressure, the density, the mass, etc. at any time and space position are obtained. It is also to obtain that the translational motion is not dependent on rotation motion of the particles and can be separately analyzed. For a stationary particle system， the conditions that must be met by the force and force moment on the particles in the system are given. On this basis,the properties of the granular matter at rest can be further explored for.

Key words:granular flow, infinitesimal, monad, super real time-space

# 1 Introduction

Granular matter is common in nature, daily life and production technology, such as sand, soil, ice floes, snow in nature, food, sugar, salt in daily life, coal, ore, building materials in production technology. Some medicines and chemicals are also granular matter. There are also many discrete material systems such as bulk cargo transport, earth plate movement and the flow of vehicles on the road. They are also often treated as particle systems. It can be said that granular matter is the most abundant on the earth, one of the most familiar types of substances.

The annual production of cereals and other granular matter in the world is in the order of tens of billions of tons.The production，transportation，processing and storage of these materials consume about $10 \%$ of the energy of the earth each year.A deep understanding of granular matter will bring great benefits to the development of global industry and economy. At the same time, in order to prevent natural disasters such as debris flow, avalanche,ice floe,landslide, desertification and earthquake, it is also necessary to understand the movement law of granular matter.

For centuries,many famous scientists have studied the movement of granular matter. Coulomb [1] first proposed the relationship between the slope angle of the sand and the friction coefficient. Faraday (1831)[2] found that the vibration causes the particles to form convection and accumulate ,Reynolds (1885)[3] pointed out that if the particles are piled up in an elastic bag,any additional action will increase the volume of the particle system,which is called the Reynolds principle of pressure expansion.British scientist Roberts （1884） [4] first noticed the "granary efect" of granular matter.

Although，in order to applications,the industrial，engineering，and technical communities have studied the production, processing, and transportation of granular matter for a long time, the rise of physicists' interest in research of granular material has been nearly two or three decades.People have carried out experiments and simulations on various aspects of granular matter, and obtained many meaningful results.But their understanding of the laws of motion is still superficial. The basic theory of describing granular matter has not yet been established. Some problem of the most basic aspects of granular matter is still plaguing people. Regarding the understanding of granular matter, the famous theoretical physicistde Gennes [5] thinks that almost everything in this field remains to be understood. The famous physicist Kadanoff [6]said that ordinary fluid equations cannot be used to describe granular matter, and its rich and peculiar behavior is not well understood.

Granular material is a complex system. The study of granular matter not only has an important application background, but also a deep understanding of its state and motion law will promote the new development of physics. The work in this paper is based on the concepts of infinitesimal and super real time-space. And in the work a method to describe the movement of granular matter is proposed and the equations describing the law of the particle flow are obtained.

# 2Description of physical phenomena

# anditsmathematicalbasis

In order to describe the physical phenomenon in which the properties of physical objects change with time and space, the current physical practice is to divide the objects into small units in time and space $\Delta x , \Delta t$ ,and the properties of the objects in the small range are considered to be uniform.

Therefore, knowing the value of the physical quantity on every range $\Delta x , \Delta t$ ,the description completely of the physical quantity of the entire object with time and space is obtained. That is just the description of the physical properties of the object. Here, $\Delta x , \Delta t$ is the "sufficiently small" unit, the meaning of "suficiently small" is small enough to reflect the changes of physical quantity with time and space.

The mathematical abstraction of such a description method can be summarized as that the object is divided into many small units, each unit has a spatial scale $\Delta x$ ; the time size of the physical problem is also divided into many small units, and the scale .is $\Delta t$ . Then let $\Delta x  0 , \Delta t  0$ i.e. tend to time-space point $\left( x , t \right)$ to define the value of each function $f$ representing physical quantity at the point $\left( x , t \right)$ ， and further to define the various order time and spatial partial derivatives of each physical quantity function $f$ in the physical problem, such as:

$$
\frac { \partial f } { \partial t } , \frac { \partial f } { \partial x } , \frac { \partial ^ { 2 } f } { \partial ^ { 2 } t } , \frac { \partial ^ { 2 } f } { \partial ^ { 2 } x }
$$

etc. Their definitions are well known, for example

$$
\begin{array} { l } { \displaystyle \frac { \partial f } { \partial t } = \displaystyle \operatorname* { l i m } _ { \Delta t  0 } \frac { f ( t + \Delta t ) - f ( t ) } { \Delta t } } \\ { \displaystyle \frac { \partial f } { \partial x } = \displaystyle \operatorname* { l i m } _ { \Delta x  0 } \frac { f \big ( x + \Delta x \big ) - f \big ( x \big ) } { \Delta x } } \end{array}
$$

On the basis of(1), the high order partial derivatives of the function can be also defined. And the law of the motion properties of the object with time and space is described by the differential equations containing these derivatives.

Mathematically, definition(1) is based on the concept of limits (called $\delta \ – \varepsilon$ framework). In order to understand the mathematics meaning of(1), we must carefully examine the meaning of $\Delta x  0 , \Delta t  0$ . It is very clear to the physics researchers that $\Delta x  0 , \Delta t  0$ in (l), in physics, does not actually mean that it tends to be absolute zero,but rather that the physical properties of the object are uniform in a sufficiently small range $\Delta x , \Delta t$ (or the variation in this small range is negligible).

That is to say, when the physical properties of the object are uniform in a sufficiently small range $\Delta x , \Delta t$ , the mathematical analysis used to describe the motion is based on (1)， i.e. based on the limit concept under the $\delta \ – \varepsilon$ framework. And when the motion law of the object can be expressed by the mathematical equations based on (1), the motion properties of the object must be uniform over a sufficiently small range $\Delta x , \Delta t$ (or its variation within the range $\Delta x , \Delta t$ is negligible).

However, in the physical world, not all motions are that in a sufficiently small range $\Delta x , \Delta t$ the physical properties of motion are uniform. Some people may think that if the physical properties of the motion of the object in a range $\Delta x , \Delta t$ are not uniform, the segmentation can be made smaller,and a smaller one can always be obtained, so that the physical property of the motion in this smaller range is uniform. In fact, this opinion is not appropriate.

Because such a statement ignores a key fact that when describing the physical properties of an object's motion as a function of time and space, people divide time and space into many small units $\Delta x , \Delta t$ ，and the size of the small unit $\Delta x , \Delta t$ is corresponding with the specific physical problem studied. That is to say, it cannot be subjectively and randomly segmented by people. For example, the small unit scale in the flow around a cylinder in a trough is clearly quite different from the small unit scale in atmospheric physics. If people leave the specific physical problem and randomly select the scale of the small unit, there will be difficulties in physical description, such as excessive calculation.

Since in the specific physical problem, the scale of the small unit can be not taken subjectively small, but the small unit scale has objectivity, then it is possible that, in some physical problems, the physical properties of the object motion in the small unit range $\Delta x , \Delta t$ are not uniform. As it happens,turbulence,particle flows are such physical problems. The discontinuous medium of the particle assembly obviously has a non-uniform physical property in the small unit range $\Delta x , \Delta t$ ：

Scientific description of such physical problems is unreasonable in mathematics based still on (1). It is necessary to propose a mathematical concept that satisfies the variation of the values of the functions representing physical quantities within the small unit $\Delta x , \Delta t$ . This mathematics is a non-standard analysis proposed by American mathematician A.Robinson[7] in the 1960s.

In non-standard analysis, there are non-standard numbers in addition to the standard numbers,where infinitesimal $\varepsilon$ is an important non-standard number. Positive $\varepsilon$ is a number greater than zero but less than any positive real number. All real numbers are called standard numbers.Infinity $L$ is also a non-standard number, $a + \varepsilon , a \varepsilon , \varepsilon \varepsilon , L L \ldots$ all are non-standard numbers (where $a$ is any real number).

In the standard analysis，any time and space point can be expressed as $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ in a certain coordinate system, where $x _ { 1 } , x _ { 2 } , x _ { 3 } , t$ all are real numbers. These time and space points are geometric points,which are absolute geometric points with zero volume,usually called real points. For convenience of explanation, take one-dimensional space as an example.As is well known， the real number one-to-one corresponds to the point on the real axis of the one-dimensional one, i.e. any point A on the real axis corresponds to a real number $a$ ，whereas any real number $a$ must correspond to a point on the real axis (Fig.1). However, non-standard numbers cannot be matched by points on the one-dimensional real axis, and points on the real axis cannot be used to represent non-standard numbers.

![](images/1b878af8b7ae3e940b1a98710539f37740ccd2e28cb08f9ea292140260afc919.jpg)  
Figure 1 Real axis

For expressing the non-standard number, the real point A corresponding to real number $a$ should be expanded into a monad, which is a collection of numbers. Any one of monads contains only one real number $a$ ,and the remaining numbers in the monad are non-standard numbers.This monad is called $a$ -monad. The scale of the monad is infinitely small (Fig. 2).

Thus, the real number point is expanded to a monad and the real number axis is expanded to a super real number axis. The real number axis is composed of real points, which are absolute geometric points whose scale is zero. The ones which the super real axis is made from are monads. The monad is not an absolute geometric point. The scale of monad is infinitely small $\varepsilon$ ,which is greater than zero. Since the scale of an absolute geometric point is zero, the absolute geometric point has logically no interior. If you would like to take a physical small area as an absolute geometric point in mathematics, it is only reasonable that the physical quantity in this physical small area is uniform.However, if a physical small time-space region is mathematically abstracted as a monad, the scale (volume) of the monad is not zero but greater than zero, it is logically reasonable to say that the monad has its interior. Then the physical quantities are allowed to vary and be not uniform in this small region,i.e. in the monad mathematically.

![](images/4179e42881f61e0490272a12114d5a85d2fec77ca476e395c8b556571070b06c.jpg)  
Figure 2Monad (A stands for real number $a$ ）

Through the above analysis, we know that when the physical quantities in the small range $\Delta x , \Delta t$ are not uniform and vary, our description of the physical phenomena cannot be based on the standard analysis of(1), but based on non-standard analytical mathematics.

![](images/22032136848676e4d979a6c6290fbf3eeffe1de879cb42cbb692b382e1de8fed.jpg)  
Figure 3Hierarchy

It is easy to know that the monad is a lower level time-space. And Figure 3 shows three levels. The $B$ level is the O -monad in the $A$ level，the $B$ by comparison to $A$ is the lower level; the $C$ level is the O-monad in the $B$ level, which is one level lower than the $B$ level.For the convenience of description，a coordinate system $\left( x ^ { \prime } , t ^ { \prime } \right)$ is established in the monad, $x ^ { \prime }$ parallel to $x$ (same direction) (Fig.2).

So for both $\scriptstyle \left( x , t \right)$ and $\left( x ^ { \prime } , t ^ { \prime } \right)$ levels, there are

$$
d x = \varepsilon , d t = \varepsilon _ { t } \qquad d x ^ { \prime } = \varepsilon , d t ^ { \prime } = \varepsilon _ { t }
$$

But from a hierarchical perspective, the true lengths of $\left( d x ^ { \prime } , d t ^ { \prime } \right)$ in the level $\left( x , t \right)$ are(here $\stackrel { o } { \boldsymbol { \varepsilon } } , \stackrel { o } { \boldsymbol { \varepsilon } _ { t } }$ are the dimensionless infinitely small):

$$
\stackrel { o } { \varepsilon } ^ { 2 } = \stackrel { o } { \varepsilon } ^ { 2 } \varepsilon \stackrel { o } { \varepsilon } ^ { 2 } = \stackrel { o } { \varepsilon } _ { t } ^ { 2 } \varepsilon _ { t } ^ { 2 }
$$

Take a point $x$ in the real number axis.The numbers inside the $x$ -monad can be represented by coordinates $x ^ { \prime }$ ，called a internal point of the $x$ -monad. And use a function $f \left( x , x ^ { \prime } \right)$ to represent the function value on the inner point $x ^ { \prime }$ of the $x$ -monad. Can also be defined

$$
\frac { \partial f \left( x , t , x ^ { \prime } , t ^ { \prime } \right) } { \partial x } = \frac { f \left( x + \varepsilon _ { x } , t , x ^ { \prime } , t ^ { \prime } \right) - f \left( x , t , x ^ { \prime } , t ^ { \prime } \right) } { \varepsilon _ { x } }
$$

$$
\frac { \hat { \partial } f \left( x , t , x ^ { \prime } , t ^ { \prime } \right) } { \hat { \partial } t } { = } \frac { f \left( x , t + \varepsilon _ { t } , x ^ { \prime } , t ^ { \prime } \right) - f \left( x , t , x ^ { \prime } , t ^ { \prime } \right) } { \varepsilon _ { t } }
$$

For the four-dimensional space, there is similar discussion, i.e. the real point $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ is expanded into the monad $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ ，containing only one real number point $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ ： $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right)$ denotes the internal point $\left( x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right)$ of the monad $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ . The function value of the internal point $\left( x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right)$ of the monad $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right)$ isrepresented bya function $f { \big ( } x _ { 1 } , x _ { 2 } , x _ { 3 } , t , x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } { \big ) }$ , and so on.

In the standard analysis, the variables in the equations describing the motion law of the physical object based on(1） are the functions on the absolute point. In the non-standard analysis,the description of the physical motion law also requires the equations.In this case, the variables in the equations based on (4) (5) are often related to the whole monad, such as some average value.

# 3Description of granular motion

# (model of granular motion)

The time and space in which the granular matter is located is divided into small units $\Delta x , \Delta t$ . Particle motion is a physical phenomenon in which the motion properties (physical quantities) are variable and non-uniform in the small unit range $\Delta x , \Delta t$ . For example, the two small spheres are close to the point of contact, there is arbitrarily small $\Delta x , \Delta t$ around the contact point .And the inside of $\Delta x , \Delta t$ is non-uniform, there must be a space of density $\rho \neq 0$ and space of density $\scriptstyle { \rho = 0 }$ (i.e., no matter) (Fig. 4). Therefore, in mathematical abstraction, the movement of granular matter occurs in a super real time-space composed of the monads. That is, the particle matter flows out from a monad and flows into an adjacent monad.

![](images/60ed19d06c3038f9156f59ecafff6805e2dcffbb81411d328c31a8c01fb7e6e8.jpg)  
Figure 4Near the contact point of two ball

Regarding the translational motion of particles (or particle parts), they can be classified. Let there be a total of $k$ particles (or particle parts) in the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ .They are marked as $1 , 2 , \cdots k$ . And their movements can be classified as three types (Fig.5):

A. Movement purely inside the monad, such as particle "1"; B. The particles are on both sides of the interface between the adjacent monads. Such as particle"2", "3", "4". Particle "2" is flowing out of the monad, "3" flowing into the monad, and "4" can be regarded as "2", "3"in combination of two situations,both flowing into and out of the monad; C.The movement of particles (or parts of particles) at some time, such as $t ^ { \prime } = t _ { 1 } ^ { \prime }$ ” occurs with inflow (or outflow) of the monad. For example, particle ‘ $5 ^ { , 9 }$ is outside the monad before the time $t _ { 1 } ^ { \prime }$ ,and becomes $^ { \cdot \mathfrak { s } , \mathfrak { s } }$ type after the time $t _ { 1 } ^ { \prime }$ . About the movement of particle "6"， before the $t _ { 1 } ^ { \prime }$ , there are some materials of the particle in the monad, and at the time $t _ { 1 } ^ { \prime }$ particle "6" completely leaves the monad. In fact, the (C) type of motion is the movement being adjacent to starting and ending of the (B) type motion.

The parts of the same particle in the same space-monad have the same physical properties; while the physical properties of different particle in the same space-monad are different, which reflects the discontinuity of particle system motion.However, the physical properties of the same particle divided into two adjacent monads have the infinitesimal differences,which is consistent with the continuous motion of the material and is the continuous side of the particle flow.

![](images/f010a83f8c9b5c113d77d9d51a3c5602c9aff5b767c34babd461f183b35eccb9.jpg)  
Figure 5Classification of particle translational motions

On the particle flow, a certain limit is imposed on the particle characteristic size in the system.If the particle size $\ll \varepsilon$ (monad scale), the flow of a large number of such particles becomes a continuous medium motion, which can be solved by using of the hydrodynamic equations.

Now the particle flow we are going to study is not the above case. It is now to consider the system composed of a large number of particles，while the particle characteristic size $\sim \varepsilon$ or greater than $\varepsilon$ (monad scale). The movement of the aggregate system composed of a large number of such particles is called the particle flow or the movement of granular matter. What we want to describe is the movement of this situation.

For the sake of simplicity, it is assumed that the particle matter is an elastic substance,and the influence of a fluid such as air on the movement of the particles is ignored.

Here are a few useful concepts (1) The inner point of the monad

The super-real space is composed of the monads, and the monad is composed of the lower-level monads. The lower-level monad can be considered as a geometric point in a sense, that is, the physical properties inside the lower level monad are uniform. This low-level monad is called the inner point of a high-level monad.

The scales of the monad are infinitely small quantities $\varepsilon _ { 1 } , \varepsilon _ { 2 } , \varepsilon _ { 3 } , \varepsilon _ { t }$ , here $\ \varepsilon _ { i }$ is   
infinitely small in $i$ -direction of space, $\mathcal { E } _ { t }$ is the time infinitely small. The scale of   
the lower level monad is $\begin{array} { c c c } { { } } & { { { \scriptstyle o } ^ { 2 } } } & { { { \scriptstyle o } ^ { 2 } } } \\ { { } } & { { \mathcal { E } _ { 1 } \mathcal { E } _ { 1 } , \mathcal { E } _ { 2 } \mathcal { E } _ { 2 } , \mathcal { E } _ { 3 } \mathcal { E } _ { 3 } , \mathcal { E } _ { t } \mathcal { E } _ { t } } } \end{array}$ . The volume of space monad is $\mathscr { E } _ { 1 } \mathscr { E } _ { 2 } \mathscr { E } _ { 3 }$ , and the volume of lower-level space monad is $\left\{ \begin{array} { l } { { \left( \begin{array} { l l l } { o } & { o } & { o } \\ { \mathcal { E } 1 \mathcal { E } 2 \mathcal { E } 3 } \end{array} \right) } ^ { 2 } \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } } \end{array} \right.$

Therefore, the number of inner-points in the space monad is

$$
N _ { o } = { \frac { \varepsilon _ { 1 } \varepsilon _ { 2 } \varepsilon _ { 3 } } { \varepsilon _ { 1 } \varepsilon _ { 2 } \varepsilon _ { 3 } { \left( \begin{array} { l } { o } \\ { \varepsilon _ { 1 } \varepsilon _ { 2 } \varepsilon _ { 3 } } \\ { } \end{array} \right) } ^ { 2 } } } = { \left( \begin{array} { l } { o } \\ { \varepsilon _ { 1 } \varepsilon _ { 2 } \varepsilon _ { 3 } } \\ { } \end{array} \right) } ^ { - 2 }
$$

Similarly the number of inner-points in the time-space monad is

$$
N _ { o } ^ { \prime } = \frac { \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } } { \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } \left( \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } \right) ^ { 2 } } = \left( \begin{array} { c c c } { o } & { o } & { o } \\ { \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } } \\ { \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } \left( \mathcal { E } _ { 1 } \mathcal { E } _ { 2 } \mathcal { E } _ { 3 } \mathcal { E } _ { t } \right) ^ { 2 } } \end{array} \right) ^ { - 2 }
$$

Among them, $\mathbf { \xi } _ { \mathcal { E } _ { i } , \mathcal { E } _ { t } } ^ { o }$ are the dimensionless infinitely small, $\stackrel { o } { L } _ { i } , \stackrel { o } { T }$ dimensionless infinite.

Take

$$
\stackrel { o } { L } _ { i } \varepsilon _ { i } = 1 , \stackrel { o } { T } \varepsilon _ { t } = 1
$$

(2) Particle and the element of a particle

System is composed of a large number of particles, its motion is the object of our research; the particles move between the monads. And we call the particle material at an inner point of the space monad as the element of a particle. Since the inner point of the monad is a lower level monad, we believe that the particle material is evenly filled in the inner point of the space monad. That is,the density of the particle material has only one value for one inner point, i.e. the density at the inner point is uniform. And

so are other physical properties.

In space, the element of a particle is always at an inner point of the space monad, moving from one inner point to another.

(3) The mass inner point and no mass inner point

At a time-space $\left( \varepsilon _ { 1 } , \varepsilon _ { 2 } , \varepsilon _ { 3 } , \varepsilon _ { t } \right)$ ,the total number of inner-points is $N _ { o } ^ { \prime }$ . Any one of these $N _ { o } ^ { \prime }$ inner points which is not occupied by the particle matter is called as no-mass inner point.Otherwise,it is called as the mass inner point.

Between $t \to t + \varepsilon _ { t }$ ,if an element of particle moves inside a monad (including stopping at a space inner point), the number of mass inner points contributed by the element of particle is:

$$
\frac { \varepsilon _ { t } } { \varepsilon _ { t } \varepsilon _ { t } } { = } \frac { T } { \varepsilon _ { t } } { = } \mathcal { E } _ { t } ^ { ' }
$$

If the time for which the element of particle staysin the monad i $\left( t , t ^ { \prime } { = } 0 \to t , t ^ { \prime } { = } t ^ { \prime } \right)$ ， the number of mass inner points contributed to the monad by the element of particle is:

$$
\frac { t ^ { \prime } \mathcal { E } _ { t } } { \varepsilon _ { t } \mathcal { E } _ { t } } = \frac { t ^ { \prime } } { \mathcal { E } _ { t } }
$$

An element of particle flows out of the monad, and there is a corresponding number of mass inner points in the monad flowing out of the monad; when an element of particle flows into the monad, there is a corresponding number of mass inner points into the monad also.And let an element of a particle flow out of(into) a monad at $\left( t , t ^ { \prime } \right)$ , the corresponding number of mass inner points flowing out of(into) the monad is

$$
\frac { \left( T - t ^ { \prime } \right) \mathcal { E } _ { t } ^ { \mathrm { ~ ~ 2 ~ } } } { \varepsilon _ { t } \mathcal { E } _ { t } } = \frac { T - t ^ { \prime } } { \varepsilon _ { t } }
$$

Let there be $\Delta N$ elements of particle flowing out of the monad $\left( x + \varepsilon \right)$ (Fig. 6). They flow out at interval of the $\cdot \left( t , t ^ { \prime } = 0 \right) \to \left( t , t ^ { \prime } = \alpha ^ { \prime } \right)$ （204号

![](images/726a39ce0f048555d86ac2fbf9634c1072b4fb39324a40d06b12767d9413df01.jpg)  
Figure 6Elements of particle flowing between monads

Then at interval of the $( t , t ^ { \prime } = 0 )  ( t , t ^ { \prime } = \alpha ^ { \prime } )$ the total number of the mass inner points flowing out from the monad $\left( x + \varepsilon \right)$ is

$$
\Delta N ^ { \prime } = \int _ { 0 } ^ { \alpha ^ { \prime } } \frac { T - t ^ { \prime } } { \varepsilon _ { t } } d n
$$

In case of equal sections and equal velocity of elements of particle，you have $d n = a d t ^ { \prime }$ ,here $a$ is a constant.

Then

$$
\Delta N ^ { \prime } = \frac { \left( T - \frac { 1 } { 2 } \alpha ^ { \prime } \right) } { \varepsilon _ { t } } \Delta N
$$

Generally speaking, there is: $\Delta N ^ { \prime } = J \left( \Delta N \right)$

(4)The average over the monad and the average over the substance of particle Taking the physical quantity $f \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right)$ , its average over monad is

$$
\widetilde { f } = \widetilde { f } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right) = \frac { 1 } { L _ { 1 } } \int _ { 0 } ^ { L _ { 1 } } d x _ { 1 } ^ { \prime } \frac { 1 } { L _ { 2 } } \int _ { 0 } ^ { L _ { 2 } } d x _ { 2 } ^ { \prime } \frac { 1 } { L _ { 3 } } \int _ { 0 } ^ { L _ { 3 } } d x _ { 3 } ^ { \prime } \frac { 1 } { T } \int _ { 0 } ^ { T } d t ^ { \prime } f
$$

Let $B$ be a collection of elements of particles (a collection of particle substances), and $B$ 's contribution to the average over the monad is

$$
\widetilde { f } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = \frac { 1 } { L _ { 1 } L _ { 2 } L _ { 3 } T } { \int { f d x _ { 1 } ^ { \prime } d x _ { 2 } ^ { \prime } d x _ { 3 } ^ { \prime } d t ^ { \prime } } }
$$

There is also average value as follows:

$$
\widetilde { f } ^ { { \cal B } } = \widetilde { f } ^ { { \cal B } } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , { \cal B } \right) = \frac { 1 } { { \cal V } \left( { \cal B } \right) } \int _ { \cal B } f d x _ { 1 } ^ { \prime } d x _ { 2 } ^ { \prime } d x _ { 3 } ^ { \prime } d t ^ { \prime }
$$

$V { \big ( } B { \big ) }$ is time-space volume of $B$ .This is the average value of $f$ over $B$ ， called as the average value of $f$ over the collection of related substances in time-space.

It is available from (16),(17) that

$$
\begin{array} { r } { { N _ { 0 } } ^ { \prime } \tilde { f } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = N ^ { \prime } \left( B \right) \widetilde { f } ^ { B } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) } \end{array}
$$

Where $N ^ { \prime } \big ( B \big )$ is the number of mass inner points by $B$ (5) Strain, stress and elastic force in the particle

The space in which the particle system moves is composed of the space monads, and the movement of the particles is between the monads. The part of the particle $l$ in the space monad $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ is marked as $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } , l \right)$ $\left( \operatorname { o r } l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right) \right)$ ，and its average velocity over the substances is $U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , l \right)$ 、The velocities of all elements of particle $l$ in the same monad are $U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , l \right)$

According to the usual practice of elastic mechanics, the strain and stress of the particle $l$ can be defined as follows.

Displacement change

$$
\Delta r _ { i j } ^ { * } = \Big [ U _ { i } \big ( x _ { i } , x _ { j } + \varepsilon _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) - U _ { i } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Big ] \varepsilon _ { t } \varepsilon _ { t } ^ { 2 }
$$

Strain

$$
e _ { i i } ^ { * } \left( t , t ^ { \prime } \right) = \frac { \Delta r _ { i i } ^ { * } } { \varepsilon _ { i } } = \left[ U _ { i } \left( x _ { i } + \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - U _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \right] \frac { \varepsilon _ { t } \varepsilon _ { t } } { \varepsilon _ { i } }
$$

$$
\gamma _ { i j } ^ { * } \left( t , t ^ { \prime } \right) = \frac { \Delta r _ { i j } ^ { * } } { \varepsilon _ { j } } + \frac { \Delta r _ { j i } ^ { * } } { \varepsilon _ { i } } = \left[ U _ { i } \left( x _ { i } , x _ { j } + \varepsilon _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - U _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \right] \frac { \varepsilon _ { t } \varepsilon _ { t } } { \varepsilon _ { j } }
$$

$$
+ \Big [ U _ { j } \left( x _ { i } + \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - U _ { j } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] \frac { \mathscr { E } _ { t } \mathscr { E } _ { t } } { \mathscr { E } _ { i } }
$$

Consider pre-strain

$$
\begin{array} { l } { { e _ { i i } \left( t , t ^ { \prime } \right) = e _ { i i } ^ { o } \left( t , t ^ { \prime } \right) + e _ { i i } ^ { \ast } \left( t , t ^ { \prime } \right) } } \\ { { \ } } \\ { { \gamma _ { i j } \left( t , t ^ { \prime } \right) = \gamma _ { i j } ^ { o } \left( t , t ^ { \prime } \right) + \gamma _ { i j } ^ { \ast } \left( t , t ^ { \prime } \right) } } \end{array}
$$

Similarlythereis

$$
\theta = e _ { 1 1 } + e _ { 2 2 } + e _ { 3 3 }
$$

Then the stress is

$$
\begin{array} { l } { \sigma _ { i i } = \lambda \theta + 2 \mu e _ { i i } } \\ { \phantom { \frac { 1 } { 2 } } } \\ { \tau _ { i j } = \mu \gamma _ { i j } } \end{array}
$$

Here $\lambda , \mu$ are Lame constants.

The elastic force is equal to the stress multiplied by the corresponding area.

Due to the discontinuity, this corresponding area must be defined and sought for.   
The area is given below. For example, the particlel moves through plane A-A. The   
number of elements of particle passing through the plane A-A within $( t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } )$   
is $\Delta n$ ,the average number of elements of particle passing through A-A in unit time   
is $\frac { \Delta n } { \int \limits _ { \mathrm { ~ \it ~ { ~ o ~ } ~ } ^ { 2 } } ^ { \mathrm { ~ ~ \it ~ { ~ o ~ } ~ } ^ { 2 } } }$ ． And the time interval, in which one element of particle passes A-A，is dt'εt $o ^ { 2 }$ （204号 $\frac { \ \mathcal { E } _ { i } \ \mathcal { E } _ { i } } { U _ { i } \left( t , t ^ { \prime } \right) }$ . Hence the number of elements of particle passing through A-A during （24号

thattime intervalis

$$
\frac { \varepsilon _ { i } \varepsilon _ { i } } { U _ { i } \left( t , t ^ { \prime } \right) } \frac { \Delta n } { d t ^ { \prime } \varepsilon _ { t } ^ { 2 } }
$$

These elements of particle are just the elements of particle in the $l$ -cross section on the A-A plane. This cross section consists of these elements of particle (a layer of

elements of particle). Obviously the area of this layer of elements of the particle is

$$
s _ { i } \left( t , t ^ { \prime } + d t ^ { \prime } \right) = \frac { \varepsilon _ { i } \varepsilon _ { i } } { U _ { i } \left( t , t ^ { \prime } \right) } \frac { \Delta n } { { d t ^ { \prime } } \varepsilon _ { t } } { \left( \varepsilon _ { i } \varepsilon _ { i } \right) } ^ { 2 } = \frac { 1 } { U _ { i } \left( t , t ^ { \prime } \right) } \frac { \Delta n } { { d t ^ { \prime } } \varepsilon _ { t } } { \left( \varepsilon _ { i } \varepsilon _ { i } \right) } ^ { 3 }
$$

Note that the values of the physical quantities (density, average velocity) on two sides of A-A plane may be different, so there are two areas on two sides of A-A plane . We take the smaller of the two as the area in the calculation of the elastic force.

# 4One kinematic condition

Let $U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right)$ be the velocity of movement of the granular matter(which consists of a large number of elements of particle,and the element of particle is indicated as $\left( x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , x _ { 3 } ^ { \prime } , t ^ { \prime } \right) )$ . Its average over monad is

$$
\widetilde { U _ { i } } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t \right) = \frac { 1 } { L _ { 1 } L _ { 2 } L _ { 3 } T } \iiint U _ { i } d x _ { 1 } ^ { \prime } d x _ { 2 } ^ { \prime } d x _ { 3 } ^ { \prime } d t ^ { \prime }
$$

Put case that there is only one element of particle moving in the monad. Then have

$$
\widetilde { U _ { i } } = \frac { 1 } { L ^ { 3 } T } \int U _ { i } \left( t ^ { \prime } \right) d t ^ { \prime } \varepsilon _ { 1 } \varepsilon _ { 2 } \varepsilon _ { 3 } = \frac { 1 } { \underset { L } { \overset { o ^ { 3 } } { \varepsilon ^ { 3 } } } \left( \underset { \mathcal { E } _ { 1 } } { \overset { o } { \varepsilon } } \varepsilon _ { 2 } \varepsilon _ { 3 } \right) ^ { - 1 } } \frac { 1 } { T } \int U _ { i } \left( t ^ { \prime } \right) d t ^ { \prime } = = \frac { 1 } { N _ { o } T } \intop _ { s } d x _ { i } ^ { \prime } \frac { \varepsilon _ { i } ^ { \prime } } { \varepsilon _ { t } } \underset { \mathcal { E } _ { t } } { \overset { . } { \varepsilon } } \left( x _ { i } ^ { \prime } \right) \underset { \mathcal { E } _ { t } } { \overset { . } { \varepsilon } } \left( x _ { i } ^ { \prime } \right)
$$

Among them, Sdxrepresents theintegralaongthe motiontrajectoryfthe element of particle,and the relationship is also used here: U;(t')dt'ε， = dx' εi 02 Then there is, $\widetilde { U } _ { i } = \frac { 1 } { N _ { o } T } \frac { \varepsilon _ { i } } { \varepsilon _ { t } ^ { \ o } } \Big ( x _ { i , e } ^ { \prime } - x _ { i , b } ^ { \prime } \Big )$ (30)

Here $x _ { i , e } ^ { \prime } , x _ { i , b } ^ { \prime }$ are the lower-level coordinates of the end point and beginning point of

the motion trajectory of the element of particle respectively

(30) is the contribution of only one element motion to the average over the monad. There is now an assembly of elements of particle $B$ in the monad, which contributes to the average over the monad by

$$
\widetilde { U _ { i } } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = \frac { 1 } { N _ { o } T } \frac { \varepsilon _ { i } } { \varepsilon _ { t } ^ { \ 2 } } \sum _ { B } \left( x _ { i , e } ^ { \prime } - x _ { i , b } ^ { \prime } \right)
$$

Here, the meaning of ∑ is to sum over all the elements of particle in the $B$ ： By (18), there is

$$
N _ { o } ^ { \prime } \widetilde { U _ { i } } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = N ^ { \prime } \left( B \right) U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right)
$$

$N ^ { \prime } \big ( B \big )$ is the number of mass inner points within the assembly $B$ . Then there is

$$
\frac { N ^ { \prime } \big ( B \big ) } { N _ { o } ^ { \prime } } U _ { i } \big ( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \big ) = \frac { 1 } { N _ { o } T } \frac { \varepsilon _ { i } } { \varepsilon _ { t } ^ { \circ } } \sum _ { B } \Big ( x _ { i , e } ^ { \prime } - x _ { i , b } ^ { \prime } \Big )
$$

![](images/cc8c2f57d1000d33cb7ffcf8d9bd0b2b8f8de5e76a0035f03b685568698dcba0.jpg)  
Figure 7Definition of surface $i ^ { + } , i ^ { - }$

For the space monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ ，Figure 7 shows the $x _ { i }$ - direction. Then the surface $x _ { i }$ is taken as the surface $i ^ { - }$ and the surface $x _ { i } + \varepsilon _ { i }$ as the surface $i ^ { + }$ .For a monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ , the coordinates of the start or end points of one element motion trajectory on the surface $i ^ { - }$ are all zero; the coordinates of the start point or the end point on the surface $i ^ { + }$ are infinity $L _ { \phantom { } _ { i } }$ . The start point of one element of particle is located on the surface $i ^ { + }$ ,it is considered to flow into the monad through the surface $i ^ { + }$ ． The element end point is located on the surface $i ^ { + }$ ，it is considered that the element is flowing out through the surface $i ^ { + }$ ,and the rest direction is analogous.

The right summation in(33) can be written as

$$
\sum _ { B } \Bigl ( x _ { i , e } ^ { \prime } - x _ { i , b } ^ { \prime } \Bigr ) = \sum _ { x _ { i , e } ^ { \prime } ( B ) \mathrm { f i n } . } x _ { i , e } ^ { \prime } - \sum _ { x _ { i , b } ^ { \prime } ( B ) \mathrm { f i n } . } x _ { i , b } ^ { \prime } + N _ { i ^ { + } } ^ { o u t } L _ { i } - N _ { i ^ { + } } ^ { i n } L _ { i }
$$

Then (33) can be written as (by using εi Li =1 )

$$
\frac { N ^ { \prime } \big ( B \big ) } { N _ { o } ^ { \prime } } U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = \frac { \varepsilon _ { i } } { \varepsilon ^ { 2 } } \frac { 1 } { N _ { o } T } \Bigg ( \sum _ { x _ { i , e } ^ { \prime } ( B ) \mathrm { f i n } . } x _ { i , e } ^ { \prime } - \sum _ { x _ { i , e } ^ { \prime } ( B ) \mathrm { f i n } . } x _ { i , b } ^ { \prime } \Bigg ) + \frac { \varepsilon _ { i } } { \varepsilon ^ { 2 } } \frac { 1 } { N _ { o } T } \Big ( N _ { i ^ { + } } ^ { o u t } - N _ { i ^ { + } } ^ { i n } \Big )
$$

Here $\sum _ { , e ^ { \prime } ( B ) \mathrm { f i n . } } , \sum _ { x _ { i , b } ^ { \prime } ( B ) \mathrm { f i n . } }$ are the sums of the terms having finite coordinates of the end x   
point and beginning point of elements of particle respectively. And $N _ { i ^ { + } } ^ { o u t } , N _ { i ^ { + } } ^ { i n }$ are the   
numbers of the elements of particle flowing out and in the monad through the surface   
$i ^ { + }$ respectively.

It is easily to know that only (35) is independent kinematic condition.

Let $m _ { o }$ ,related to density, be the mass of one element of particle, $m _ { e } , m _ { b }$ be the mass of the $B$ at end time and the starting time respectively, $x _ { i , e } ^ { \prime c } , x _ { i , b } ^ { \prime c }$ be the coordinates of the end point and the beginning point of the centroid of the $B$ ，then there is

$$
\frac { N ^ { \prime } ( B ) } { N _ { o } ^ { \prime } } U _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , B \right) = \frac { \varepsilon _ { i } } { \varepsilon _ { i } } \frac { 1 } { N _ { o } T m _ { o } } \big ( m _ { e } x _ { i , e } ^ { \prime c } - m _ { b } x _ { i , b } ^ { \prime c } \big ) + \frac { \varepsilon _ { i } } { \varepsilon _ { i } } \frac { 1 } { N _ { o } T } \big ( N _ { i ^ { + } } ^ { o u t } - N _ { i ^ { + } } ^ { i n } \big )
$$

# 5 Translational movement (A) particle interaction

First there is the discussion of the motion of the "2" type in Fig. 5.

The particle $l$ leaves the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ and enters the $\begin{array} { r } { \mathrm { m o n a d } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right) \left( \mathrm { F i g . } 8 \right) \mathrm { . } \operatorname { L e t t h e } \mathrm { v e l o c i t y } U _ { s } \left( x _ { i } \left( q \right) , x _ { j } \left( q \right) , x _ { k } \left( q \right) , t , t ^ { \prime } , l \right) } \end{array}$ be given. Among them, $( q )$ represents six adjacent monads or the six interfaces of the monad $\begin{array} { r } { \big ( x _ { i } , x _ { j } , x _ { k } \big ) , \mathrm { h e r e } q = \big ( 1 , 2 , \cdots 6 \big ) \mathrm { o r } q = \big ( i ^ { - } , j ^ { - } , k ^ { - } , i ^ { + } , j ^ { + } , k ^ { + } \big ) . \mathrm { A n d } } \end{array}$ $\left( { x } _ { i } , { x } _ { j } , { x } _ { k } , { x } _ { i } ^ { \prime } , { x } _ { j } ^ { \prime } , { x } _ { k } ^ { \prime } \right)$ will be abbreviated to $\left( x , x ^ { \prime } \right)$ ．And following the steps below ,tl translational motion of $l \left( x _ { i } , x _ { j } , x _ { k } \right)$ in the monad can be solved.

![](images/46093a5ba2d6c51b41d8d05a83264f16a45d864ea6335859cbd919adeb45c04c.jpg)  
Figure 8Particle $l$ moving in the type of "2"

(1) By the velocity $U _ { s } \left( x _ { i } \left( q \right) , x _ { j } \left( q \right) , x _ { k } \left( q \right) , t , t ^ { \prime } , l \right)$ in the adjacent monads, from the relationships (25), (26) the elastic deformation stress in $l$ ， i.e. $\sigma _ { s s } \left( x , t , t ^ { \prime } , l \right)$ $\tau _ { s p } \left( x , t , t ^ { \prime } , l \right)$ , are obtained. Because $s _ { i } \left( x , t , t ^ { \prime } , l \right)$ is known thereby further the elastic force $F _ { s } \left( x , t , t ^ { \prime } , l \right)$ is obtained.

(2) The total force on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ exerted by the other particles (or particle parts) in the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ is $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ ,then there is

$$
\sum _ { l } { f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } = 0
$$

(3) According to the conservation of momentum, there is a relationship

$$
\Big [ F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) + f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] { d t ^ { \prime } } \varepsilon _ { t } ^ { 2 }
$$

$$
\begin{array} { l } { { = U _ { s } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) m \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) } } \\ { { \ } } \\ { { \displaystyle - U _ { s } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) m \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) } } \\ { { \ } } \\ { { \displaystyle + \delta m ^ { o u t } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \Big ) U _ { s } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) } } \\ { { \ } } \\ { { \displaystyle - \sum _ { q = 1 } ^ { 6 } \delta m _ { q } ^ { i n } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \Big ) U _ { s } \Big ( x _ { i } \big ( q ) , x _ { j } \big ( q \big ) , x _ { k } \big ( q \big ) , t , t ^ { \prime } , l \Big ) } } \end{array}
$$

Ignoring high-order small quantities, there is:

$$
\begin{array} { r l } & { \Big [ F _ { s } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) + f _ { s } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Big ] d t ^ { \prime } \varepsilon _ { t } ^ { 2 } } \\ & { } \\ & { = \Big [ U _ { s } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) - U _ { s } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Big ] m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } \end{array}
$$

Among them

$$
\begin{array} { c } { { m \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) = m \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) + \delta m ^ { i n } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \Big ) } } \\ { { { } } } \\ { { - \delta m ^ { o u t } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \Big ) \qquad \quad ( 3 9 ) } } \end{array}
$$

$$
\delta m ^ { i n } = \sum _ { q = 1 } ^ { 6 } \delta m _ { q } ^ { i n } , \delta m ^ { o u t } = \sum _ { q = 1 } ^ { 6 } \delta m _ { q } ^ { o u t }
$$

By (38) can obtained

$$
F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) + f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \sim m \sim \varepsilon ^ { 3 }
$$

(4)Now give the method to get at $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ ， Let $\begin{array} { r } { \int _ { s } ^ { * } \Big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) = - F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } \end{array}$ When, for a certain particle $l ^ { \prime }$ ， $F _ { \mathrm { { } } s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right) = 0$ ， Let $f _ { s } ^ { * } \left( x _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } , t , t ^ { \prime } , l ^ { \prime } \right) = m \left( x _ { i } , \boldsymbol { x } _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right) \left[ a _ { o } \right]$ Here the $\left[ a _ { o } \right]$ is acceleration dimension.

$$
\sum _ { l = 1 } ^ { k } \boldsymbol { f } _ { s } ^ { * } \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } , t , t ^ { \prime } , l \right) = \delta _ { s } \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } , t , t ^ { \prime } \right)
$$

Then $\delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \right)$ will be allocated by size of $f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ ,i.e. let $\left| f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \right| = d _ { o } \alpha _ { l } , \sum _ { l = 1 } ^ { k } \alpha _ { l } = \alpha$ （20 and take $\delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \frac { \delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \right) } { \alpha } \alpha _ { l } .$ (44)

Obviously $\delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \right) = \sum _ { l = 1 } ^ { k } \delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$

Here $d _ { o }$ is a positive constant.

Then take the amendment to $f _ { s } ^ { * }$

$$
f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)
$$

Obviously there is $\sum _ { l = 1 } ^ { k } { f _ { s } \left( { x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l } \right) } = 0$

(47) That is, $f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ is corrected to $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ by $\delta _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \ . \quad \mathrm { S u c h } \ f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ obtained can be taken as the total force on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ exerted by other particles (or particle parts)within the monad .

(5)The velocity $U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ will be obtained when substituting $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ into (38).

And in the formula (38), $m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } { + } d t ^ { \prime } , l \big )$ is required,which will be discussed in the next section.

(6) Repeat the above steps to find the velocity of $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ and the internal forces (the total force on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ （204号 exerted by the other particles in the monad) at any time.

About interior motion purely ("1" type in Fig.5)

With the interior motion purely of the particle $l ^ { \prime } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \big )$ , known the initial velocity $U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right)$ ,let

$$
f _ { s } ^ { * } \left( { x } _ { i } , { x } _ { j } , { x } _ { k } , t , t ^ { \prime } , l ^ { \prime } \right) = m \big ( x _ { i } , { x } _ { j } , { x } _ { k } , t , t ^ { \prime } , l ^ { \prime } \big ) \big [ a _ { o } \big ]
$$

Then to correct $\begin{array} { r l r } { f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } & { { } } & { \left( l = 1 , 2 , \cdots l ^ { \prime } \cdots k \right) } \end{array}$ and get at each $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ , included $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right)$ . So the acceleration of the internal motion $a _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right)$ can be found, and so the next moment velocity $U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l ^ { \prime } \right)$ . In order to proceed to the next step, let

$$
f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l ^ { \prime } \right) = f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right)
$$

Repeatedly you can get at the velocity $U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ^ { \prime } \right)$ and internal force on $l ^ { \prime }$ at any time.

About motion in the "5" type (Fig.5)

The particle "5" completely outside the studied monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ enters the monad at some time between $( t ^ { \prime } = 0  t ^ { \prime } = T )$ ）.Let there be not $^ { 6 6 } 5 ^ { , 9 }$ in the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ before the time $t ^ { \prime } = t _ { 1 } ^ { \prime }$ ，while $t ^ { \prime } = t _ { 1 } ^ { \prime }$ particle “ $5 ^ { , 9 }$ starts to enter the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ from the $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right)$ monad. Because,at the time $t ^ { \prime } = t _ { 1 } ^ { \prime }$ ,the mass of particle "5"isverysmall in the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ ，it can beset $\mathrm { t h a t } U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = t _ { 1 } ^ { \prime } , 5 \right) = U _ { s } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = t _ { 1 } ^ { \prime } , 5 \right) .$ That is,

$$
F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = t _ { 1 } ^ { \prime } , 5 \right) = 0
$$

So let $f _ { s } ^ { * } \left( x _ { i } , x _ { j } , x _ { k } , t , t _ { 1 } ^ { \prime } , 5 \right) = m \left( x _ { i } , x _ { j } , x _ { k } , t , t _ { 1 } ^ { \prime } , 5 \right) \left[ a _ { o } \right]$

Then by the amendment to $f _ { s } ^ { * }$ ，you can get at $f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t _ { 1 } ^ { \prime } , 5 \right)$ ，by (38) the velocity $U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t _ { 1 } ^ { \prime } + d t ^ { \prime } , 5 \right) \mathrm { w i l l } \mathrm { b e }$ obtained. And further

$F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t _ { 1 } ^ { \prime } + d t ^ { \prime } , 5 \right)$ can be obtained. Then you can follow the previous method.

# 6Translational movement (B) Formulation of Equations

Assuming that the particle $l$ flows out of the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ and enters the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right) ( \mathrm { F i g . } 9 )$ . Between $t ^ { \prime }  t ^ { \prime } { + } d t ^ { \prime }$ , the part of the flow out of the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ (flow into the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right) \rangle$ ) is denoted as $A$ , and the mass of the outflow is $\delta m _ { 1 } ^ { o u t } ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l )$ , and likewise, the part of the flow into the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right)$ (from the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right) )$ is denoted as $\mathcal { A } ^ { \prime }$ ,the mass of the inflow into the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right)$ is $\delta m _ { 4 } ^ { i n } \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \big ) .$

![](images/b6401661638add921dee3d1e579932aa2aa60e46f20243773b2d1fe704a2b5c7.jpg)  
Figure 9Movement of the particle $l$ between two monads

The unknown quantities required are the quantities at the next time $t ^ { \prime } + d t ^ { \prime }$ . For the $l -$ movement between two monads the unknown quantities are as below.

On $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$ there are pressure,density,temperature,velocity,i.e.   
$\begin{array} { r l } & { p \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , \rho \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , } \\ & { T \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , U _ { s } \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } \end{array}$ On $l \left( x _ { i } , x _ { j } , x _ { k } \right)$ there are also pressure,density,temperature,velocity,i.e.   
$\begin{array} { r l } & { p \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , \rho \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , } \\ & { T \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) , U _ { s } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } \end{array}$ Moreover, $N _ { i ^ { + } } ^ { i n } ( A ^ { \prime } ) , \quad N _ { i ^ { - } } ^ { o u t } ( A )$ .So there are total fourteen quantities unknown.

The equations for solving these unknowns are given below.

The equations for $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$ are: the energy equation, the momentum equations, the equation of state and the pressure formula at $t ^ { \prime } + d t ^ { \prime }$ ·

The equations for $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ are also: the energy equation, the momentum equations, the equation of state and the pressure formula at $t ^ { \prime } + d t ^ { \prime }$ ·

Moreover there are the energy equation of $A$ and the mass conservation equation for $A$ There are 14 equations above, so the problem can be solved.

Now list these 14 equations below.

The energy equation on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$

$$
\begin{array} { r l } & { m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) u \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) - m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) u \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) } \\ & { - \delta m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l \big ) u \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) = Q ^ { i n } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l \big ) } \\ & { \qquad - p \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Bigg [ \frac { m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } { \rho \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } - \frac { m \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) } { \rho \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) } \Bigg ] } \end{array}
$$

The momentum equation on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$

$$
\begin{array} { r l } & { \Big [ F _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) + f _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] d t ^ { \prime } \varepsilon _ { t } ^ { 2 } } \\ & { \qquad = \Big [ U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) - U _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] m \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) } \end{array}
$$

The state equation on $l \left( \boldsymbol { x } _ { i } , \boldsymbol { x } _ { j } , \boldsymbol { x } _ { k } \right)$ at $t ^ { \prime } { + } d t ^ { \prime }$

$$
\frac { 1 } { \rho \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) } = \frac { 1 } { \rho _ { o } \left( T _ { o } , 0 \right) } \Big [ 1 + \alpha \Big ( T \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) - T _ { o } \Big ) - \kappa p \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) \Big ]
$$

The pressure formula on $l \left( { x _ { i } , x _ { j } , x _ { k } } \right)$ at $t ^ { \prime } + d t ^ { \prime }$

$$
p \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) = - \frac { 1 } { 3 } \big ( \sigma _ { 1 1 } + \sigma _ { 2 2 } + \sigma _ { 3 3 } \big ) \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big )
$$

The energy equation on $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$

$$
\begin{array} { r l r } & { } & { m \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) u \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) - m \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) u \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , } \\ & { } & { \qquad - \delta m \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l \Big ) u \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) = Q ^ { i n } \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l \Big ) } \end{array}
$$

$$
- p \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) \Bigg [ \frac { m \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) } { \rho \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \Big ) } - \frac { m \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) } { \rho \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \Big ) } \Bigg ]
$$

The momentum equation on $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$

$$
\begin{array} { r l } & { \Big [ F _ { s } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) + f _ { s } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] d t ^ { \prime } \varepsilon _ { t } ^ { 2 } } \\ & { \quad = \Big [ U _ { s } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) - U _ { s } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] m \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) } \end{array}
$$

The state equation on $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$ at $t ^ { \prime } + d t ^ { \prime }$

$$
\frac { 1 } { \rho \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) } = \frac { 1 } { \rho _ { o } \left( T _ { o } , 0 \right) } \Big [ 1 + \alpha \Big ( T \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) - T _ { o } \Big ) - \kappa p \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t ^ { \prime } + d t ^ { \prime } , l \big ) - 1 \Big ] .
$$

The pressure formula on $l \Big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \Big )$ at $t ^ { \prime } + d t ^ { \prime }$

$$
p \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) = - \frac { 1 } { 3 } \big ( \sigma _ { 1 1 } + \sigma _ { 2 2 } + \sigma _ { 3 3 } \big ) \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big )
$$

The energy equation on $A$ ：

$$
\begin{array} { l } { { \displaystyle \Big [ u \big ( t , t ^ { \prime } + d t ^ { \prime } , A ^ { \prime } \big ) - u \big ( t , t ^ { \prime } , A \big ) \Big ] m \big ( A \big ) } } \\ { { \displaystyle = - p \big ( t , t ^ { \prime } , A \big ) \Bigg [ \frac { 1 } { \rho \big ( t , t ^ { \prime } + d t ^ { \prime } , A ^ { \prime } \big ) } - \frac { 1 } { \rho \big ( t , t ^ { \prime } , A \big ) } \Bigg ] m \big ( A \big ) + Q ^ { i n } \big ( t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , A \big ) } } \end{array}
$$

The mass conservation equation:

$$
\begin{array} { c } { { \rho \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \right) N _ { i ^ { * } } ^ { i n } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) V _ { o } } } \\ { { { } } } \\ { { = \rho \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) N _ { i ^ { - } } ^ { o u t } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) V _ { o } } } \end{array}
$$

Where $u$ is the internal energy per unit mass, which can be obtained from the equation of state in thermodynamics as a function of the temperature and density. $Q ^ { i n }$ is the input heat. $\boldsymbol { V } _ { o }$ is the volume of internal points of a space monad. The energy equation is just the first law of thermodynamics.

The cross section $s _ { i } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) , s _ { i } \left( x - \varepsilon , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ can be obtained from (28） ，and will be used for the next step calculation.

In addition, kinematic conditions are required for the position of the centroid

Applying kinematic conditions to the outflow part through the face $i ^ { - }$ of the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ (coincident with the face $i ^ { + }$ of the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right) \colon$ ） $A$ , you can get:

$$
\frac { N ^ { \prime } ( A ) } { N _ { o } ^ { \prime } } U _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) { = } - \frac { 1 } { N _ { o } T } \frac { \mathrm { \Lambda } _ { o } ^ { o ^ { 2 } } } { \mathrm { \Lambda } _ { \mathscr { E } _ { t } } ^ { o ^ { 2 } } } x _ { i , b } ^ { \prime c } \left( A \right) N _ { i } ^ { o u t } \left( A \right)
$$

And applying kinematic conditions to the part $\mathcal { A } ^ { \prime }$ , there is

$$
\frac { N ^ { \prime } \big ( A ^ { \prime } \big ) } { N _ { o } ^ { \prime } } U _ { i } \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } , l \big ) = \frac { 1 } { N _ { o } T \varepsilon _ { t } } \dddot { \varepsilon _ { i } } x _ { i , e } ^ { \prime c } \big ( A ^ { \prime } \big ) - \varepsilon _ { i } \bigg ) N _ { i ^ { + } } ^ { i n } \big ( A ^ { \prime } \big )
$$

From (14), we can see the relationship between $N ^ { \prime } ( A )$ and $N _ { i ^ { - } } ^ { o u t } \left( A \right)$ (also $N ^ { \prime } ( A ^ { \prime } )$ and $N _ { i ^ { + } } ^ { i n } ( A ^ { \prime } ) ) .$

By (58)、(59) $x _ { i , b } ^ { \prime c } \left( A \right)$ and $x _ { i , e } ^ { \prime c } \left( A ^ { \prime } \right)$ can be obtained. The coordinates in the direction （20 $x _ { j } , x _ { k }$ of the centroid $A$ 、 $\boldsymbol { A ^ { \prime } }$ can be processed as follows. Let the components in the direction （204号 $x _ { j } , x _ { k }$ of the centroid-coordinate of the cross section of $l \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } \right)$ on the interface between the correspondent monads be $x _ { q , j } ^ { \prime c } , x _ { q , k } ^ { \prime c }$ respectively (the subscript $q$ indicates the interface between the monads),and obtained from the pre-determined initial conditions. It is possible to make the components in the direction $x _ { j } , x _ { k }$ of the centroid-coordinate of $A$ be （20 $x _ { q , j } ^ { \prime c } , x _ { q , k } ^ { \prime c }$ at the time $\left( t , t ^ { \prime } \right)$ ，atht $x _ { j } , x _ { k }$ of the centrildcoordinate of $\boldsymbol { A ^ { \prime } }$ at the time $\left( t , t ^ { \prime } + d t ^ { \prime } \right)$ can be easily obtained. With the centroid- coordinates of $A$ and （20 $\boldsymbol { A ^ { \prime } }$ （20 you can calculate the centroid position of $l \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } \big ) \mathrm { a n d } l \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } + d t ^ { \prime } \big ) .$

# 7 About the rotation of particles

# 1, Rotational angle of particle and setting of some coordinate systems

If there is the deformation inside the particle, there is the relative displacement between the points inside the particle and the particle state is not equilibrium. In order to describe the non-equilibrium state of the particles,we will set some Cartesian coordinate systems at each point (the monad) inside the particle $l$

The coordinate system in each point which is rotation-fixed to the mass is recorded as $K _ { \eta } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ，the coordinate system in the point $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ，whose coordinate axes are （20 $\left( \eta _ { 1 } , \eta _ { 2 } , \eta _ { 3 } \right)$ . The coordinate system $K _ { o } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ refers to the coordinate system in the $\mathrm { p o i n t } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ,the axis directions of which are the same as $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ .The origins of both $K _ { \eta } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ and $K _ { o } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ are the centroid $c _ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , l \right)$ of the mass of $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ in the point (the monad) $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$

![](images/4d6d783934ad8d153fc143a3178f218fc81a7eef5bbe14f1a6e75cf80c53d4d9.jpg)  
Figure 10 Coordinate systems $K _ { \eta } ^ { l } , K _ { o } ^ { l } , K _ { o }$

The axis directions of $K _ { o } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ are fixed in space, but it is in translation motion with the particle. However $K _ { \eta } ^ { l } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ is rotation-fixed with the mass of the particle $l$ in the point $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ , and rotates with the particle. The origin of the coordinate system $K _ { o } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ is $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ，a fixed coordinate system whose axis directions are $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ (See Figure 10).

As shown in the figure 10, the angles between the axes of $K _ { \eta } ^ { l }$ and $K _ { o } ^ { l }$ are recorded as $\varphi _ { i s } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right)$ . It is the angle between the coordinate axis $x _ { i }$ of $K _ { o } ^ { l }$ and the coordinate axis $\eta _ { s }$ of the coordinate system $K _ { \eta } ^ { l }$ （20

Let

$$
\begin{array} { l } { { \cos \varphi _ { i s } = \alpha _ { i s } } } \\ { { { } } } \\ { { \alpha _ { 1 k } \alpha _ { 1 l } + \alpha _ { 2 k } \alpha _ { 2 l } + \alpha _ { 3 k } \alpha _ { 3 l } = \delta _ { k l } \qquad \quad ( k , l = 1 , 2 , 3 ) } } \end{array}
$$

So one has

Therefore, only three of $\alpha _ { i s }$ are independent. Give these three of $\alpha _ { i s }$ and can get all nine $\alpha _ { i s }$

The coordinate system $K _ { \eta } ^ { l }$ is rotation-fixedly connected to the material, so the rotation of $K _ { \eta } ^ { l }$ is just the rotation of the mass. And let $K _ { \eta } ^ { l }$ rotate round axis $x _ { i }$ of the system $K _ { o } ^ { l }$ , the rotation angle is $\phi _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right)$ ：

Assume that

$$
\begin{array} { r l } & { \varphi _ { o p } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \varphi _ { o p } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \Delta \varphi _ { o p } ^ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } \\ & { } \\ & { \phi _ { o } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \phi _ { o } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \Delta \phi _ { o } ^ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } \end{array}
$$

$$
\begin{array} { r l } & { \delta \varphi _ { s p } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right) = \varphi _ { s p } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } + d t ^ { \prime } , l \right) - \varphi _ { s p } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right) } \\ & { } \\ & { \delta \phi _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right) = \phi _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } + d t ^ { \prime } , l \right) - \phi _ { i } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right) } \end{array}
$$

It is obviously that $\delta \varphi _ { s p }$ can be obtained from $\left( \delta \phi _ { 1 } , \delta \phi _ { 2 } , \delta \phi _ { 3 } \right)$

# 2,Force couple moment on the interface

The elastic force action on the interface of two adjacent monads exerted on （204号 $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ isreduced tooneforce(i.e.， theaforementionedforce $F _ { o } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right)$ ）plus one force couple moment, the component of which in the

axis $x _ { o }$ is $P _ { o } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } , t , t ^ { \prime } , l \right)$

Let the moment of force couple generated by the deformation of the particle l on the interface of two adjacent monads be proportional to $\Delta \phi _ { o }$ .That isto say, there are

$$
P _ { i ^ { - } , i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = - \alpha \Delta \phi _ { i } ^ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \frac { 1 } { \varepsilon _ { i } }
$$

$$
\left. \begin{array} { c } { \displaystyle = - \alpha \Big [ \phi _ { i } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) - \phi _ { i } \big ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Big ] \frac { 1 } { \varepsilon _ { i } } \right. } \end{array}
$$

$$
\begin{array} { r } { \int _ { \ o } { d \ o \left[ \phi _ { i } \left( x _ { i } + \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \phi _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \right] \frac { 1 } { \varepsilon _ { i } } } } \end{array}
$$

$$
\begin{array} { r } { = - \alpha _ { 1 } \Big [ \phi _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \phi _ { i } \left( x _ { i } , x _ { j } - \varepsilon _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] \frac { 1 } { \varepsilon _ { j } } } \end{array}
$$

$$
P _ { j ^ { + } , i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \alpha _ { 1 } \Delta \phi _ { i } ^ { j } \left( x _ { i } , x _ { j } + \varepsilon _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \frac { 1 } { \varepsilon _ { j } }
$$

$$
\begin{array} { r } { = \alpha _ { 1 } \Big [ \phi _ { i } \big ( x _ { i } , x _ { j } + \varepsilon _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) - \phi _ { i } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) \Big ] \frac { 1 } { \varepsilon _ { j } } } \end{array}
$$

$$
P _ { \boldsymbol { k } ^ { - } , i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) { = } - { \alpha } _ { 1 } \Delta { \phi } _ { i } ^ { k } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \frac { 1 } { { \varepsilon } _ { k } }
$$

$$
\begin{array} { r } { = - \alpha _ { 1 } \Big [ \phi _ { i } \big ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \big ) - \phi _ { i } \big ( x _ { i } , x _ { j } , x _ { k } - \varepsilon _ { k } , t , t ^ { \prime } , l \big ) \Big ] \frac { 1 } { \varepsilon _ { k } } } \end{array}
$$

$$
P _ { \boldsymbol { k } ^ { + } , i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \alpha _ { 1 } \Delta \phi _ { i } ^ { k } \left( x _ { i } , x _ { j } , x _ { k } + \varepsilon _ { k } , t , t ^ { \prime } , l \right) \frac { 1 } { \varepsilon _ { k } }
$$

$$
= \alpha _ { 1 } \Big [ \phi _ { i } \left( x _ { i } , x _ { j } , x _ { k } + \varepsilon _ { k } , t , t ^ { \prime } , l \right) - \phi _ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) \Big ] \frac { 1 } { \varepsilon _ { k } }
$$

Here the subscripts to the couple moment $P$ represent the surface (the former) and theomponentdectheae $P _ { i ^ { - } , i } , P _ { i ^ { + } , i } , P _ { j ^ { - } , i } , P _ { j ^ { + } , i } , P _ { k ^ { - } , i } , P _ { k ^ { + } , i }$ Pk+,i are the components of $x _ { i }$ -direction of the couple moment on the surfaces of $i ^ { - } , i ^ { + } , j ^ { - } , j ^ { + } , k ^ { - } , k ^ { + }$ respectively .The right sides of the later four relationships in (64) are the curvatures of particle $l \left( x _ { i } , x _ { j } , x _ { k } \right)$ . The nature of (64) is the constitutive equation.

# 3,About momentum moment theorem

Write the momentum moment theorem for $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ in the coordinate system

$$
\begin{array} { r l } & { K _ { o } ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ~ : } \\ & { \overline { { M } } ( x , t , t ^ { \prime } , l ) \varepsilon _ { t } ^ { 2 } d t ^ { \prime } = \overline { { L } } ( x , t , t ^ { \prime } + d t ^ { \prime } , l ) - \overline { { L } } ( x , t , t ^ { \prime } , l ) } \\ & { ~ + \overline { { L ^ { o u t } } } ( x , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) - \overline { { L ^ { i n } } } ( x , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) } \end{array}
$$

Here $\overrightarrow { M }$ be the force moment on $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ， $\mathit { \Pi } _ { \overline { { L } } }$ be the momentum moment of $l \big ( x _ { 1 } , x _ { 2 } , x _ { 3 } \big )$ ， $\overline { { L ^ { o u t } } }$ and $\overrightarrow { L ^ { i n } }$ be the momentum moments of the outflow from and the

![](images/6dc2d2383016125b420c10d2b7a0f1cad65b254111fe8a64dca0d7b37325ecbf.jpg)  
Figure 11Schematic diagram of momentum moment calculation

inflow into the monad $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ . These moments all have the reference point of $\left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ ，the origin of coordinate system $K _ { o } \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$

In Figure 11, $\overline { { R } }$ is the vector of the centroid $c _ { \scriptscriptstyle l }$ in the coordinate system （204号 $K _ { o }$ ,the unit vectors on three axes of the coordinate system $K _ { o }$ are $u _ { 1 } , u _ { 2 } , u _ { 3 }$ （20 respectively.

The momentum moment of $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ is

$$
\overline { { L } } \left( x , t , t ^ { \prime } , l \right) = \varepsilon ^ { \ 2 } \overline { { R } } \left( x , t , t ^ { \prime } , l \right) \times \overline { { U } } \left( x , t , t ^ { \prime } , l \right) m \left( x , t , t ^ { \prime } , l \right) + \sum _ { i } \varepsilon ^ { \ 2 } \overline { { r _ { i } ^ { \prime } } } \times \Delta m _ { i } \overline { { U _ { i } ^ { \prime } } }
$$

Where， $\overrightarrow { U _ { i } ^ { \prime } } = \overline { { \omega } } \times \overline { { r } } _ { i } ^ { \ o \phantom { \prime } 2 } , \overline { { \omega } } = \overline { { \omega } } \big ( x , t , t ^ { \prime } , l \big )$ is the angular velocity of the particle$l \big ( x _ { 1 } , x _ { 2 } , x _ { 3 } \big ) .$ （204号

By calculation there is

$\begin{array} { r l } & { \overline { { L } } \left( x , t , t ^ { \prime } , l \right) = \varepsilon ^ { 2 } \overline { { R } } \left( x , t , t ^ { \prime } , l \right) \times \overline { { U } } \left( x , t , t ^ { \prime } , l \right) m \left( x , t , t ^ { \prime } , l \right) } \\ & { + \big ( I _ { 1 1 } \omega _ { 1 } - I _ { 1 2 } \omega _ { 2 } - I _ { 1 3 } \omega _ { 3 } \big ) \overline { { u _ { 1 } } } + \big ( I _ { 2 2 } \omega _ { 2 } - I _ { 1 2 } \omega _ { 1 } - I _ { 2 3 } \omega _ { 3 } \big ) \overline { { u _ { 2 } } } + \big ( I _ { 3 3 } \omega _ { 3 } - I _ { 1 3 } \omega _ { 1 } - I _ { 2 3 } \omega _ { 2 } \big ) \overline { { u _ { 3 } } } } \end{array}$ (67 A $\mathrm { n o n g \ t h e m } , I _ { s s } = \sum _ { i } \Delta m _ { i } \left( x _ { p , i } ^ { \prime 2 } + x _ { q , i } ^ { \prime 2 } \right) \varepsilon ^ { \circ ^ { 4 } } , I _ { s q } = \sum _ { i } \Delta m _ { i } x _ { s , i } ^ { \prime } x _ { q , i } ^ { \prime } \varepsilon ^ { 4 }$ That are the moments of inertia of $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ in the coordinate system $K _ { o } ^ { l }$ In the equation (67), $\omega _ { s } = \omega _ { s } \left( x , t , t ^ { \prime } , l \right) , I _ { s s } = I _ { s s } \left( x , t , t ^ { \prime } , l \right) , I _ { s q } = I _ { s q } \left( x , t , t ^ { \prime } , l \right) .$

And let the masses flowing out (or into ） through the six interfaces be denoted as $\left( { { A _ { 1 } } , { A _ { 2 } } , { A _ { 3 } } , { A _ { 4 } } , { A _ { 5 } } , { A _ { 6 } } } \right)$ respectively. The vectors of the centroids of these masses on the interfacesare $\left( \overline { { h _ { 1 } } } , \overline { { h _ { 2 } } } , \overline { { h _ { 3 } } } , \overline { { h _ { 4 } } } , \overline { { h _ { 5 } } } , \overline { { h _ { 6 } } } \right)$ (relative to the origin of the system $K _ { o }$ ），or $\left( \vec { r } _ { 1 } ^ { \prime } , \vec { r } _ { 2 } ^ { \prime } , \vec { r } _ { 3 } ^ { \prime } , \vec { r } _ { 4 } ^ { \prime } , \vec { r } _ { 5 } ^ { \prime } , \vec { r } _ { 6 } ^ { \prime } \right)$ (relative tothecentroid $c _ { l }$ ）， which canbe obtainedfrom $\left( \overline { { h _ { 1 } } } , \overline { { h _ { 2 } } } , \overline { { h _ { 3 } } } , \overline { { h _ { 4 } } } , \overline { { h _ { 5 } } } , \overline { { h _ { 6 } } } \right)$ . And that the $\overrightarrow { h _ { q } }$ is just $\left( x _ { q , i } ^ { \prime c } , x _ { q , j } ^ { \prime c } , x _ { q , k } ^ { \prime c } \right)$ which have been already obtained in the previous section. Therefore these vectors are known or available.

Then there is

$$
\overline { { { L ^ { o u t } } } } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) = \sum _ { q = 1 } ^ { 6 } \overline { { { R } } } \left( x , t , t ^ { \prime } , l \right) \overset { o ^ { 2 } } { \varepsilon } \times \delta m _ { q } ^ { o u t } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) \overline { { { U } } } \left( x , t , t ^ { \prime } , l \right)
$$

$$
+ \sum _ { q = 1 } ^ { 6 } \overline { { { r _ { q } ^ { \prime } } } } ( x , t , t ^ { \prime } , l ) \times [ \overline { { { \omega } } } ( x , t , t ^ { \prime } , l ) \times \overline { { { r _ { q } ^ { \prime } } } } ( x , t , t ^ { \prime } , l ) ] ] ^ { \rho } \delta ^ { 4 } \delta m _ { q } ^ { o u t } ( x , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l )
$$

$$
\overline { { { L ^ { i n } } } } ( x , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) = \sum _ { q } \overline { { { R } } } ( x , t , t ^ { \prime } , l ) \varepsilon ^ { ^ { 2 } } \times \delta m _ { q } ^ { i n } ( x , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) \overline { { { U } } } ( x , t , t ^ { \prime } , l ) .
$$

$$
+ \sum _ { q = 1 } ^ { 6 } \overline { { { r _ { q } ^ { \prime } } } } \left( x , t , t ^ { \prime } , l \right) \times \left[ \overline { { { \omega } } } \left( x , t , t ^ { \prime } , l \right) \times \overline { { { r _ { q } ^ { \prime } } } } \left( x , t , t ^ { \prime } , l \right) \right] \sp { \circ } \varepsilon ^ { 4 } \delta m _ { q } ^ { { \mathrm { i n } } } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right)
$$

The three components of $\overline { { L ^ { o u t } } } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) \quad \mathrm { a r e : } \quad L _ { s } ^ { o u t } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right)$

The three components of $\overline { { L ^ { i n } } } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right) \quad \mathrm { a r e : } \quad L _ { s } ^ { i n } \left( x , t , t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } , l \right)$

The three components of $\begin{array} { r } { \begin{array} { l } { \mathrm { \Lambda } _ { \varepsilon } ^ { o ^ { 2 } } \overline { { R } } \big ( x , t , t ^ { \prime } , l \big ) \times \overrightarrow { U } \big ( x , t , t ^ { \prime } , l \big ) m \big ( x , t , t ^ { \prime } , l \big ) } \end{array} \mathrm { a r e } L _ { s } ^ { m } \left( x , t , t ^ { \prime } , l \right) } \end{array}$

Then the momentum moment theorem can be written as

$$
\begin{array} { r l } & { \mathcal { H } _ { q } ( \{ \Delta , \xi \} ^ { 2 } , \{ \xi \} ^ { 2 } ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } , \{ \Delta , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } , \{ \Delta , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } , \{ \Delta , \xi \} ^ { 2 } ) ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ \Delta , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \{ X , \xi \} ^ { 2 } ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + ( \mathcal { H } _ { q } ( \{ X , \xi \} ^ { 2 } ) ) } \\ & { + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \mathcal { H } _ { q } ( \mathcal { X } ^ { 2 } ) - \mathcal { H } _ { q } ( \mathcal { X } ^ { 2 } ) ) } \\ &  + \mathcal { E } _ { \mathrm { H } } ^ { 2 } ( \mathcal { H } _ { q } ( \mathcal { X } ^  \end{array}
$$

Where the force moment $\overline { { M } } \left( x , t , t ^ { \prime } , l \right)$ is the force moment to be imposed on $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ (relative to the origin of the coordinate system $K _ { o } \in \mathcal { K } _ { o } \in K _ { o } \in K _ { o } \in K _ { o } \in K _ { o } \in K _ { o } \cap K _ { o } \cap \mathcal { K } _ { o } \cap K _ { o }$ ,and

$$
M _ { s } \left( x , t , t ^ { \prime } , l \right) = P _ { s } \left( x , t , t ^ { \prime } , l \right) + m _ { o , s } ^ { F } \left( x , t , t ^ { \prime } , l \right) + m _ { o , s } ^ { f } \left( x , t , t ^ { \prime } , l \right) + m _ { s } \left( x , t , t ^ { \prime } , l \right) .
$$

There are four items on the right side of the equation (7O). The first item is the $s -$ component of the force couple moment on the interface of the adjacentmonads due to elastic deformation; The second is the $s -$ component of the moment of the elastic force $\overrightarrow { F }$ ，its action point is the centroid of the cross-section between the adjacent monads, referring to the origin of the coordinate system $K _ { o }$ ; The third is the S- component of the moment of the force $\overrightharpoon { f }$ acting on the particle $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right)$ due to the other particles in the monad (The action point of $\overline { { \boldsymbol { f } } }$ is the centroid $c _ { \scriptscriptstyle l }$ of l - mass in the monad.) referring to the origin point of the coordinate system $K _ { o }$ ； The fourth term is the $s -$ component of the couple moment acting on $l -$ particle due to the other particles in the monad.

# 4, Solving rotation problem

$$
\phi _ { i } \left( x , t , t ^ { \prime } , l \right) , \omega _ { s } \left( x , t , t ^ { \prime } , l \right) , \varphi _ { s p } \left( x , t , t ^ { \prime } , l \right)
$$

By using successively the following steps,

(1) One finds from $\phi _ { o }$ that

$$
\begin{array} { r } { \Delta \phi _ { o } ^ { i } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) = \phi _ { o } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) - \phi _ { o } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right) } \end{array}
$$

(2) By using of (64) one can get at $P _ { i } \left( x , t , t ^ { \prime } , l \right)$

(3) Formula about the force moment is

$$
M _ { s } \left( x , t , t ^ { \prime } , l \right) = P _ { s } \left( x , t , t ^ { \prime } , l \right) + m _ { o , s } ^ { F } \left( x , t , t ^ { \prime } , l \right) + m _ { o , s } ^ { f } \left( x , t , t ^ { \prime } , l \right) + m _ { s } \left( x , t , t ^ { \prime } , l \right) .
$$

It can be seen from (69) that $M _ { s } \left( x , t , t ^ { \prime } , l \right) \sim { \varepsilon } ^ { 5 }$ a high-order small quantity.

Therefore, there is an approximate relationship

$$
m _ { s } \left( x , t , t ^ { \prime } , l \right) \dot { = } - P _ { s } \left( x , t , t ^ { \prime } , l \right) - m _ { o , s } ^ { F } \left( x , t , t ^ { \prime } , l \right) - m _ { o , s } ^ { f } \left( x , t , t ^ { \prime } , l \right)
$$

Thus, take

$$
m _ { s } ^ { * } \left( x , t , t ^ { \prime } , l \right) = - P _ { s } \left( x , t , t ^ { \prime } , l \right) - m _ { o , s } ^ { F } \left( x , t , t ^ { \prime } , l \right) - m _ { o , s } ^ { f } \left( x , t , t ^ { \prime } , l \right)
$$

Let $m _ { s } ^ { * }$ be approximately $m _ { s }$ and then correct $m _ { s } ^ { * }$ to get the more accurate value of $m _ { s }$ ：

(4) Amendment of $m _ { s } ^ { * }$

When the interaction between the particles is a contact action, then the sum of the internal force moments of the system (refer to any point) is zero. Thus there is

$$
{ \sum _ { l = 1 } ^ { k } } { [ { \overline { { R } } } { ( { x , t , t ^ { \prime } , l } ) } ] ^ { \circ } } \varepsilon \times { \overline { { f } } } ( { x , t , t ^ { \prime } , l } ) { ] _ { s } } + { \sum _ { l = 1 } ^ { k } { m _ { s } ( { x , t , t ^ { \prime } , l } ) } } = 0
$$

In square brackets, it is the moment of force （2 $\overline { { f } } \left( x , t , t ^ { \prime } , l \right)$ and the origin of the coordinate system $K _ { o }$ is taken as the reference point. Yet the force $\overline { { f } } \left( x , t , t ^ { \prime } , l \right)$ has been already found in the translation problem

Replacing $m _ { s }$ in (72) by $m _ { s } ^ { * }$ in (71),(72) will become $\sum _ { l = 1 } ^ { k } \Biggl [ \overline { { R } } \left( x , t , t ^ { \prime } , l \right) \Biggr ] \stackrel { o } { \varepsilon } ^ { 2 } \times \overline { { f } } \left( x , t , t ^ { \prime } , l \right) \Biggr ] _ { s } + \sum _ { l = 1 } ^ { k } m _ { s } ^ { * } \left( x , t , t ^ { \prime } , l \right) = \Omega _ { s } \left( x , t , t ^ { \prime } \right)$

And to allocate $\Omega _ { s } \left( x , t , t ^ { \prime } \right)$ based on the value of $m _ { s } ^ { * } \left( x , t , t ^ { \prime } , l \right)$ , that is, let

$$
\Omega _ { s } \left( x , t , t ^ { \prime } \right) = \sum _ { l = 1 } ^ { k } { \Omega _ { s } \left( x , t , t ^ { \prime } , l \right) }
$$

and （204号 $\left| m _ { s } ^ { * } \left( x , t , t ^ { \prime } , l \right) \right| = b _ { o } \beta _ { l } , \sum _ { l = 1 } ^ { k } \beta _ { l } = \beta$

$$
\Omega _ { s } \left( x , t , t ^ { \prime } , l \right) = \frac { \Omega _ { s } \left( x , t , t ^ { \prime } \right) } { \beta } \beta _ { l }
$$

Here $b _ { _ o }$ is a positive constant.

$$
m _ { s } \left( x , t , t ^ { \prime } , l \right) = m _ { s } ^ { * } \left( x , t , t ^ { \prime } , l \right) - \Omega _ { s } \left( x , t , t ^ { \prime } , l \right)
$$

Obviously substituting the $m _ { s } \left( x , t , t ^ { \prime } , l \right)$ in (76) into (73) there is

$$
{ \sum _ { l = 1 } ^ { k } } { \left[ { \overline { { R } } } \left( x , t , t ^ { \prime } , l \right) { \varepsilon } ^ { 2 } \times { \overline { { f } } } \left( x , t , t ^ { \prime } , l \right) \right] _ { s } } + { \sum _ { l = 1 } ^ { k } } m _ { s } \left( x , t , t ^ { \prime } , l \right) = 0
$$

(5) Substitutingso obtained $m _ { s } \left( x , t , t ^ { \prime } , l \right)$ into (70)， the moment of force $M _ { s } \left( x , t , t ^ { \prime } , l \right)$ can be calculated.

And by using of the momentum moment theorem (69） one can find $\omega _ { s } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) .$ （204号

(6) Finding by use of $\omega _ { s } \left( x , t , t ^ { \prime } , l \right)$

$$
\begin{array} { r l } & { \boldsymbol { \phi } _ { s } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) = \boldsymbol { \phi } _ { s } \left( x , t , t ^ { \prime } , l \right) + \overleftarrow { \boldsymbol { \varepsilon } _ { t } } \ d t ^ { \prime } \boldsymbol { \omega } _ { s } \left( x , t , t ^ { \prime } , l \right) } \\ & { \delta \boldsymbol { \phi } _ { s } = \boldsymbol { \phi } _ { s } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) - \boldsymbol { \phi } _ { s } \left( x , t , t ^ { \prime } , l \right) } \end{array}
$$

Then you can find （204号 $\delta \varphi _ { s p } \left( x , t , t ^ { \prime } , l \right)$ from $\delta \phi _ { s } \left( x , t , t ^ { \prime } , l \right)$ ．The state of rotation of $l \left( x _ { 1 } , x _ { 2 } , x _ { 3 } \right) \mathrm { i s ~ i n d i c a t e d ~ b y } \left( \delta \phi _ { s } , \delta \varphi _ { s p } \right) .$

There is $\varphi _ { s p } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) = \varphi _ { s p } \left( x , t , t ^ { \prime } , l \right) + \delta \varphi _ { s p } \left( x , t , t ^ { \prime } , l \right)$

$\left( 7 \right) \mathrm { S t a r t i n g ~ f r o m } \omega _ { s } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) , \phi _ { s } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) , \varphi _ { s p } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right) ,$ repeat the above steps again.

The moments of inertia of $l \big ( x , t , t ^ { \prime } \big )$ in the system $K _ { o } ^ { l }$ are required in the calculation. This will be discussed below.

# 5,About the moment of inertia

The moment of inertia of the particle-mass $m \big ( x , t , t ^ { \prime } , l \big )$ in the coordinate system $K _ { \eta } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } , l \right)$ ,recorded as $I _ { s p } ^ { o , l } \left( x , t , t ^ { \prime } , l \right)$ ，is given .The moment of inertia of $m \big ( x , t , t ^ { \prime } , l \big )$ in the coordinate system $K _ { o } ^ { l } \left( x , t , t ^ { \prime } , l \right)$ , recorded as $I _ { i j } ^ { l } \left( x , t , t ^ { \prime } , l \right)$ ,can be obtained by use of $\varphi _ { s p } \left( x , t , t ^ { \prime } , l \right)$ and $I _ { s p } ^ { o , l } \left( x , t , t ^ { \prime } , l \right)$ ： $I _ { i j } ^ { l } \left( x , t , t ^ { \prime } , l \right)$ is just the moment of inertia in the momentum moment theorem (69).

The expressions of $I _ { i j } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } , l \right)$ are given below.

$$
I _ { i j } ^ { l } = \left( \alpha _ { i 1 } \alpha _ { j 2 } + \alpha _ { i 2 } \alpha _ { j 1 } \right) I _ { 1 2 } ^ { o , l } + \left( \alpha _ { i 1 } \alpha _ { j 3 } + \alpha _ { i 3 } \alpha _ { j 1 } \right) I _ { 1 3 } ^ { o , l } + \left( \alpha _ { i 2 } \alpha _ { j 3 } + \alpha _ { i 3 } \alpha _ { j 2 } \right) I _ { 2 3 } ^ { o , l }
$$

$$
\begin{array} { r l r } & { } & { - \alpha _ { i 1 } \alpha _ { j 1 } I _ { 1 1 } ^ { o , l } - \alpha _ { i 2 } \alpha _ { j 2 } I _ { 2 2 } ^ { o , l } - \alpha _ { i 3 } \alpha _ { j 3 } I _ { 3 3 } ^ { o , l } } \\ & { } & \\ & { } & { I _ { k k } ^ { l } = \alpha _ { k 1 } ^ { 2 } I _ { 1 1 } ^ { o , l } + \alpha _ { k 2 } ^ { 2 } I _ { 2 2 } ^ { o , l } + \alpha _ { k 3 } ^ { 2 } I _ { 3 3 } ^ { o , l } - 2 \alpha _ { k 1 } \alpha _ { k 2 } I _ { 1 2 } ^ { o , l } - 2 \alpha _ { k 1 } \alpha _ { k 3 } I _ { 1 3 } ^ { o , l } - 2 \alpha _ { k 2 } \alpha _ { k 3 } I _ { 2 3 } ^ { o , l } } \end{array}
$$

In the coordinate system $K _ { \eta } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } , l \right)$ let

$$
\begin{array} { r l } & { I _ { s p } ^ { o , l , * } ( \boldsymbol { x } , t , t ^ { \prime } + d t ^ { \prime } , l ) = I _ { s p } ^ { o , l } ( \boldsymbol { x } , t , t ^ { \prime } , l ) } \\ & { \qquad + \delta I _ { s p } ^ { o , l , i n } ( \boldsymbol { x } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) - \delta I _ { s p } ^ { o , l , o u t } ( \boldsymbol { x } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) } \end{array}
$$

When the coordinate system $K _ { \eta } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } , l \right)$ istranslated from $c _ { l } \left( \boldsymbol { x } , t , t ^ { \prime } , l \right)$ t0 $c _ { l } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ ， the coordinate system $K _ { \eta } ^ { l } \left( x , t , t ^ { \prime } , l \right)$ will be $K _ { \eta } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ . After the coordinate transformation the value of $I _ { s p } ^ { o , l , * } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ will become $I _ { s p } ^ { o , l } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ in the coordinate system $K _ { \eta } ^ { l } \left( \boldsymbol { x } , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ . Then using the angles $\varphi _ { s p } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ the moment of inertia $I _ { i j } ^ { l } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ in the coordinate system $K _ { o } ^ { l } \left( x , t , t ^ { \prime } + d t ^ { \prime } , l \right)$ can be obtained.

In solving the rotation problem,it is also assumed that the moment of inertia caused by the inflow and outflow masses is calculated in the case of the inflow and outflow masses being concentrated on there centroids on the interfaces. For example, the shaded portion in Fig.12. is the mass $A$ which flows out of the monad $\left( { { x } _ { i } } , { { x } _ { j } } , { { x } _ { k } } \right)$ and enters into the monad $\left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } \right)$ . The centroid of the mass on the interface is $c \big ( x _ { i } ^ { \prime c } = 0 , x _ { j } ^ { \prime c } , x _ { k } ^ { \prime c } \big )$ in the coordinate system $K _ { o } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ （20

![](images/ae06b73762f40493904dbbde7b6facbdc9e134213981fecaf7124391986a282a.jpg)  
Figure 12Finding the moment of inertia of the inflow (outflow) masses

and $c \big ( x _ { i } ^ { \prime c } = L _ { i } , x _ { j } ^ { \prime c } , x _ { k } ^ { \prime c } \big )$ in the coordinate system $K _ { o } \left( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ . Due to the relationships between coordinate systems $K _ { o } \left( x _ { i } , x _ { j } , x _ { k } \right)$ ， $K _ { o } ^ { l } \left( x _ { i } , x _ { j } , x _ { k } \right)$ （20 and $K _ { \eta } ^ { l } \left( x _ { i } , x _ { j } , x _ { k } \right)$ the coordinates of point $c$ in $K _ { \eta } ^ { l }$ are obtained.

So by focusing the $A$ mass on the centroid $c$ ，you can calculate the moments ofinertiaof $A$ in thecoordinatesystem $K _ { \eta } ^ { l } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l \right)$ and $\begin{array} { r l } & { K _ { \eta } ^ { l } ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } , l ) \quad , \quad \mathrm { w h i c h } \quad \mathrm { ~ a r e } \quad \quad \delta I _ { s p } ^ { o , l , o u t } ( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) } \\ & { \delta I _ { s p } ^ { o , l , i n } ( x _ { i } - \varepsilon _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime }  t ^ { \prime } + d t ^ { \prime } , l ) \mathrm { ~ r e s p e c t i v e l y . } } \end{array}$ and （204号

# 8 static state of particle system

Static state means that all particles in the system are at rest. In this case,in order to understand the state of the particle system, it is necessary to understand the state of the forces of the particle system. The forces on $l \left( x , t , t ^ { \prime } \right)$ are: the elastic action on the corresponding interface（ $x$ -surface)，the action can be divided into elastic force $F _ { s } \left( x , t , t ^ { \prime } , l \right)$ (action point $c ^ { \prime }$ on $x$ -surface） and elastic force couple moment $P _ { s } \left( x , t , t ^ { \prime } , l \right)$ ; the force to $l \left( x , t , t ^ { \prime } \right)$ applied by other particles (or particle parts) in the monad (the force action point is $c _ { \scriptscriptstyle l }$ , the centroid of $l \left( x , t , t ^ { \prime } \right)$ ） $f _ { s } \left( x , t , t ^ { \prime } , l \right)$ , as well as the force couple moment $m _ { s } \left( x , t , t ^ { \prime } , l \right)$ ；gravity $F _ { s } ^ { g }$ (only the component in the vertical direction) , its action point is $c _ { \scriptscriptstyle l }$ too(see Fig. 13.).

![](images/4246949b728b4de2527da0d5fce79cd3d1f46c99c8f03abec5290a7c8333d2e9.jpg)  
Figure 13Forces on the particle $l \big ( x , t , t ^ { \prime } \big )$ at rest

Since $l \big ( x , t , t ^ { \prime } \big )$ is static, there are the balance equations

$$
\begin{array} { r l } & { F _ { s } \left( x , t , t ^ { \prime } , l \right) + f _ { s } \left( x , t , t ^ { \prime } , l \right) + F _ { s } ^ { g } \left( x , t , t ^ { \prime } , l \right) = 0 } \\ & { \left( \overline { { R } } ^ { \prime } \times \overline { { F } } \left( x , t , t ^ { \prime } , l \right) \right) _ { s } + P _ { s } \left( x , t , t ^ { \prime } , l \right) + m _ { s } \left( x , t , t ^ { \prime } , l \right) + \left( \overline { { R } } \times \overline { { f } } \left( x , t , t ^ { \prime } , l \right) \right) _ { s } + \left( \overline { { R } } \times \overline { { F ^ { g } } } \left( x , t , t ^ { \prime } , l \right) \right) _ { s } = 0 } \end{array}
$$

Here $\overline { { R } } , \overline { { R ^ { \prime } } }$ are the vectors of $c _ { l } , c ^ { \prime }$ respectively.

The referred point of the force moment is the origin of the coordinate system $K _ { o }$

$$
\sum _ { l = 1 } ^ { k } f _ { s } \big ( x , t , t ^ { \prime } , l \big ) = 0 , \quad \sum _ { l = 1 } ^ { k } m _ { s } \big ( x , t , t ^ { \prime } , l \big ) + \sum _ { l = 1 } ^ { k } \big ( \overline { { R } } \times \overline { { f } } \big ( x , t , t ^ { \prime } , l \big ) \big ) _ { s } = 0
$$

So,let the (84),(85) be summed over $l \left( x , t , t ^ { \prime } \right)$ , it is obtained that

$$
\sum _ { l = 1 } ^ { k } { F _ { s } \left( x , t , t ^ { \prime } , l \right) } = - \sum _ { l = 1 } ^ { k } { F _ { s } ^ { g } \left( x , t , t ^ { \prime } , l \right) }
$$

$$
\sum _ { l = 1 } ^ { k } \bigl ( \overrightarrow { R ^ { \prime } } \times \overrightarrow { F } \left( x , t , t ^ { \prime } , l \right) \bigr ) _ { s } + \sum _ { l = 1 } ^ { k } P _ { s } \left( x , t , t ^ { \prime } , l \right) = - \sum _ { l = 1 } ^ { k } \bigl ( \overrightarrow { R } \times \overrightarrow { F ^ { g } } \left( x , t , t ^ { \prime } , l \right) \bigr ) _ { s }
$$

The right sides of equations (87) and (88) are gravity and gravity moment respectively, while the left sides show the elastic force and elastic force moment generated on the interface between adjacent monads due to particle deformation. Therefore, equations (87) and (88) give the conditions that must be satisfied by the elastic force and moment generated on the interface between adjacent monads due to the deformation of the particle. On this basis, the static state of the particle system can be further explored.

# 9 Conclusions

(1) The basic idea is that the time-space in which there is the movement system of a large number of particles consists of the monads. The volume of a monad is infinitely small, but not zero. The physical quantities throughout the interior of the monad are not the same,i.e. are non-uniform. The physical quantities of the elements of the same particle in the monad are same, while that of different particles (or particle parts) in the monad are different, which are discontinuous. However, between the different parts of the same particle in the adjacent monads, the difference of the physical

quantities is infinitely small, which in turn reflects some continuity of granular motion. (2) The particle motion considered in one monad occurs within $\sim \varepsilon ^ { 3 }$ of the spatial range. This small scale range of motion gives a basic approximation in solving the problem. That is, the sum of the forces applied on the particles (or the particle parts) should be high order infinitesimal, the sum of the force moments applied on the particles (or the particle parts) should be high order infinitesimal also.

(3）When the number of particles of small scale $( \ll \varepsilon )$ is large， for such a large number of small particles, we cannot use the method of this paper to solve one by one. One reasonable way to do is to find out the total effect of these many small particles.

(4） The translational motion can be solved independently. After solving the translational problem the parameters on rotation motion can be obtained and the rotational problem will be solved easily.

(5)The time step is taken as $\left( t ^ { \prime } \to t ^ { \prime } + d t ^ { \prime } \right)$ in above discussing. People can divide whole time interval $( t ^ { \prime } = 0  { t ^ { \prime } } = T )$ ）into $n$ segments. It is reasonable that the step is taken as $\Delta t ^ { \prime }$ (i.e. $n \Delta t ^ { \prime } = T$ ) in calculation.   
(6) On the initial value of the formulation, the following initial values should be given previously,   
for translational motion only   
${ U _ { s } } \left( { x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l } \right) , \qquad T { \left( { x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l } \right) , } \quad m { \left( { x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l } \right) }$   
(and its centroid position $\begin{array} { r } { \overrightarrow { R } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l \right) } \end{array}$ ），the cross section $s _ { i } \left( x , t , t ^ { \prime } = 0 , l \right)$ 、 $s _ { i } \big ( x - \varepsilon , t , t ^ { \prime } = 0 , l \big )$ ，thecentroid-postonofthecrossection $x _ { q , j } ^ { \prime c } , x _ { q , k } ^ { \prime c } \left( t , t ^ { \prime } = 0 , l \right)$ （204号   
if considering both translational and rotational motion, need an addition of initial values

$$
\begin{array} { l l } { \phi _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l \right) , } & { \omega _ { s } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l \right) , \quad \varphi _ { s p } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l \right) } \\ & { I _ { s p } ^ { o , l } \left( x _ { i } , x _ { j } , x _ { k } , t , t ^ { \prime } = 0 , l \right) } \end{array}
$$

The conditions must be met between them that the differences of the different initial values of the same particle between adjacent monads are infinitely small. The initial values can be selected under the condition that the compatibility is satisfied.

References [1] Coulomb C A. Acad. Roy. Sci. Mem. Phys. Divers Savants. 1773, 7:343 [2] Faraday M. Philos. Tran. Roy. Soc. London, 1831, 52:299 [3] Reynolds O. Phil. Mag. Ser. 5, 1885, 50:469 [4] Roberts I. Proc. Roy. Soc. 1884, 36:226 [5] de Gennes P G. Rev. Mod. Phys. 1999,71:S374 [6] Kadanoff L P. Rev. Mod. Phys. 1999, 71:435 [7] Robinson A. Nonstandard Analysis(North-Holland, Amsterdam, ed.2,1974), Chapter 1,2,10.