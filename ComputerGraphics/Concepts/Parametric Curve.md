## Quick Summary
A parametric curve expresses position as a function of a parameter `t`, making it flexible for geometric modeling, animation, and motion.

## What It Is
Instead of `y = f(x)`, a parametric curve uses:
- 2D: `P(t) = (x(t), y(t))`
- 3D: `P(t) = (x(t), y(t), z(t))`

This can represent lines, circles, splines, and complex paths.

![[ButterflyParametricCurve.svg|300]]

## How It Is Used
- Camera and object trajectory definition.
- Curve-based modeling in CAD and graphics tools.
- Procedural motion and path following.
- Sampling geometry for rendering and simulation.

## Why Parametric Form Is Powerful
- Handles vertical tangents and loops naturally.
- Extends cleanly from 2D to 3D.
- Gives direct control over traversal via parameterization.

## Derivatives In Use
- `P'(t)`: tangent and local direction.
- `P''(t)`: curvature behavior.

These support orientation along path and motion control.

## Practical Notes
- Uniform steps in `t` do not guarantee uniform spatial spacing.
- Constant-speed traversal often needs arc-length correction.
- Sampling density should increase in high-curvature regions.

## Exam-Style Questions
1. Why can parametric form represent curves that explicit form struggles with?
2. What does `P'(t)` represent geometrically?
3. Why might uniform `t` stepping cause uneven motion?

## One-Line Recall
A parametric curve maps a parameter to position, enabling flexible shape definition and controllable motion.