---
aliases:
  - Hermite
---

## Quick Summary
A Hermite curve is a cubic [[parametric curve]] controlled by endpoints and endpoint tangents, giving direct control over entry and exit direction.

## What It Is
A cubic Hermite segment uses:
- `P0`, `P1` (endpoints)
- `T0`, `T1` (endpoint tangent vectors)
- parameter `t` in `[0,1]`

Curve form:
- `P(t) = h00(t)P0 + h10(t)T0 + h01(t)P1 + h11(t)T1`

## How It Is Used
- Path design where endpoint direction matters.
- Motion systems needing controllable in/out tangents.
- Intermediate representation in animation and [[spline]] systems.

## Why It Is Useful
- Intuitive control: edit position and slope directly.
- Exact endpoint [[interpolation]].
- Good local segment behavior.

## Continuity Across Segments
- `C0`: segments meet in position.
- `C1`: tangents match at joins for smooth direction.

## Practical Notes
- Tangent magnitude influences overshoot and speed profile.
- Poor tangent choices can introduce loops.
- Tangents can be hand-authored or derived from neighbors.

## Exam-Style Questions
1. What data defines a cubic Hermite segment?
2. Why does tangent matching matter at segment joins?
3. How does increasing tangent magnitude affect shape?

## One-Line Recall
Hermite curves interpolate endpoints while using endpoint tangents to shape direction and smoothness.