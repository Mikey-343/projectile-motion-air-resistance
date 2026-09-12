# Mathematical Model

## 1. Problem Definition

We consider the motion of a projectile launched with an initial speed
\(v_0\) at an angle \(\theta\) with the horizontal, under the influence
of gravity and linear air resistance.

## 2. Physical Model

The gravitational force is

\[
\vec{F}_g = m\vec{g}
\]

The air-resistance force is assumed to be proportional to the
instantaneous velocity and opposite to the direction of motion:

\[
\vec{F}_d = -b\vec{v}
\]

where \(b\) is the linear drag coefficient.

## 3. Physical Assumptions

The projectile is treated as a point mass.

The gravitational acceleration \(g\) is assumed to be constant.

The motion is confined to two dimensions.

Wind effects are neglected.

The air-resistance force is assumed to be linear in velocity:

\[
\vec{F}_d=-b\vec{v}
\]

The projectile is assumed to move near the Earth's surface, so
variations in \(g\) are neglected.

## 4. Equations of Motion

Using Newton's second law,

\[
m\frac{d\vec{v}}{dt}
=
m\vec{g}-b\vec{v}
\]

Resolving the equation into horizontal and vertical components gives

\[
\frac{dx}{dt}=v_x
\]

\[
\frac{dy}{dt}=v_y
\]

\[
\frac{dv_x}{dt}
=
-\frac{b}{m}v_x
\]

\[
\frac{dv_y}{dt}
=
-g-\frac{b}{m}v_y
\]

## 5. Initial Conditions

The projectile is launched from the origin:

\[
x(0)=0,\qquad y(0)=0
\]

The initial velocity components are

\[
v_x(0)=v_0\cos\theta
\]

\[
v_y(0)=v_0\sin\theta
\]

## 6. State Vector

For numerical computation, the state of the system is represented by

\[
\mathbf{Y}
=
\begin{bmatrix}
x\\
y\\
v_x\\
v_y
\end{bmatrix}
\]

Therefore,

\[
\frac{d\mathbf{Y}}{dt}
=
\begin{bmatrix}
v_x\\
v_y\\
-\frac{b}{m}v_x\\
-g-\frac{b}{m}v_y
\end{bmatrix}
\]

or, in compact form,

\[
\frac{d\mathbf{Y}}{dt}
=
\mathbf{f}(t,\mathbf{Y})
\]

## 7. Model Parameters

| Parameter | Symbol | SI Unit |
|---|---|---|
| Initial speed | \(v_0\) | m/s |
| Launch angle | \(\theta\) | rad |
| Projectile mass | \(m\) | kg |
| Linear drag coefficient | \(b\) | kg/s |
| Gravitational acceleration | \(g\) | m/s² |
| Numerical time step | \(\Delta t\) | s |

## 8. Scope of the Initial Model

The first numerical implementation will use the linear drag model

\[
\vec{F}_d=-b\vec{v}
\]

A no-drag case \((b=0)\) will later be used for validation against
the analytical projectile-motion solution.

A quadratic drag model may be investigated as an extension of the
project.