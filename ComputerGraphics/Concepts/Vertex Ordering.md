## Quick Summary
Vertex ordering is the sequence used to list a polygon’s vertices.

## Core Idea
- What it is: Vertex ordering defines winding direction (clockwise or counter-clockwise).
- Why it matters: Winding controls face orientation, culling, and normal direction.
- Where it is used: It is used in triangle setup, culling, and shading pipelines.

## Details
- Counter-clockwise is commonly treated as front-facing.
- Reversed order can flip normal direction.
- Inconsistent winding causes culling and lighting artifacts.
- Consistent ordering is required for robust mesh processing.

## Example
Example: `(v0,v1,v2)` may be front-facing, while `(v0,v2,v1)` becomes back-facing.

## Related Concepts
- [[Surface Normal (3D Graphics)]]
- [[Back-Face Culling]]

## One-Line Recall
Vertex ordering determines winding, which determines face orientation.
