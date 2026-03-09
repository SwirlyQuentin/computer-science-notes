## Quick Summary
A polygon is a closed 2D shape made of straight edges. In computer graphics, polygons are core building blocks for modeling, clipping, filling, and rendering surfaces.

## What It Is
A polygon is defined by an ordered list of vertices. Consecutive vertices form edges, and the last vertex connects back to the first.

Main parts:
- Vertex: corner point
- Edge: line segment between two vertices
- Boundary: closed loop of all edges

## How It Is Used
- Surface representation: most raster pipelines reduce geometry to polygonal primitives, especially triangles.
- 2D drawing and fill: UI shapes, vector art, and region filling use polygon boundaries.
- Clipping and culling: many visibility operations operate on polygon boundaries.
- Collision and hit testing: 2D and 3D engines test points/objects against polygonal regions.

## Common Types
- Convex: no inward dents, easier for many algorithms.
- Concave: has at least one inward dent.
- Regular: equal sides and angles.
- Irregular: side lengths/angles vary.

## Important Rules In Practice
- Vertex order matters (clockwise vs counterclockwise).
- Self-intersections complicate fill logic.
- Degenerate polygons (repeated/collinear points) can break algorithms.

## Mini Workflow Example
1. Store vertices in order.
2. Build edges from adjacent vertex pairs.
3. Triangulate if needed for GPU rendering.
4. Apply transforms and rasterize.

## Exam-Style Questions
1. Why are triangles commonly preferred over general polygons in real-time rendering?
2. What problems can appear if vertex winding is inconsistent?
3. How does a concave polygon differ algorithmically from a [[convex polygon]]?

## One-Line Recall
A polygon is a closed chain of straight edges that acts as a fundamental geometry primitive in graphics.
