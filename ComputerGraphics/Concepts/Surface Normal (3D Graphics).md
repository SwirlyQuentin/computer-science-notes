---
aliases:
  - Surface Normal
---

## Quick Summary
A surface normal is a vector perpendicular to a surface.

## Core Idea
- What it is: A surface normal encodes local surface orientation at a point.
- Why it matters: Lighting and visibility computations depend on normal direction.
- Where it is used: It is used in shading, reflections, and culling.

## Details
- Dot products with light/view vectors determine diffuse/specular terms.
- Face normals come from cross products of triangle edges.
- Vertex normals are often averaged from adjacent faces.
- Normal direction depends on vertex winding order.

## Example
Example: Diffuse intensity uses `max(0, N·L)` where `N` is normal and `L` is light direction.

## Related Concepts
- [[Vertex Ordering]]
- [[Back-Face Culling]]

## One-Line Recall
Surface normals provide the orientation needed for lighting and culling.
