## **Quick Summary**
A polygon is a closed 2D shape formed by connecting straight line segments between an ordered set of vertices. In computer graphics, polygons are fundamental primitives used to represent shapes, surfaces, and boundaries.

## **Core Idea**
- A polygon is formed from an **ordered list of vertices**
- Adjacent vertices form **edges**
- The last vertex connects back to the first to create a **closed shape**
- Polygons are widely used to represent **2D shapes and 3D surfaces**

Polygons form the basis of many graphics operations and are commonly reduced to **triangles** for rendering.

## **What it is**
A polygon is a geometric shape defined by a sequence of vertices connected by straight edges that form a closed boundary.

If a polygon has vertices:

$$V_0, V_1, V_2, ..., V_{n-1}$$

then the edges are:

$$(V_0,V_1), (V_1,V_2), ..., (V_{n-1},V_0)$$

This final connection closes the shape.

Key components:

- **Vertex** → a point defining a corner of the polygon
- **Edge** → line segment between two vertices
- **Boundary** → closed loop of edges

A polygon whose edges do not intersect is called a **simple [[Polygon]]**.

If the first and last vertices connect in a polyline, the shape becomes a **closed polyline**, which forms a polygon.

## **How its Used**
Polygons are one of the most important primitives in computer graphics.

They are used in:

- 2D drawing systems
- raster graphics rendering
- vector graphics
- game engines
- geometric modeling
- surface representation in 3D graphics

Most real-time rendering pipelines convert geometry into **triangles**, since triangles are always planar and easy for GPUs to process.

Typical workflow in a graphics system:

1. Define vertices of the polygon.
2. Construct edges from consecutive vertices.
3. Store geometry using structures such as [[Vertex Table]] and edge tables.
4. Triangulate the polygon if needed.
5. Apply transformations and render.

## **Example**

### Example 1: Polygon With 4 Vertices

A quadrilateral may be defined by:

$$V_0=(0,0),\quad V_1=(4,0),\quad V_2=(4,3),\quad V_3=(0,3)$$

Edges:

$$(V_0,V_1), (V_1,V_2), (V_2,V_3), (V_3,V_0)$$

This forms a rectangle.

### Example 2: Area of a Polygon (Shoelace Formula)

For a polygon with vertices:

$$(x_1,y_1), (x_2,y_2), ..., (x_n,y_n)$$

Area:

$$A=\frac{1}{2}\left|\sum_{i=1}^{n} (x_i y_{i+1} - x_{i+1} y_i)\right|$$

This formula is commonly used in computational geometry.

### Example 3: GPU Rendering

A polygon may be converted into triangles:
```
Polygon → Triangulation → Triangles → Rasterization
```

This makes rendering more efficient on GPUs.

## **Details**

### Convex vs Concave
Polygons are commonly categorized as:

- [[Convex Polygon]] → any line between two points inside stays inside
- Concave polygon → at least one line between interior points exits the polygon

Convex polygons are easier to process for many algorithms.

### Vertex Ordering
Vertices are usually stored in **counterclockwise order**.

This helps determine:

- inside vs outside
- polygon orientation
- surface normals in 3D

### Representation in Graphics Systems
Polygons are commonly stored using:

- [[Vertex Table]] (list of coordinates)
- edge tables referencing vertex indices

This representation avoids storing duplicate vertices.

### Self-Intersecting Polygons
Polygons whose edges cross are called **complex polygons** and often require special handling in graphics algorithms.

## **Related**
[[Polyline]]
[[Convex Polygon]]
[[Vertex Table]]
[[Edge Table]]
[[Spline]]

## **One Line Recall**
A polygon is a closed shape formed by connecting straight edges between an ordered set of vertices.