---
aliases:
  - Triangle
---

## Quick Summary
A triangle is the fundamental polygon primitive in 3D graphics.

## Core Idea
- What it is: A triangle is a 3-vertex polygon defining a planar surface.
- Why it matters: GPUs are optimized to rasterize triangles efficiently and robustly.
- Where it is used: It is used in virtually all real-time 3D rendering.

## Details
- Three non-collinear points define one plane.
- Complex meshes are decomposed into triangles.
- Vertex attributes are interpolated across triangle interiors.
- Winding order determines front/back face orientation.

## Example
Example: A quad is rendered as two triangles: `(v0,v1,v2)` and `(v0,v2,v3)`.

## Related Concepts
- [[Triangular Mesh]]
- [[Vertex (3D Graphics)]]
- [[Face (3D Graphics)]]

## One-Line Recall
Triangles are the GPU’s core primitive for representing 3D surfaces.
