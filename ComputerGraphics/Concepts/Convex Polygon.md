## **Quick Summary**
A convex polygon is a polygon where any line segment drawn between two points inside the shape remains completely inside the polygon. Convex polygons have no inward dents, which makes many graphics algorithms simpler and faster.

## **Core Idea**
- All **interior angles are less than 180°**
- Any line between two points inside the polygon **stays inside**
- The boundary consistently turns in **one orientation** (usually counterclockwise)
- Convex polygons are easier to process in graphics algorithms

Because of these properties, convex polygons avoid many geometric edge cases.

## **What it is**
A convex polygon is a type of [[Polygon]] in which the shape bulges outward and contains no inward indentations.

If two points $A$ and $B$ lie inside the polygon, the entire line segment between them also lies inside the polygon.

Formally:

$$\forall A,B \in P,\quad \text{segment } AB \subseteq P$$

Where $P$ represents the polygon.

Another equivalent definition is that every interior angle satisfies:

$$\theta_i < 180^\circ$$

Examples of convex polygons include:
- triangles
- rectangles
- squares
- regular polygons

Convex polygons are especially useful because they guarantee predictable geometric behavior.

## **How its Used**
Convex polygons are commonly used in computer graphics and computational geometry because they simplify many algorithms.

Typical uses include:

- collision detection in physics engines
- polygon clipping
- rendering pipelines
- triangulation
- hit testing
- spatial partitioning

Many graphics systems also convert complex shapes into **sets of convex polygons** to make rendering and physics calculations easier.

In real-time graphics, shapes are often decomposed into triangles, which are always convex.

## **Example**

### Example 1: Convex Quadrilateral

Vertices:

$$V_0=(0,0),\quad V_1=(4,0),\quad V_2=(4,3),\quad V_3=(0,3)$$

All interior angles are:

$$90^\circ$$

Any segment between interior points stays inside the polygon.

### Example 2: Convexity Test Using Cross Products

For consecutive edges:

$$E_i = V_{i+1}-V_i$$

Compute the cross product of adjacent edges:

$$E_i \times E_{i+1}$$

If all cross products have the **same sign**, the polygon is convex.

Pseudo workflow:

1. Walk vertices in order.
2. Compute cross-product sign for each edge pair.
3. If all signs match → polygon is convex.

### Example 3: Convex vs Concave

Convex polygon:
```
  /\
 /  /
/____\
```

Concave polygon:
```
  /\
 /  /
/_  _/
```

The concave version contains an inward indentation.

## **Details**

### Algorithmic Simplicity
Convex polygons simplify many operations:

- intersection tests
- clipping algorithms
- point-in-polygon tests
- collision detection

This is because there is only **one continuous interior region**.

### Convex Decomposition
Complex shapes are often broken into multiple convex polygons.

This process is called **convex decomposition** and is widely used in:

- physics simulations
- mesh processing
- game engines

### Numerical Issues
Real-world implementations must handle:

- collinear vertices
- duplicate points
- floating-point rounding errors

Tolerance checks are usually required.

## **Related**
[[Polygon]]
Concave Polygon
[[Vertex Table]]
[[Edge Table]]
[[Spline]]

## **One Line Recall**
A convex polygon is a polygon with no inward dents where every line segment between interior points remains inside the shape.