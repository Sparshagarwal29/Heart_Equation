# Animated Heart Curve Visualization (HTML Canvas)

This project visualizes a **parametric heart-like curve** derived from a modified implicit heart equation and rendered dynamically using the HTML5 Canvas API.  
The curve evolves over time through a continuously varying parameter `k`, producing a smooth animated deformation of the heart shape.

---

## Mathematical Background

The curve is based on the equation:

\[
y = |x|^{\frac{2}{3}} + 0.9 \sqrt{|x|}\,\sin(kx)\sqrt{3 - x^2}
\]

### Breakdown of the Equation

#### 1. Base Heart Structure  
The term:

\[
|x|^{\frac{2}{3}}
\]

is a **well-known heart curve component**.  
It creates the characteristic cusp at the bottom and symmetric lobes at the top.  
This form appears in classical implicit heart equations and is mathematically stable around the origin.

---

#### 2. Oscillatory Deformation Term  

\[
0.9 \sqrt{|x|}\,\sin(kx)\sqrt{3 - x^2}
\]

This term adds **controlled wave-like perturbations** to the base heart shape.

- `sin(kx)` introduces oscillation
- `k` controls **frequency**, not amplitude
- `√(3 − x²)` acts as a **domain limiter**, ensuring the curve remains real-valued
- `√|x|` smoothly scales oscillations near the center

Together, these terms prevent discontinuities while allowing expressive deformation.

---

## Role of Parameter `k`

- `k` acts as a **temporal modulation parameter**
- Increasing `k` increases oscillation frequency
- Animation is achieved by incrementing `k` every frame
- Resetting `k` avoids floating-point overflow

This makes the curve *dynamic* rather than static, without changing the underlying equation.

---

## Numerical Domain and Scaling

- The curve is evaluated over:
