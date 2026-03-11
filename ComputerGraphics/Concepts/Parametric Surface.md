## Quick Summary
A parametric surface defines a 3D surface with two parameters, usually `u` and `v`.

## Core Idea
- What it is: A parametric surface maps `(u,v)` to 3D position `S(u,v)`.
- Why it matters: It represents smooth curved geometry compactly and precisely.
- Where it is used: It is used in CAD, modeling tools, and surface tessellation pipelines.

## Details
- Typical form: `S(u,v) = (x(u,v), y(u,v), z(u,v))`.
- Bezier and spline surfaces are common parametric families.
- Surfaces are tessellated into triangles for rasterization.
- Parameter domains control patch boundaries.

## Example
Example: A curved hood in a CAD model is stored as patches `S(u,v)` then triangulated for GPU rendering.

## Related Concepts
- [[Spline]]
- [[Surface Patch]]
- [[Triangular Mesh]]

## One-Line Recall
Parametric surfaces map two parameters to smooth 3D geometry.
