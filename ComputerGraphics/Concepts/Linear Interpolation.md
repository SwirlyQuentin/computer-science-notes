---
aliases:
  - LERP
---
## **Quick Summary**

Linear interpolation (LERP) blends between two values using a parameter `t`, producing a value along the straight line between them.

---

## **Core Idea**

* Linear interpolation computes values along a straight-line path between two points.
* A parameter `t` controls how far the result lies between the endpoints.
* The interpolation is a weighted average of the two values.
* It forms the basic building block for many higher-level interpolation methods.

---

## **What it is**

Linear Interpolation (LERP) is a simple interpolation method used to estimate values between two known values.

The formula is:
```
LERP(a, b, t) = (1 − t)a + tb
```

An equivalent form is:
```
LERP(a, b, t) = a + t(b − a)
```

Where:

* `a` = starting value
* `b` = ending value
* `t` = interpolation parameter

For `t ∈ [0,1]`:

| t value | Result   |
| ------- | -------- |
| 0       | a        |
| 0.5     | midpoint |
| 1       | b        |

As `t` increases from 0 to 1, the result moves smoothly from `a` to `b`.

---

## **How its Used**

### Animation

LERP is used to interpolate positions, colors, and other properties between keyframes.

### Graphics Rendering

During [[Rasterization]], vertex attributes such as color, depth, and texture coordinates are interpolated across triangle surfaces.

### UI and Motion Effects

LERP controls smooth transitions in UI elements, camera motion, and object movement.

### Texture Sampling

More advanced techniques like bilinear and trilinear [[Interpolation]] are built from multiple linear interpolations.

---

## **Example**

### Example 1: Numeric Interpolation

Suppose:
```
a = 10
b = 20
t = 0.3
```

Using the formula:
```
LERP(a, b, t) = a + t(b − a)
```

Substitute values:
```
= 10 + 0.3(20 − 10)
= 10 + 0.3 * 10
= 13
```

The interpolated value is 13.

### Example 2: Position Interpolation

If an object moves between two positions:
```
A = (0,0)
B = (10,0)
t = 0.5
```

Then:
```
P = LERP(A, B, 0.5) = (5,0)
```

The object is halfway between the two positions.

---

## **Details**

### Extrapolation

If `t` is outside `[0,1]`, the formula still works but produces extrapolated values.

Example:
```
t > 1 → value beyond b
t < 0 → value before a
```

This may or may not be desirable depending on the application.

### Relation to Distance

In geometric contexts, LERP produces points along a straight line between two points.

This makes it useful for:

* path generation
* edge interpolation
* linear motion

### Limitations

Linear interpolation has several limitations:

* Only produces straight-line transitions
* Uniform parameter `t` may not correspond to uniform speed in world space
* Not suitable for large-angle rotations (methods like spherical interpolation are often used instead)

### Time-Based Animation

In animation systems, the interpolation parameter is often computed using time:
```
t = elapsed_time / total_duration
```

This allows smooth transitions over time.

---

## **Related**

* [[Interpolation]]
* [[Spline]]
* [[Bezier Curve]]
* [[Hermite Curve]]
* [[Rasterization]]

---

## **One Line Recall**

Linear interpolation (LERP) computes a straight-line blend between two values using a parameter `t`.