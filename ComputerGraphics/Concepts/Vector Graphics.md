## **Quick Summary**
Vector Graphics represent images using mathematical descriptions of shapes such as lines, curves, and polygons instead of pixels. The image is generated from these equations during rendering, allowing it to scale to any size without losing quality.

## **Core Idea**
- Images are described using **mathematical primitives**
- Shapes are defined by **coordinates and equations**
- The image is computed **when rendered**
- Graphics are **resolution independent**
- Quality remains sharp when scaling

Vector graphics describe **how to draw an image**, rather than storing every pixel of the image.

## **What it is**
Vector graphics represent images using geometric primitives such as points, lines, curves, and shapes defined by mathematical equations.

Instead of storing a grid of pixel colors like [[Raster Graphics]], vector graphics store instructions such as:

- coordinates of points
- line segments
- Bézier curves
- shapes and paths
- transformations (scale, rotation, translation)

When the image is displayed, the graphics system evaluates these mathematical descriptions and converts them into pixels for the display device.

Because the image is generated mathematically, it can be scaled to any size without losing quality.

For example, a circle might be stored as:

$$(x - h)^2 + (y - k)^2 = r^2$$

Where:
- $h, k$ = center of the circle
- $r$ = radius

This equation defines the circle regardless of resolution.

## **How its Used**
Vector graphics are used in applications where images must scale cleanly or be easily edited.

Common uses include:

- logos
- diagrams
- technical illustrations
- UI elements
- digital fonts
- maps
- icons

Many modern systems also use vector graphics for web and UI rendering.

For example, web graphics frequently use [[SVG]] (Scalable Vector Graphics), which describes shapes using coordinates and path instructions.

When displayed on a raster screen, the vector description is **converted into pixels during rendering**.

## **Example**

### Example 1: Line Defined by Two Points

A line segment can be represented using coordinates:

$$P_1 = (x_1, y_1)$$
$$P_2 = (x_2, y_2)$$

The graphics system draws a line between these two points.

### Example 2: Bézier Curve

Vector graphics often use **Bézier curves** to represent smooth shapes.

A cubic Bézier curve is defined as:

$$B(t) = (1-t)^3P_0 + 3(1-t)^2tP_1 + 3(1-t)t^2P_2 + t^3P_3$$

Where:
- $P_0, P_1, P_2, P_3$ are control points
- $t$ ranges from 0 to 1

These curves allow smooth shapes used in fonts, icons, and illustrations.

### Example 3: Simple SVG Shape
```xml
<circle cx="100" cy="100" r="50" fill="blue"/>
```

This instruction tells the renderer to draw a circle at the given coordinates rather than storing pixel colors.

## **Details**

### Resolution Independence
Because shapes are defined mathematically, vector graphics can be scaled indefinitely without pixelation.

### Rendering to Raster Displays
Most display hardware uses raster displays, so vector graphics must eventually be **converted into pixels** through rasterization before appearing on the screen.

### Performance Characteristics
Vector graphics work well for scenes with relatively few primitives. However, as the number of shapes increases, rendering can become slower because the system must recompute the image each time.

### Editing Advantages
Vector graphics are easier to modify because shapes remain separate objects that can be individually transformed or edited.

## **Related**
[[Raster Graphics]]
[[SVG]]
[[Frame Buffer]]
[[Rasterization]]
[[Spline]]

## **One Line Recall**
Vector graphics represent images using mathematical descriptions of shapes that can scale infinitely without losing quality.