## **Quick Summary**
The Display Model is the graphics system's internal representation of objects in a form ready for rendering. It contains the visual information needed to draw objects on the screen, such as geometry, transformations, and visual properties.

## **Core Idea**
In graphics systems, scene data is often separated into two representations:

- [[Application Model]] → logical or real-world data used by the application
- [[Display Model]] → visual representation optimized for rendering

The Display Model is what the graphics system actually uses when the scene is drawn to the screen.

Think of it this way:

- [[Application Model]] → *what the world is*
- **Display Model** → *how the world looks when rendered*

The Display Model exists so the graphics system can efficiently render objects without needing all the extra application-level information.

## **What it is**
The Display Model is a representation of graphical objects that contains the information necessary for rendering them on a display device. It is typically maintained by the graphics platform, graphics library, or rendering engine.

While the [[Application Model]] may contain many types of data (game logic, physics values, object IDs, etc.), the Display Model focuses only on **visual properties needed for rendering**.

The Display Model may include:

- geometric representations (vertices, meshes, shapes)
- transformations (position, rotation, scaling)
- color and material properties
- texture information
- rendering state

Because it is designed for rendering, the Display Model is often organized in structures optimized for drawing, such as a [[Scene Graph]] or GPU buffers.

In systems using [[Retained Mode]], the graphics framework maintains and updates the Display Model internally.

## **How its Used**
The Display Model is used by the rendering system to generate the final image that appears on the screen.

Typical pipeline:

1. The application stores objects in the [[Application Model]].
2. The rendering system converts or maps that data into the **Display Model**.
3. The Display Model organizes the visual representation of objects.
4. The graphics pipeline renders the objects into the [[Frame Buffer]].
5. The resulting image is displayed on the screen.

The Display Model allows graphics systems to:

- optimize rendering
- cache visual objects
- manage redraws efficiently
- organize objects for rendering order

This separation is especially important in large systems such as:

- game engines
- GUI frameworks
- visualization tools
- CAD software

## **Example**

### Example 1: Application vs Display Data

A game object in the [[Application Model]] might contain:
```cpp
class Enemy
{
    Mesh mesh;
    Vector3 position;
    int health;
    int damage;
}
```

The Display Model only needs the visual information:
```cpp
DisplayObject
{
    Mesh mesh;
    Transform transform;
    Material material;
}
```

Notice that **gameplay data (health, damage)** is not needed for rendering.

### Example 2: Rendering From the Display Model

The renderer may iterate through display objects:
```
for each displayObject in displayModel
    send geometry to GPU
    apply transformations
    draw object
```

This representation is optimized for drawing and eventually produces pixels in the [[Frame Buffer]].

## **Details**

### Rendering Optimization

The Display Model allows graphics systems to organize objects for efficient rendering. This may include:

- batching similar objects
- storing geometry in GPU buffers
- hierarchical transformations

### Scene Graph Representation

Many retained graphics systems represent the Display Model using a [[Scene Graph]]. This hierarchical structure allows transformations and properties to propagate through the scene.

### Relationship to Retained Mode

In [[Retained Mode]], the graphics system maintains the Display Model internally and updates it when object properties change.

In [[Immediate Mode]], the system typically does **not maintain a persistent Display Model**, since primitives are drawn and discarded each frame.

## **Related**

[[Application Model]]
[[Retained Mode]]
[[Immediate Mode]]
[[Scene Graph]]
[[Frame Buffer]]

## **One Line Recall**

The Display Model is the graphics system's internal representation of objects optimized for rendering to the screen.