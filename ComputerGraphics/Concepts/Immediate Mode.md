## **Quick Summary**

Immediate Mode is a graphics rendering approach where the application directly sends drawing commands to the graphics system every frame. The graphics platform does not store the scene; instead, the application is responsible for resending all primitives whenever the scene is redrawn.

---

## **Core Idea**

* Rendering is **stateless on the graphics platform**.
* The **application fully owns the scene representation** using the [[Application Model]].
* Every frame, the application **issues commands to draw primitives again**.
* The graphics system **does not retain geometry or scene structure**.
* Vertices are sent **one at a time**, which can create **many draw operations and slow performance**.

---

## **What it is**

Immediate Mode is a rendering model where graphical primitives (such as points, lines, and triangles) are sent directly to the graphics API for drawing. Once the primitives are drawn, the graphics system **does not store them**.

This means the application must continuously resend the entire scene whenever the display is refreshed.

The scene structure exists only inside the application in the [[Application Model]]. The graphics platform acts primarily as a **drawing engine** rather than a scene manager.

In systems like legacy [[OpenGL]], Immediate Mode works by issuing commands between `glBegin()` and `glEnd()` calls. Every vertex is individually transmitted to the GPU.

This approach produces a **large number of draw operations**, because every primitive requires multiple vertex submissions.

Because the GPU does not store the geometry, the CPU must repeatedly send the same data every frame.

Historically, Immediate Mode was common in early graphics APIs such as legacy [[OpenGL]] and certain rendering workflows using [[DirectX]]. However, modern graphics pipelines favor **buffer-based approaches** like [[Vertex Buffer Object (VBO)]]s that allow geometry to remain stored on the GPU.

---

## **How its Used**

Immediate Mode is used when the application wants **full control over rendering** and is willing to manage all scene data itself.

Common uses include:

* Early real-time graphics systems
* Simple visualization tools
* Educational graphics programs
* Debug rendering
* GUI systems that redraw every frame

Example workflow:

1. Application computes geometry.
2. Application sends drawing commands to the graphics API.
3. Graphics system renders primitives.
4. On the next frame, the application repeats the process.

Because nothing is stored by the graphics platform, **the full scene must be redrawn each frame**.

In large scenes (such as voxel worlds), this approach becomes extremely inefficient because millions of vertices would need to be sent to the GPU repeatedly.

---

## **Example**

### Example 1: Immediate Mode Rendering (Conceptual OpenGL Style)
```cpp
glBegin(GL_TRIANGLES);

glVertex3f(0.0f, 0.0f, 0.0f);
glVertex3f(1.0f, 0.0f, 0.0f);
glVertex3f(0.0f, 1.0f, 0.0f);

glEnd();
```

Each frame, the application explicitly sends the triangle vertices. The graphics system draws the triangle but does not remember it afterward.

### Example 2: Frame Rendering Loop
```
while(running)
{
    clearScreen()

    drawTriangle()
    drawCube()
    drawSphere()

    displayFrame()
}
```

Every frame, all objects must be redrawn from scratch.

### Example 3: Voxel Rendering Problem

Imagine rendering a voxel world with **1,000,000 cubes**.

Each cube requires multiple vertices to render its faces. If each vertex is submitted individually:
```
1,000,000 cubes × many vertices per cube = millions of vertex submissions
```

This results in extremely poor performance.

Modern engines instead batch geometry using [[Vertex Array]] or [[Vertex Buffer Object (VBO)]] systems.

---

## **Details**

### Stateless Rendering

Immediate Mode is stateless with respect to scene geometry. The graphics system processes primitives but does not store them for later reuse.

### CPU Responsibility

Because the application owns the scene data, the CPU is responsible for:

* storing geometry
* organizing objects
* issuing draw commands every frame

### Performance Considerations

Immediate Mode is inefficient for complex scenes because:

* geometry must be resent every frame
* the CPU must issue many vertex commands
* the GPU cannot reuse previously submitted geometry
* many small draw operations occur

Performance ranking (slowest to fastest):
```
Immediate Mode
Vertex Arrays
Display Lists
Vertex Buffer Objects
```

### Modern Graphics Pipelines

Modern graphics APIs instead use **retained data structures** such as:

* [[Vertex Buffer Object (VBO)]]
* [[Vertex Array]]
* GPU memory buffers

These allow geometry to remain stored on the GPU, drastically improving performance.

---

## **Related**

* [[Retained Mode]]
* [[Application Model]]
* [[Display Model]]
* [[Frame Buffer]]
* [[Raster Graphics]]
* [[OpenGL]]
* [[DirectX]]
* [[Vertex Array]]
* [[Vertex Buffer Object (VBO)]]
* [[Draw Call]]

---

## **One Line Recall**

Immediate Mode is a rendering method where the application sends all drawing commands each frame while the graphics platform stores no scene data.