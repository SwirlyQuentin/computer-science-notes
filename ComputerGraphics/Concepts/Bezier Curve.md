---
aliases:
  - Bezier
---
## **Quick Summary**

A **Bezier Curve** is a [[parametric curve]] defined by a set of [[control points]] and Bernstein polynomials. It is widely used for smooth curve modeling in graphics, design tools, and animation paths.

---

## **Core Idea**

* A Bezier curve is defined by **a weighted combination of control points**.
* The weights are **Bernstein basis polynomials**, which vary smoothly as the parameter `t` moves from `0` to `1`.
* The curve shape is controlled indirectly through **control point positions rather than explicit equations**.
* The curve is **parametric**, meaning its position is computed as a function of a parameter `t`.
* Recursive geometric evaluation methods such as the **De Casteljau algorithm** allow stable computation of points on the curve.

---

## **What it is**

A **Bezier curve** is a mathematical curve used in computer graphics and geometric modeling to represent smooth shapes.

Given control points `P0, P1, ..., Pn`, a degree-`n` Bezier curve is defined as:
```
P(t) = Σ B_i,n(t) * P_i     for t ∈ [0,1]
```

Where the **Bernstein polynomial** is:
```
B_i,n(t) = C(n,i) (1 − t)^(n−i) t^i
```

and:

* `C(n,i)` is the **binomial coefficient**
* `t` is the curve parameter
* `P_i` are the **control points**

As `t` moves from **0 to 1**, the equation computes points that trace a smooth curve influenced by the control points.

---

## **How its Used**

### Vector Graphics

Bezier curves define **paths in vector graphics systems** such as font outlines and drawing tools.

### UI and Graphic Design

Design software uses Bezier curves to allow designers to **interactively shape curves with control handles**.

### Animation and Motion Paths

Bezier curves can represent **smooth motion trajectories** for objects or cameras.

### Modeling Workflows

Complex curves are built from **chains of connected Bezier segments**, allowing flexible shape construction.

---

## **Example**

### Example 1: Quadratic Bezier Curve

A quadratic Bezier curve has **three control points**:
```
P0, P1, P2
```

The curve equation becomes:
```
P(t) = (1−t)^2 P0 + 2(1−t)t P1 + t^2 P2
```

* `P0` → starting point
* `P1` → control point influencing curvature
* `P2` → ending point

Changing `P1` bends the curve without moving the endpoints.

---

### Example 2: Cubic Bezier Curve

A cubic Bezier curve has **four control points**:
```
P0, P1, P2, P3
```

Equation:
```
P(t) =
(1−t)^3 P0
+ 3(1−t)^2 t P1
+ 3(1−t) t^2 P2
+ t^3 P3
```

This is the **most commonly used Bezier curve** in graphics systems.

---

## **Details**

### Endpoint Properties

* The curve **starts at `P0`**
* The curve **ends at `Pn`**

The **tangent directions** at the endpoints are determined by nearby control points:

* Start tangent → direction of `P1 − P0`
* End tangent → direction of `Pn − P(n−1)`

---

### Convex Hull Property

A Bezier curve always lies **inside the convex hull of its control points**.

This property ensures:

* predictable curve behavior
* stable shape editing
* no unexpected oscillations.

---

### De Casteljau Algorithm

The **De Casteljau algorithm** computes points on a Bezier curve using **repeated linear interpolation between control points**.

Advantages:

* numerically stable
* easy to implement
* useful for subdivision and rendering.

---

### Degree and Control Points

The **degree of the curve** is determined by:
```
degree = number_of_control_points − 1
```

Examples:

| Control Points | Degree    |
| -------------- | --------- |
| 3              | Quadratic |
| 4              | Cubic     |

---

### Piecewise Bezier Curves

Long or complex shapes are usually constructed from **multiple connected Bezier segments**, often **cubic**, because:

* they are easy to control
* they provide sufficient flexibility
* they are efficient to compute.

---

## **Related**

* [[Parametric Curve]]
* [[Control Points]]
* [[De Casteljau Algorithm]]
* [[Spline Curves]]
* [[Bernstein Polynomial]]

---

## **One Line Recall**

A Bezier curve is a parametric curve defined by control points and Bernstein polynomials that smoothly interpolates between endpoints.