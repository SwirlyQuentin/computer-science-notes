---
aliases:
  - LERP
---
## Quick Summary
LERP blends between two values using a parameter `t`. It is one of the most frequently used operations in graphics and animation.

## What It Is
Formula:
- `LERP(a, b, t) = (1 - t)a + tb`
- Equivalent: `a + t(b - a)`

For `t` in `[0,1]`:
- `t=0` gives `a`
- `t=1` gives `b`
- `t=0.5` gives midpoint

## How It Is Used
- Interpolating positions between keyframes.
- Interpolating vertex attributes across edges/triangles.
- Blending colors and alpha.
- Driving UI transitions and camera movement.

## Why It Is Important
- Very cheap computationally.
- Stable and easy to reason about.
- Foundation for bilinear/trilinear [[interpolation]].

## Limits
- Produces straight paths only.
- Uniform `t` does not always mean uniform speed in world space.
- For rotations, spherical interpolation is often better.

## Practical Notes
- Clamp `t` when extrapolation is not desired.
- Compute `t = elapsed / duration` for time-based animation.

## Exam-Style Questions
1. Write the LERP formula in two equivalent forms.
2. What happens when `t > 1`?
3. Why is LERP not ideal for large-angle orientation blending?

## One-Line Recall
LERP is a constant-rate straight-line blend between two values controlled by parameter `t`.