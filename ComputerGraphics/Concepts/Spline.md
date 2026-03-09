## Quick Summary
A spline is a smooth curve built from multiple low-degree polynomial segments joined with continuity constraints. Splines are used whenever smooth, editable paths are needed.

## What It Is
A spline is piecewise, meaning it has multiple curve segments connected at knots.

Key concepts:
- Segment: one polynomial piece.
- Knot: segment boundary.
- Continuity: smoothness at joins (`C0`, `C1`, `C2`).

## How It Is Used
- Animation paths (camera and object motion).
- Vector drawing and font outlines.
- CAD and surface modeling.
- Data smoothing and [[interpolation]].

## Why Splines Beat Single High-Degree Polynomials
- Better numerical stability.
- Local control: editing one control point mostly affects nearby shape.
- Easier smoothness control at segment boundaries.

## Common Families
- [[Hermite Curve|Hermite]] splines: endpoints + tangents.
- [[Bezier Curve|Bezier]] splines: [[control points]] + Bernstein basis.
- B-splines: local basis support.
- NURBS: rational extension with exact conics.

## Practical Notes
- Parameterization (uniform/chord-length/centripetal) changes behavior.
- Endpoint constraints strongly influence curve ends.
- Over-aggressive tangents can cause overshoot.

## Exam-Style Questions
1. Why are splines usually piecewise instead of single global polynomials?
2. What does `C1` continuity guarantee?
3. Why are B-splines considered locally controllable?

## One-Line Recall
A spline is a smooth, piecewise polynomial curve designed for stable shape control and practical editing.