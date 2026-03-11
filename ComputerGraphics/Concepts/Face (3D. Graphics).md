---
aliases:
  - Face
---

## Quick Summary
A face is a polygon formed by connecting multiple vertices, typically a triangle in modern rendering.

## Core Idea
- What it is: A face is a polygonal element of a mesh defined by ordered vertex indices.
- Why it matters: It matters because faces determine visible surface geometry and how shading is computed.
- Where it is used: It is used in mesh representation, rasterization, and geometric modeling.

## Details
- A face references vertices from a vertex table.
- Most real-time systems triangulate faces for GPU rendering.
- Vertex order controls front/back orientation.
- Faces plus vertices and edges form a mesh topology.

## Example
Example: A triangle face can be stored as indices `(v2, v8, v5)` into a shared vertex list.

## Related Concepts
- [[Vertex (3D Graphics)]]
- [[Triangle (3D Graphics)]]
- [[Triangular Mesh]]
- [[Vertex Ordering]]

## One-Line Recall
A face is a vertex-indexed polygon unit that defines part of a mesh surface.
