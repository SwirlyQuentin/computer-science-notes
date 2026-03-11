---
aliases:
  - Geometric Transformations
---

## Quick Summary
Geometric transformations change an object’s position, orientation, or size in space.

## Core Idea
- What it is: Geometric transformations are operations such as translation, rotation, and scaling applied to geometric data.
- Why it matters: They are fundamental to camera movement, object placement, and animation.
- Where it is used: They are used throughout modeling, viewing, and rendering pipelines.

## Details
- Translation moves points by an offset vector.
- Rotation changes orientation around an axis or pivot.
- Scaling changes object size along one or more axes.
- Transformations are commonly composed using matrices.
- Order matters: `T*R*S` is not the same as `S*R*T`.

## Example
Example: Apply scale, then rotation, then translation to place a model correctly in world space.

## Related Concepts
- [[Vertex (3D Graphics)]]
- [[Projection Matrix]]
- [[Triangular Mesh]]

## One-Line Recall
Geometric transformations are ordered operations that move, rotate, and scale geometry.
