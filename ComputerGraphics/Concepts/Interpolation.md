## **Quick Summary**

Interpolation is the process of estimating values between known data points by constructing a function that passes exactly through those points.

---

## **Core Idea**

* Interpolation constructs a function that matches all known sample values exactly.
* Known data points act as constraints the function must satisfy.
* The resulting function can be used to estimate intermediate values.
* Different interpolation methods balance accuracy, smoothness, and computational cost.

---

## **What it is**

Interpolation is a mathematical technique used to estimate values between known sample points.

Given a set of samples:
```
(x₀, y₀), (x₁, y₁), ..., (xₙ, yₙ)
```

Interpolation constructs a function `f(x)` such that:
```
f(xᵢ) = yᵢ
```

for every sample point.

This means the resulting function passes exactly through the known data points while providing values for positions between them.

Interpolation is commonly used when data is discrete but continuous values are needed, such as reconstructing smooth curves, images, or motion paths.

---

## **How its Used**

### Graphics Rendering

Interpolation is used to compute values across surfaces, such as color, depth, and texture coordinates during [[Rasterization]].

### Texture Mapping

Texture coordinates are interpolated across triangles so that textures appear smoothly mapped onto surfaces.

### Animation

Interpolation blends between keyframes to produce smooth motion in animation systems.

### Image Processing

When resizing images, interpolation estimates new pixel values between existing pixels.

### Signal Processing

Interpolation is used to reconstruct or resample signals from discrete measurements.

---

## **Example**

### Example 1: Linear Interpolation

Suppose two known points:
```
(0, 2) and (4, 10)
```

To estimate the value at `x = 2`, we use linear interpolation:
```
f(x) = y₀ + (x - x₀) * (y₁ - y₀) / (x₁ - x₀)
```

Substituting values:
```
f(2) = 2 + (2 - 0) * (10 - 2) / (4 - 0)
     = 2 + 2 * 8 / 4
     = 2 + 4
     = 6
```

So the interpolated value is 6.

### Example 2: Graphics Attribute Interpolation

In a triangle with colored vertices:
```
Red      Green
   \    /
    \  /
    Blue
```

During rasterization, colors between vertices are interpolated so the triangle appears smoothly shaded.

---

## **Details**

### Common Interpolation Methods

**Nearest Neighbor**
* Uses the closest sample value
* Very fast but produces blocky results

**Linear Interpolation**
* Uses straight-line interpolation between points
* Simple and widely used

**Polynomial Interpolation**
* Uses a single polynomial to pass through all points
* Can produce oscillations with many points

**[[Spline]] Interpolation**
* Uses piecewise polynomials
* Produces smooth curves with better stability

### Interpolation vs Approximation

**Interpolation**
* Must pass through all sample points
```
f(xᵢ) = yᵢ
```

**Approximation**
* Attempts to follow the trend of the data
* May not pass through every sample point

Approximation methods are often used when data contains noise or measurement errors.

### Stability Considerations

High-degree polynomial interpolation may produce large oscillations, especially near the boundaries of the data range (Runge's phenomenon).

Spline-based methods help avoid this issue by using multiple low-degree polynomials instead of one large polynomial.

---

## **Related**

* [[Linear Interpolation]]
* [[Spline]]
* [[Bezier Curve]]
* [[Hermite Curve]]
* [[Rasterization]]

---

## **One Line Recall**

Interpolation estimates values between known data points while ensuring the resulting function passes through the original samples.