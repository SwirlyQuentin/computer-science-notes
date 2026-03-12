## **Quick Summary**
An Edge Table is a data structure used in scanline polygon filling that stores polygon edges organized by their starting scanline. It allows raster algorithms to efficiently determine which edges intersect each row of pixels.

## **Core Idea**
- Stores information about **polygon edges**
- Organized by **starting y-coordinate**
- Used for **scanline rasterization**
- Works together with an **Active Edge List (AEL)**

Instead of recomputing intersections for every scanline, the edge table allows incremental updates as the algorithm moves down the image.

## **What it is**
An Edge Table is a preprocessing data structure that stores all non-horizontal edges of a [[Polygon]] along with information needed to compute their intersection with scanlines.

Each edge entry typically contains:

- $y_{min}$ → the scanline where the edge begins
- $y_{max}$ → the scanline where the edge ends
- $x_{min}$ → x-coordinate where the edge intersects $y_{min}$
- inverse slope $\frac{dx}{dy}$

Edges are grouped into **buckets based on their starting scanline $y_{min}$**.
This allows the rasterization algorithm to quickly activate edges when the scanline reaches their starting point.

## **How its Used**
Edge tables are primarily used in **scanline polygon filling algorithms** in raster graphics.

Typical workflow:

1. Construct the [[Edge Table]] from the polygon's edges.
2. Move scanline $y$ from top to bottom of the polygon.
3. Add edges with $y_{min} = y$ to the **Active Edge List (AEL)**.
4. Sort active edges by their current x-intersection.
5. Fill pixel spans between pairs of edges.
6. Update intersection positions using the edge's inverse slope.

This incremental process makes rasterization more efficient than recomputing intersections for each scanline.

## **Example**

### Example 1: Edge Record

For an edge between vertices:

$$V_1 = (2,2), \quad V_2 = (6,6)$$

Compute:

$$y_{min} = 2$$

$$y_{max} = 6$$

$$x_{min} = 2$$

$$\frac{dx}{dy} = \frac{6-2}{6-2} = 1$$

Edge record:

| y_min | y_max | x_at_y_min | dx/dy |
|-------|-------|------------|-------|
| 2 | 6 | 2 | 1 |

### Example 2: Edge Table Buckets
```
y = 2 : edge A
y = 4 : edge B
y = 6 : edge C
```

Each scanline activates edges stored in its bucket.

### Example 3: Scanline Filling
```
Edge A     Edge B
  \         /
   \       /
    \_____/  ← filled region
```

The algorithm fills pixels between edge intersections on each scanline.

## **Details**

### Horizontal Edges
Horizontal edges are usually **excluded** because they can cause double counting when determining interior spans.

### Active Edge List (AEL)
During rasterization:

- **Edge Table** → static structure storing edges
- **Active Edge List** → dynamic list of edges intersecting the current scanline

The AEL is updated each scanline.

### Incremental Intersection Updates
Instead of recomputing intersections:

$$x_{new} = x_{old} + \frac{dx}{dy}$$

This allows efficient incremental calculations.

### Parity Rule
Many scanline algorithms use an **even–odd rule**:

- fill pixels between every pair of edge intersections.

This determines the interior of the polygon.

## **Related**
[[Polygon]]
[[Vertex Table]]
[[Rasterization]]
Scanline Algorithm
Active Edge List

## **One Line Recall**
An edge table organizes polygon edges by starting scanline so scanline rasterization can efficiently determine which pixels to fill.