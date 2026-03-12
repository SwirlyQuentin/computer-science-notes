## **Quick Summary**
Immediate Mode is a graphics rendering approach where the application directly sends drawing commands to the graphics system every frame. The graphics platform does not store the scene; instead, the application is responsible for resending all primitives whenever the scene is redrawn.

## **Core Idea**
- Rendering is **stateless on the graphics platform**.
- The **application fully owns the scene representation** using the [[Application Model]].
- Every frame, the application **issues commands to draw primitives again**.
- The graphics system **does not retain geometry or scene structure**.

## **What it is**
Immediate Mode is a rendering model where graphical primitives (such as points, lines, and triangles) are sent directly to the graphics API for drawing. Once the primitives are drawn, the graphics system **does not store them**.

This means the application must continuously resend the entire scene whenever the display is refreshed.

The scene structure exists only inside the application in the [[Application Model]]. The graphics platform acts primarily as a **drawing engine** rather than a scene manager.

Historically, this approach was common in early graphics APIs such as legacy [[OpenGL]] and certain rendering workflows using [[DirectX]]. However, modern graphics pipelines often favor retained-style or buffer-based approaches for efficiency.

## How its Used
Immediate Mode is used when the application wants **full control over rendering** and is willing to manage all scene data itself.

Common uses include:
- Early real-time graphics systems
- Simple visualization tools
- Educational graphics programs
- Debug rendering
- GUI systems that redraw every frame

In older OpenGL versions, Immediate Mode allowed developers to send vertices directly during rendering.

Example workflow:
1. Application computes geometry.
2. Application sends drawing commands to the graphics API.
3. Graphics system renders primitives.
4. On the next frame, the application repeats the process.

Because nothing is stored by the graphics platform, **the full scene must be redrawn each frame**.

## **Example**

### Example 1: Immediate Mode Rendering (Conceptual OpenGL Style)
```cpp
glBegin(GL_TRIANGLES);

glVertex3f(0.0f, 0.0f, 0.0f);
glVertex3f(1.0f, 0.0f, 0.0f);
glVertex3f(0.0f, 1.0f, 0.0f);

glEnd();
```

In this example:
- Each frame, the application explicitly sends the triangle vertices.
- The graphics system draws the triangle but does not remember it afterward.

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

## Details

### Stateless Rendering
Immediate Mode is stateless with respect to scene geometry. The graphics system processes primitives but does not store them for later reuse.

### CPU Responsibility
Because the application owns the scene data, the CPU is responsible for:
- storing geometry
- organizing objects
- issuing draw commands every frame

### Performance Considerations
Immediate Mode is generally less efficient for complex scenes because:
- geometry must be resent repeatedly
- the CPU must issue many draw calls
- the GPU cannot reuse stored geometry

Modern graphics APIs instead use vertex buffers and retained data structures.

## Related
[[Retained Mode]]
[[Application Model]]
[[Display Model]]
[[Frame Buffer]]
[[Raster Graphics]]
[[OpenGL]] 
[[DirectX]]

## One Line Recall
Immediate Mode is a rendering method where the application sends all drawing commands each frame while the graphics platform stores no scene data.