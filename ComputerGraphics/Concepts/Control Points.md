## Quick Summary
Control points are shape handles that define or influence curves and surfaces. They are central to interactive modeling and path editing.

## What It Is
A control point is a reference point used by a curve/surface formulation to determine geometry.

Important distinction:
- [[Interpolation]] point: curve must pass through it.
- Control point: curve is influenced by it, but may not pass through it.

## How It Is Used
- Editing vector paths in drawing software.
- Tuning curvature for animation paths.
- Defining [[spline]] and surface patches in CAD/modeling.
- Managing local shape behavior in B-splines/NURBS.

## Behavior By Curve Family
- [[Bezier Curve|Bezier]]: endpoints are included, internal points steer tangents/shape.
- [[Hermite Curve|Hermite]]: endpoint positions plus tangent controls.
- B-spline: control points affect local regions, not entire curve.

## Why Control Points Matter
- Intuitive drag-and-edit workflow.
- Compact representation of complex smooth forms.
- Good balance between artist control and mathematical structure.

## Practical Notes
- Point spacing affects curvature smoothness.
- Extreme placement can create loops/self-intersections.
- Constraint tools can enforce symmetry or continuity.

## Exam-Style Questions
1. How do control points differ from [[interpolation]] points?
2. Why is local control valuable in curve editing?
3. How do inner [[Bezier Curve|Bezier]] control points affect the curve?

## One-Line Recall
Control points are the primary handles used to shape curves and surfaces in practical graphics workflows.