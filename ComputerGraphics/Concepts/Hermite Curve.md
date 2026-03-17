---
aliases:
  - Hermite
---
## **Quick Summary**

A Hermite curve is a cubic [[Parametric Curve]] defined by two endpoints and their tangent vectors, allowing direct control over the curve's position and direction at the endpoints.

---

## **Core Idea**

* A Hermite curve is defined using endpoint positions and endpoint tangents.
* The curve interpolates its endpoints, meaning it passes through them exactly.
* Tangent vectors determine the direction and rate of change of the curve at each endpoint.
* Cubic basis functions blend positions and tangents to generate the curve.

---

## **What it is**

A Hermite curve is a cubic parametric curve used in computer graphics and geometric modeling.

A single Hermite segment is defined by:

* `P0` – starting point
* `P1` – ending point
* `T0` – tangent vector at the start
* `T1` – tangent vector at the end

The curve parameter `t` varies from 0 to 1, producing points along the curve.

The Hermite curve equation is:
```
P(t) = h00(t)P0 + h10(t)T0 + h01(t)P1 + h11(t)T1
```

Where the Hermite basis functions are:
```
h00(t) =  2t^3 - 3t^2 + 1
h10(t) =  t^3 - 2t^2 + t
h01(t) = -2t^3 + 3t^2
h11(t) =  t^3 - t^2
```

These basis functions blend the endpoint positions and tangents to create a smooth curve between `P0` and `P1`.

---

## **How its Used**

### Path and Motion Design

Hermite curves allow designers to control how an object enters and exits a point, which is useful for motion paths and camera movement.

### Animation Systems

Animation frameworks sometimes use Hermite curves as intermediate representations for controlling smooth motion and interpolation.

### Curve and Spline Construction

Hermite segments can be combined to form larger [[Spline]] curves used in modeling and animation.

### Procedural Motion

Game engines and simulations use Hermite interpolation to generate smooth transitions between positions.

---

## **Example**

### Example 1: Hermite Segment

Suppose we define:
```
P0 = (0,0)
P1 = (4,2)

T0 = (2,1)
T1 = (1,-1)
```

* `P0` and `P1` determine where the curve starts and ends.
* `T0` and `T1` control the direction and curvature at the endpoints.

Changing the tangent vectors modifies the shape of the curve without moving the endpoints.

### Example 2: Tangent Effect

If the magnitude of a tangent vector increases:
```
T0 → larger magnitude
```

the curve initially moves farther in that direction, creating stronger curvature or potential overshoot.

---

## **Details**

### Endpoint Interpolation

Hermite curves always pass through their endpoints:
```
P(0) = P0
P(1) = P1
```

### Tangent Control

The derivative of the curve at the endpoints equals the tangent vectors:
```
P'(0) = T0
P'(1) = T1
```

This allows precise control of the curve's entry and exit direction.

### Continuity Between Segments

When multiple Hermite segments are connected, continuity conditions determine smoothness.

**C0 continuity**
* Endpoints meet
* Curves connect in position

**C1 continuity**
* Tangents match at the join
* Produces smooth directional transitions

### Tangent Generation

Tangents can be:

* Manually specified
* Computed automatically from neighboring points

Many spline systems derive tangents automatically to maintain smoothness.

---

## **Related**

* [[Parametric Curve]]
* [[Spline]]
* [[Bezier Curve]]
* [[Interpolation]]
* [[Control Points]]

---

## **One Line Recall**

A Hermite curve is a cubic parametric curve defined by endpoints and endpoint tangents that control direction and smoothness.