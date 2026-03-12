## **Quick Summary**
The Application Model is the internal representation of a scene maintained by the application. It stores both geometric data (like shapes and positions) and non-geometric data (like object properties or behavior) in an [[Application Database]].

## **Core Idea**
- The **application owns the scene description**.
- All objects and their properties are stored in an [[Application Database]].
- The application uses this model to **generate rendering commands** for the graphics system.
- The model can include both **geometry and application-specific information**.

## **What it is**
The Application Model is a data structure maintained by the application that represents everything in the scene. It contains information needed to construct and manage objects before they are rendered.

This model typically includes:

**Geometric information**
- vertices
- edges
- surfaces
- meshes
- transformations (position, rotation, scale)

**Non-geometric information**
- object names
- object types
- materials or colors
- physics properties
- game logic or metadata

All of this information is stored in an [[Application Database]], which is the application's internal storage for scene objects.

The graphics API does not necessarily know about this structure. Instead, the application **translates the Application Model into rendering commands** that are sent to the graphics system.

In systems using [[Immediate Mode]], the Application Model is the **only place where scene data exists**, since the graphics platform does not store objects.

## How its Used
The Application Model is used by programs that render or simulate graphical scenes.

Typical workflow:

1. The application builds the scene in the **Application Model**.
2. Objects and properties are stored in the [[Application Database]].
3. The application processes the model (animation, physics, updates).
4. Rendering commands are generated from the model.
5. These commands are sent to the graphics system.

This model is essential in:
- **game engines**
- **CAD systems**
- **3D modeling software**
- **scientific visualization**
- **simulation software**

For example, in a game engine, the Application Model might contain:

- player objects
- enemy objects
- terrain meshes
- lighting data
- physics components

The renderer then converts that information into triangles and sends them to the GPU.

## **Example**

### Example 1: Game Object in an Application Model

A game engine might store objects like this:
```cpp
class GameObject
{
    Mesh mesh;
    Vector3 position;
    Vector3 rotation;
    Material material;
    int health;
};
```

Here:
- **Mesh** → geometric information
- **Position/Rotation** → transformations
- **Material** → rendering property
- **Health** → non-geometric gameplay data

All objects would be stored in the application's [[Application Database]].

### Example 2: Rendering From the Application Model

Rendering might iterate through the stored objects:
```cpp
for (GameObject obj : sceneObjects)
{
    drawMesh(obj.mesh, obj.position, obj.rotation);
}
```

The Application Model provides the data used to **generate rendering commands**.

## **Details**

### Application Database

The [[Application Database]] stores the complete scene description used by the program. It often contains structures like:

- scene graphs
- object lists
- spatial hierarchies
- component systems

### Separation From Rendering

A key idea in graphics architecture is that the **application model is separate from the display system**.

This separation allows:

- easier updates to objects
- simulation and physics
- scene editing
- efficient rendering pipelines

### Relationship to Retained Mode

In [[Retained Mode]], the graphics system may maintain its own representation called a [[Display Model]].
In [[Immediate Mode]], the Application Model is the **only stored scene representation**.

## **Related**

[[Application Database]]
[[Immediate Mode]]
[[Retained Mode]]
[[Display Model]]
[[Frame Buffer]]

## **One Line Recall**

The Application Model is the application's internal scene representation storing both geometric and non-geometric data in an [[Application Database]].