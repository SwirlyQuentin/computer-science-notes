## **Quick Summary**

Clip Space is a coordinate system in the graphics pipeline where vertices are tested against the viewable volume before projection to the screen.

---

## **Core Idea**

* Vertices are transformed by the projection matrix, producing homogeneous coordinates.
* Clipping algorithms determine which parts of geometry lie inside the view volume.
* Geometry outside the viewing region is discarded or split so only visible portions continue through the pipeline.
* Clip space coordinates still contain the w component, which is required for the later perspective divide.

---

## **What it is**

Clip Space is an intermediate coordinate system used in the graphics pipeline after applying the [[Projection Matrix]].

When vertices are transformed from view (camera) space, the projection matrix converts them into homogeneous clip coordinates `(x, y, z, w)`.

At this stage, the GPU determines whether geometry lies inside the viewing frustum. The valid region of clip space is defined by:
```
-w ≤ x ≤ w
-w ≤ y ≤ w
-w ≤ z ≤ w
```

Geometry that falls outside this region is clipped before continuing through the rendering pipeline.

After clipping, the system performs the perspective divide:
```
x_ndc = x / w
y_ndc = y / w
z_ndc = z / w
```

This converts coordinates from clip space → normalized device coordinates (NDC), which are later mapped to screen coordinates.

---

## **How its Used**

### Visibility Determination

Clip space is used to determine whether vertices and primitives lie inside the view frustum.

### Geometry Clipping

If triangles intersect the viewing volume boundary, they may be split into smaller primitives so that only the visible portion remains.

### Preparing for Screen Mapping

After clipping, the perspective divide converts clip coordinates into normalized coordinates that can be mapped to pixels during [[Rasterization]].

### Supporting Projection Types

Both perspective projection and orthographic projection produce clip space coordinates before the divide step.

---

## **Example**

### Example 1: Vertex Transformation Pipeline

A vertex goes through the following transformations:
```
Object Space
      ↓
World Space
      ↓
View (Camera) Space
      ↓
Projection Matrix
      ↓
Clip Space
      ↓
Perspective Divide
      ↓
Normalized Device Coordinates (NDC)
      ↓
Screen Coordinates
```

Clip space is the stage where visibility checks against the frustum occur.

### Example 2: Clipping Condition

Suppose a vertex after projection is:
```
(x, y, z, w) = (2, 0.5, 0.2, 1)
```

Check clip space bounds:
```
-w ≤ x ≤ w
-1 ≤ 2 ≤ 1   ❌
```

Since `x` lies outside the allowed range, the vertex is outside the viewing volume and will be clipped or discarded.

---

## **Details**

### Homogeneous Coordinates

Clip space uses homogeneous coordinates, meaning each vertex has a fourth component `w`. This allows perspective transformations to be represented with matrix multiplication.

### Perspective Divide

The perspective divide converts clip coordinates to normalized device coordinates:
```
(x, y, z, w) → (x/w, y/w, z/w)
```

This step creates the perspective effect where distant objects appear smaller.

### Clipping vs Culling

* **Clipping:** Splits primitives that intersect the frustum boundary.
* **Culling:** Removes primitives entirely when they face away or lie completely outside the view.

---

## **Related**

* [[Projection Matrix]]
* [[View Space]]
* [[World Space]]
* [[Homogeneous Coordinates]]
* [[Normalized Device Coordinates]]
* [[Rasterization]]

---

## **One Line Recall**

Clip space is the coordinate system after projection where geometry is tested against the viewing frustum before the perspective divide.