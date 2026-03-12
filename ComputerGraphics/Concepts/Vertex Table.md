## **Quick Summary**
A Vertex Table is a structured list that stores the attributes of every vertex used to define geometric objects. Each row represents one vertex and contains data such as position, color, normals, or texture coordinates.

## **Core Idea**
- Each row represents **one vertex**
- Stores **per-vertex attributes**
- Used as the main **geometry input for rendering pipelines**
- Works together with index/edge references to build shapes

The vertex table defines **what each vertex is**, while other structures define **how vertices connect**.

## **What it is**
A Vertex Table is a data structure used in computer graphics to store the geometric and attribute information associated with vertices.

Each entry in the table corresponds to a vertex and may include multiple properties such as:

- position $(x, y, z)$
- surface normal $(n_x, n_y, n_z)$
- texture coordinates $(u, v)$
- color $(r, g, b, a)$
- tangent and bitangent vectors
- animation data (bone weights and indices)

Conceptually, the table acts as a **database of vertex attributes** used to construct geometric primitives like triangles or lines.

In simple polygon representations (as discussed in the lecture), the vertex table stores coordinates and an [[Edge Table]] references vertex indices to define edges.

## **How its Used**
Vertex tables are a fundamental structure used in graphics pipelines and geometry processing.

Typical uses include:

- defining geometry in 2D and 3D scenes
- supplying vertex data to the GPU
- constructing primitives such as triangles or polygons
- enabling interpolation of attributes during [[Rasterization]]
- supporting animation and deformation of meshes

In rendering pipelines:

1. Vertex attributes are stored in the vertex table.
2. Indices or edge lists reference vertices.
3. The GPU processes vertices through vertex shaders.
4. Attributes are interpolated across fragments during rendering.

Using vertex tables avoids storing duplicate vertex information and allows efficient geometry reuse.

## **Example**

### Example 1: Simple Vertex Table

| Index | x | y |
|-------|---|---|
| 0 | 1 | 2 |
| 1 | 3 | 5 |
| 2 | 4 | 2 |

This table defines three vertices.

An [[Edge Table]] could then reference these indices to define edges.

### Example 2: Vertex Table with Attributes

| Index | Position | UV |
|-------|----------|----|
| 0 | (0,0,0) | (0,0) |
| 1 | (1,0,0) | (1,0) |
| 2 | (1,1,0) | (1,1) |
| 3 | (0,1,0) | (0,1) |

This defines a square using four vertices.

### Example 3: Indexed Geometry

Indices:

$$(0,1,2), (0,2,3)$$

These indices build two triangles from the vertex table to form a quad.
```
Vertex Table → Indices → Triangles → Rasterization
```

## **Details**

### Vertex Attributes
A vertex can store multiple types of attributes used during rendering:

- geometric position
- surface normals for lighting
- texture coordinates
- color information
- animation weights

These attributes allow shaders to compute lighting, shading, and textures.

### Relationship with Edge Tables
In many geometry representations:

- [[Vertex Table]] stores coordinates
- [[Edge Table]] references vertex indices to define edges

This avoids storing duplicate vertices.

### GPU Memory Layout
In modern graphics APIs, vertex tables are often stored in **vertex buffers**.

Design considerations include:

- interleaved vs separate attribute arrays
- memory alignment for GPU efficiency
- precision formats (float32, float16, packed values)

### Common Pitfalls
Problems that may occur include:

- incorrect attribute layout for shaders
- duplicated vertices increasing memory usage
- inconsistent vertex ordering affecting polygon orientation

## **Related**
[[Edge Table]]
[[Polygon]]
[[Interpolation]]
[[Rasterization]]
[[Bezier Curve]]

## **One Line Recall**
A vertex table stores the attributes of each vertex, while indices or edges determine how those vertices connect into geometric primitives.