## Quick Summary
A convex [[Polygon|polygon]] has no inward dents: every segment connecting two points inside the polygon stays inside. This property makes many graphics algorithms faster and simpler.

## What It Is
A polygon is convex when:
- Every interior angle is less than 180 degrees.
- Boundary turns keep consistent orientation.
- Any line segment between internal points remains internal.

## How It Is Used
- Fast collision checks in physics and game engines.
- Reliable clipping and intersection routines.
- Efficient point-in-polygon and triangulation steps.
- Convex decomposition target for complex shapes.

## Why Graphics Pipelines Prefer It
Convex polygons reduce edge cases:
- Fewer ambiguous intersections.
- More predictable rasterization and fill behavior.
- Simpler mathematical tests (cross-product sign consistency).

## Typical Convexity Test (2D)
1. Walk vertices in order.
2. Compute cross-product sign for each consecutive edge pair.
3. If all non-zero signs match, the polygon is convex.

## Practical Pitfalls
- Collinear points can hide bad input data.
- Repeated vertices can produce false results.
- Floating-point tolerance is required for near-collinear edges.

## Exam-Style Questions
1. Give two equivalent definitions of convexity.
2. Why are convex polygons easier for collision detection?
3. How do collinear edges affect convexity tests?

## One-Line Recall
Convex polygons are algorithm-friendly shapes with no inward dents, making them ideal for fast geometric operations.
