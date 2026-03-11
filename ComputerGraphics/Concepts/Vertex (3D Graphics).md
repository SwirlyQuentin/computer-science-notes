---
aliases:
  - Vertex
---

## Quick Summary
A vertex is a point in 3D space that anchors mesh geometry.

## Core Idea
- What it is: A vertex stores position and optional per-point attributes.
- Why it matters: Vertex data drives both shape and shading results.
- Where it is used: It is used in mesh construction, transformation, and rasterization.

## Details
- Common attributes: position, normal, UV, color, tangent.
- Vertices are transformed by model/view/projection matrices.
- Triangles reference vertices by index.
- Attributes are interpolated across fragments.

## Example
Example: A vertex might store `(x,y,z)`, normal `(nx,ny,nz)`, and UV `(u,v)` for texturing.

## Related Concepts
- [[Face (3D Graphics)]]
- [[Triangle (3D Graphics)]]
- [[Vertex Table]]

## One-Line Recall
Vertices are the fundamental data points from which mesh geometry is built.
