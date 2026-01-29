# Animated Heart Curve Visualization (HTML Canvas)

This project visualizes a **heart-shaped mathematical curve** rendered in real time using the HTML5 Canvas API.  
The curve is generated from a custom analytical equation that combines a classical heart-curve component with a trigonometric modulation, producing a continuously evolving animation.

The goal of this project is **mathematical visualization**, not decorative graphics.

---

## The Equation

The curve is defined by:

\[
y = |x|^{\frac{2}{3}} + 0.9 \sqrt{|x|}\,\sin(kx)\sqrt{3 - x^2}
\]

where:
- \(x \in [-2, 2]\)
- \(k\) is a time-varying parameter

---

## Mathematical Interpretation

### 1. Base Heart Component

\[
|x|^{\frac{2}{3}}
\]

This term is a **well-known heart-shaped function** used in several classical heart curve formulations.  
It is responsible for:
- The pointed cusp at the bottom
- The symmetric lobes at the top
- Stability near the origin

This term alone produces a static, recognizable heart profile.

---

### 2. Trigonometric Modulation Term

\[
0.9 \sqrt{|x|}\,\sin(kx)\sqrt{3 - x^2}
\]

This term introduces **controlled oscillatory deformation**:

- `sin(kx)` generates periodic variation
- `k` controls the **frequency** of oscillation (not amplitude)
- `√(3 − x²)` constrains the curve to a real-valued domain
- `√|x|` smoothly suppresses oscillations near the center

Together, these ensure the deformation remains continuous and bounded.

---

## Role of Parameter `k`

- `k` is incremented every animation frame
- Increasing `k` increases oscillation density
- The curve evolves without changing its fundamental structure
- Resetting `k` prevents floating-point instability

This produces a **time-dependent curve**, not a static plot.

---

## Important Clarification (Cardioid vs Heart Curve)

This curve **is not a cardioid**.

A cardioid is a specific polar curve defined by:
\[
r = a(1 \pm \cos\theta)
\]

While cardioids are heart-shaped, **not all heart-shaped curves are cardioids**.  
The equation used in this project belongs to a broader class of **heart-like analytical curves**, intentionally modified for visualization and animation.

Correct terminology matters.

---

## Numerical Domain and Scaling

- Computation domain:
- Values are scaled by a factor of `100` for visibility
- The y-axis is inverted to match canvas coordinate space

This choice balances numerical stability and visual clarity.

---

## Rendering Approach

- Implemented using the **HTML5 Canvas 2D context**
- The curve is rendered as a continuous polyline
- Axes are drawn explicitly for mathematical reference
- Animation is driven by `requestAnimationFrame()` for smooth rendering

Canvas is used instead of SVG to allow efficient real-time recomputation.

---

## Why Canvas (Not SVG)

- Better suited for frame-based animation
- Lower overhead for continuous redraws
- Direct control over rendering pipeline
- Ideal for mathematical plotting at 60 FPS

---

## Educational Value

This project demonstrates:

- Translating mathematical equations into graphics
- Domain constraints in numerical visualization
- Time-dependent parameter modulation
- Practical use of trigonometry in animation
- Mathematical rigor applied to creative coding

It sits at the intersection of **mathematics**, **computer graphics**, and **interactive visualization**.

---

## Limitations

- The equation is a handcrafted visualization model
- It is not derived from a single canonical heart curve
- The focus is visual intuition rather than formal proof

These limitations are intentional and transparent.

---

## License

This project is open for learning, experimentation, and modification.
