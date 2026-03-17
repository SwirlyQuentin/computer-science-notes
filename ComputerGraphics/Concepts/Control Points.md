## **Quick Summary**

Control points are reference points that define or influence the shape of curves and surfaces in geometric modeling.

---

## **Core Idea**

* Curves and surfaces are defined mathematically using points that influence their shape.
* Moving control points changes the geometry without directly editing the curve itself.
* Control points provide an indirect and structured way to manipulate complex shapes.
* Different curve formulations determine how strongly and how locally control points influence the geometry.

---

## **What it is**

A control point is a reference point used by a mathematical curve or surface representation to determine its shape.

Instead of storing every point on a curve, many modeling systems represent curves using a small set of control points. Mathematical functions then generate the actual curve based on these points.

An important distinction exists between two types of points used in curve modeling:

* [[Interpolation]] point – the curve must pass through this point.
* Control point – the curve is influenced by the point but does not necessarily pass through it.

Control points therefore act as shape guides that determine how the curve bends, stretches, or changes direction.

---

## **How its Used**

### Vector Graphics Editing

Control points act as handles that designers can drag to reshape vector paths in drawing software.

### Animation Paths

Motion paths for objects or cameras can be defined by curves whose shapes are controlled by control points.

### Geometric Modeling

Curves and surfaces used in modeling systems—such as splines and patches—are defined using sets of control points.

### CAD and Surface Design

Control points are used to construct smooth surfaces and curves in engineering and industrial design systems.

---

## **Example**

### Example 1: Quadratic Curve Control

A quadratic curve defined by three control points:
```
P0, P1, P2
```

* `P0` and `P2` determine the start and end points
* `P1` influences the direction and curvature

Moving `P1` changes the curve's bend without moving the endpoints.

### Example 2: Local vs Global Influence

Consider a curve with several control points:
```
P0  P1  P2  P3  P4
```

* In some curve types (like [[Bezier Curve]]), moving a point may influence the entire curve.
* In others (like B-splines), moving a control point only affects a local region of the curve.

---

## **Details**

### Behavior by Curve Family

**[[Bezier Curve|Bezier]]**

* Curve starts at the first control point and ends at the last.
* Interior control points influence the tangent direction and curvature.

**[[Hermite Curve|Hermite]]**

* Uses endpoint positions and tangent vectors to determine curve shape.

**B-spline Curves**

* Provide local control, meaning changes to one control point only affect nearby portions of the curve.

### Shape Control

The placement and spacing of control points strongly affects curve behavior:

* Closely spaced points can create sharp curvature
* Even spacing produces smoother shapes

### Potential Issues

Extreme placement of control points may cause:

* loops
* self-intersections
* unstable curvature

Many modeling systems provide constraints or alignment tools to maintain smoothness or symmetry.

---

## **Related**

* [[Bezier Curve]]
* [[Interpolation]]
* [[Spline]]
* [[Hermite Curve]]
* [[Parametric Curve]]

---

## **One Line Recall**

Control points are reference points that influence the shape of curves and surfaces without necessarily lying on them.