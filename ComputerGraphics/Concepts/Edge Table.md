## Quick Summary
An edge table is a scanline-fill data structure that stores [[polygon]] edges by their starting y-coordinate, enabling efficient row-by-row filling in raster space.

## What It Is
An edge table contains one record per non-horizontal polygon edge, usually with:
- `y_min`
- `y_max`
- `x_at_y_min`
- `inverse_slope = dx/dy`

Edges are bucketed by `y_min` for fast scanline activation.

## How It Is Used
In scanline polygon filling:
1. Build edge table from polygon edges.
2. For each scanline y, move matching edges into an active edge list.
3. Sort active edges by current x.
4. Fill spans between edge pairs.
5. Increment edge x using inverse slope for next scanline.

## Why It Is Useful
- Incremental updates are fast.
- Avoids recomputing intersections each row.
- Works well for software rasterization teaching and implementations.

## Relationship To Active Edge List
- Edge table: static preprocessed buckets.
- Active edge list: dynamic edges crossing current scanline.

## Practical Rules
- Skip horizontal edges to avoid double counting.
- Use consistent top/bottom inclusion rules.
- Be careful with shared vertices and parity logic.

## Exam-Style Questions
1. Why are horizontal edges typically excluded in scanline fill?
2. What data is needed in each edge record?
3. How does the active edge list differ from the edge table?

## One-Line Recall
An edge table is a y-bucketed edge structure that makes scanline polygon filling efficient and predictable.