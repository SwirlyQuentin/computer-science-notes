## **Quick Summary**

An Application Database is the collection of internal data structures a program uses to store and manage all information about a scene.

---

## **Core Idea**

* Scene information is stored as **structured data representing objects and their properties**.
* Objects in the scene are typically represented as **records containing geometry, transformations, and materials**.
* Systems like rendering, animation, and simulation **retrieve scene information from the database**.
* Scene data is often organized using **hierarchical or graph-based structures** to manage relationships between objects.

---

## **What it is**

An **Application Database** is the internal representation of all scene information maintained by a graphics application while it is running.

Instead of directly working with file formats, the program stores the scene in **in-memory data structures** that represent objects and their attributes. These structures allow the application to efficiently manage, update, and access scene data.

Typical information stored in an application database includes:

* Geometry data (meshes, vertices, faces)
* Object transformations (position, rotation, scale)
* Materials and textures
* Lighting information
* Camera parameters
* Scene hierarchy
* Animation or simulation data

The application database acts as the **central repository for all scene information**, allowing different parts of the program to access and modify the data as needed.

---

## **How its Used**

### Scene Management

The application database stores the complete description of the scene so the program can track all objects and their properties.

### Editing and Modeling

When a user modifies a model—such as moving vertices or adding objects—the program updates the information stored in the application database.

### Rendering

Rendering systems retrieve geometry, lighting, and camera information from the application database in order to generate images.

### Simulation and Animation

Animation systems update transformation or deformation data stored in the database as objects move or change over time.

---

## **Example**

### Example 1: Simple Scene Representation

A graphics application might store the following information in its application database:

| Scene Element | Stored Information                       |
| ------------- | ---------------------------------------- |
| Cube          | Vertex list, face connectivity, material |
| Light         | Position, color, intensity               |
| Camera        | Position, orientation, field of view     |

All scene elements and their properties are stored in structured data within the application database.

---

### Example 2: Game Engine Scene Data

A game engine may maintain an application database containing:

* Player character mesh
* Terrain geometry
* Enemy objects
* Light sources
* Physics objects

Each system in the engine accesses this database to retrieve or update scene information during gameplay.

---

## **Details**

### Scene Graph Organization

Many graphics programs organize the application database using a **scene graph**, which represents hierarchical relationships between objects.

Example structure:
```
Scene
 ├── Character
 │    ├── Head
 │    ├── Arms
 │    └── Legs
 └── Environment
      ├── Trees
      └── Buildings
```

Transformations applied to parent objects affect their children.

---

### In-Memory Representation

The application database exists **in memory while the program runs**. When a scene is saved, the information is written to a file format such as OBJ or FBX.

---

### Efficiency Considerations

Large scenes may contain:

* thousands of objects
* millions of vertices
* many textures and materials

Efficient data structures are necessary to allow **fast updates and rendering operations**.

---

## **Related**

* [[Scene Graph]]
* [[Triangular Mesh]]
* [[Rendering Pipeline]]
* [[Subdivision]]
* [[Geometry Processing]]

---

## **One Line Recall**

An Application Database is the in-memory set of data structures a program uses to store and manage all scene information.