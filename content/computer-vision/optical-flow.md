---
type: Concept
title: Optical Flow
description: Deriving the optical flow constraint equation via the brightness constancy assumption and a Taylor expansion.
resource: https://app.notion.com/p/1dcb3cfff9ea80bf9fd4e3b788d1f2b6
tags: [computer-vision]
timestamp: 2026-08-16T00:00:00Z
---

Part of [[first-principles|First Principles of Computer Vision]].

## Assumptions

1. The brightness of a pixel at $t_0$ and $t_1$ is assumed to be the same, so $I(x+\delta x, y + \delta y, t + \delta t) = I(x, y, t)$.
2. Displacement $(\delta x, \delta y)$ and timestep $\delta t$ are assumed to be small.

## Taylor series expansion

Expand a function as an infinite sum of its derivatives:

$$
f(x + \delta x) = f(x) + \frac{\partial f}{\partial x} \delta x + \frac{\partial^2 f}{\partial x^2} \frac{\delta x^2}{2!} + \cdots + \frac{\partial^n f}{\partial x^n} \frac{\delta x^n}{n!}
$$

If $\delta x$ is small:

$$
f(x + \delta x) = f(x) + \frac{\partial f}{\partial x} \delta x + O(\delta x^2) \rightarrow \text{Almost Zero}
$$

For a function of three variables with small $\delta x, \delta y, \delta t$:

$$
f(x + \delta x, y + \delta y, t + \delta t) \approx f(x, y, t) + \frac{\partial f}{\partial x} \delta x + \frac{\partial f}{\partial y} \delta y + \frac{\partial f}{\partial t} \delta t
$$

## Optical flow constraint

$$
I(x + \delta x, y + \delta y, t + \delta t) = I(x, y, t) \tag{1}
$$

$$
I(x + \delta x, y + \delta y, t + \delta t) = I(x, y, t) + I_x \delta x + I_y \delta y + I_t \delta t \tag{2}
$$

Subtract (1) from (2):

$$
I_x \delta x + I_y \delta y + I_t \delta t = 0
$$

Divide by $\delta t$ and take the limit as $\delta t \to 0$:

$$
I_x \frac{\partial x}{\partial t} + I_y \frac{\partial y}{\partial t} + I_t = 0
$$

Constraint equation: $I_x u + I_y v + I_t = 0$, where $(u, v)$ is the optical flow. $(I_x, I_y, I_t)$ can be easily computed from two frames.
