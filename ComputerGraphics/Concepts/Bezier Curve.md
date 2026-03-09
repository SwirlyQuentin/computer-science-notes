---
aliases:
  - Bezier
---

## Quick Summary
A Bezier curve is a [[parametric curve]] shaped by [[control points]] and Bernstein polynomials. It is a standard tool for vector paths, UI shapes, and curve modeling.

## What It Is
With [[control points]] `P0..Pn`, a degree-`n` Bezier curve is:
- `P(t) = sum(B_i,n(t) * P_i)` for `t in [0,1]`

Where:
- `B_i,n(t) = C(n,i)(1-t)^(n-i)t^i`

## How It Is Used
- Vector graphics and font outlines.
- Motion and camera paths.
- Shape editing in design tools.
- Piecewise curve chains in modeling workflows.

## Key Behavior
- Starts at `P0`, ends at `Pn`.
- Endpoint tangent directions depend on nearby control points.
- Entire curve lies inside the convex hull of control points.

## Evaluation In Practice
De Casteljau algorithm is commonly used because it is geometric and numerically stable.

## Practical Notes
- Cubic Bezier is the most common practical degree.
- High degree curves are harder to control.
- Long paths are usually built from joined cubic segments.

## Exam-Style Questions
1. What determines the degree of a Bezier curve?
2. Why is the convex-hull property useful?
3. Why are piecewise cubic Bezier chains common?

## One-Line Recall
A Bezier curve is a control-point-driven [[parametric curve]] with stable geometry and strong practical tooling support.