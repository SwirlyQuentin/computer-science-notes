## Quick Summary
A triangular mesh represents a 3D object as connected triangles.

## Core Idea
- What it is: A triangular mesh stores geometry as vertices plus triangle connectivity.
- Why it matters: It is compact, hardware-friendly, and supports many geometry algorithms.
- Where it is used: It is used in modeling, simulation, and rendering pipelines.

## Details
- Vertices hold position and optional attributes.
- Faces define triangle index triplets.
- Shared vertices reduce memory versus duplicated geometry.
- Topology supports operations like subdivision and simplification.

## Example
Example: A terrain surface is stored as a grid-like triangular mesh for efficient rendering.

## Related Concepts
- [[Triangle (3D Graphics)]]
- [[Vertex (3D Graphics)]]
- [[Mesh Simplification]]
- [[Subdivision]]

## One-Line Recall
A triangular mesh encodes shape using vertices and connected triangle faces.
