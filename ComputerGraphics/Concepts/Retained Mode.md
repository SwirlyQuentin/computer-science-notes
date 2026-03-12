## **Quick Summary**
Retained Mode is a graphics programming model where the graphics system stores and manages the scene internally. Instead of redrawing every object each frame, the application describes what objects exist and the framework automatically handles rendering and updates.

## **Core Idea**
- The graphics system maintains its own representation of the scene called a [[Display Model]].
- The application describes objects and their properties.
- The framework stores these objects, often using a [[Scene Graph]].
- The system automatically redraws the scene when changes occur.
- The application usually only updates **object properties** instead of issuing full draw commands.

## **What it is**
Retained Mode is a rendering approach where the graphics framework retains (stores) the scene description after it is created. The application provides objects such as shapes, images, or UI elements, and the system keeps them in memory.

Instead of repeatedly sending drawing commands every frame (as in [[Immediate Mode]]), the application defines objects and their attributes. The graphics system then manages:

- storage of scene elements
- rendering order
- redraw operations
- performance optimizations

This stored scene representation is often called a [[Display Model]]. Internally, many retained systems organize the scene using a [[Scene Graph]], which is a hierarchical structure of graphical objects.

When the scene changes (for example, an object's position changes or the window resizes), the framework automatically determines what must be redrawn.

## How its Used
Retained Mode is commonly used in high-level graphics frameworks and UI systems where ease of development and automatic rendering management are important.

Common uses include:

- GUI frameworks
- web graphics
- vector graphics systems
- many modern game engines
- visualization frameworks

Examples of systems using Retained Mode include:
- [[WPF]] (Windows Presentation Foundation)
- [[SVG]] (Scalable Vector Graphics)
- most modern game engines with scene management systems

In these systems, developers describe objects and update their properties instead of issuing low-level draw commands.

Typical workflow:

1. The application creates graphical objects.
2. The system stores them in its internal scene representation.
3. The system manages rendering automatically.
4. When properties change, the framework updates the display.

## **Example**

### Example 1: UI Element in Retained Mode

A developer defines a rectangle once:
```xml
<Rectangle Width="100" Height="50" Fill="Blue"/>
```

The framework stores this object and handles rendering.

If the window resizes or moves, the system redraws the rectangle automatically.

### Example 2: Updating Properties

Instead of redrawing the object manually, the application changes a property:
```pseudo
rectangle.position.x = 200
```

The framework detects the change and redraws the scene when needed.

### Example 3: Scene Graph Concept

A retained system might internally organize objects like this:
```
Scene
 ├── UI Layer
 │   ├── Button
 │   └── Panel
 └── Game Objects
     ├── Player
     └── Enemy
```

Each node stores properties and transformations.

## **Details**

### Display Model

In Retained Mode, the graphics system maintains a [[Display Model]], which is the platform's internal representation of the scene.

### Scene Graph

Many retained systems use a [[Scene Graph]] to organize objects hierarchically. This allows transformations and properties to propagate through the hierarchy.

### Automatic Redrawing

The framework can optimize rendering by:

- redrawing only changed regions
- caching objects
- batching drawing operations

This reduces the need for the application to manually manage rendering updates.

### Comparison With Immediate Mode

- [[Immediate Mode]]: application sends draw commands every frame.
- Retained Mode: system stores objects and manages rendering.

## **Related**

[[Immediate Mode]]
[[Application Model]]
[[Display Model]]
[[Scene Graph]]
[[WPF]]
[[SVG]]

## **One Line Recall**

Retained Mode is a graphics model where the system stores the scene internally and automatically handles rendering when object properties change.