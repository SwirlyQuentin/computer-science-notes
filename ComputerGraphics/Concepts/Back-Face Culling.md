## Quick Summary
Back-face culling is a rendering optimization technique that prevents polygons facing away from the camera from being drawn.

## Core Idea
- What it is: Back-face culling is a rendering optimization technique that prevents polygons facing away from the camera from being drawn.
- Why it matters: It matters because it impacts visual quality, correctness, and performance in rendering.
- Where it is used: It is used in real-time 3D rendering pipelines to skip triangles facing away from the camera.

## Details
- Uses triangle winding (clockwise/counter-clockwise) to determine front faces.
- Relies on surface normals and camera direction.
- Reduces fragment processing load on the GPU.
- Improves frame time in dense triangle scenes.

## Example
Example: During rendering, triangles facing away from the camera are skipped, reducing fragment processing cost.

## Related Concepts
- [[Vertex Ordering]]
- [[Surface Normal (3D Graphics)]]

## One-Line Recall
Back-face culling skips back-facing polygons to reduce rendering cost.
