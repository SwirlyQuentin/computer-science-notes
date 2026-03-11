## Quick Summary
Subdivision refines a mesh into a smoother, denser version.

## Core Idea
- What it is: Subdivision repeatedly splits and repositions mesh elements to smooth shape.
- Why it matters: It generates high-quality smooth surfaces from coarse control meshes.
- Where it is used: It is used in modeling and high-detail rendering workflows.

## Details
- Each iteration increases vertex and face count.
- Common schemes include Catmull-Clark and Loop subdivision.
- Produces visually smooth limits from coarse topology.
- Higher subdivision levels increase memory and compute cost.

## Example
Example: A low-poly character head is subdivided twice to produce a smoother close-up render.

## Related Concepts
- [[Triangular Mesh]]
- [[Mesh Simplification]]

## One-Line Recall
Subdivision smooths a coarse mesh by iterative refinement.
