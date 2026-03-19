---
aliases:
  - Vertex Buffer Object
  - VBO
---
## **Quick Summary**

A Vertex Buffer Object (VBO) stores vertex data directly in GPU memory so it can be rendered efficiently.

---

## **Core Idea**

Instead of sending vertex data to the GPU every frame, a VBO stores that data **once in GPU memory**, allowing it to be reused quickly for rendering.

This significantly reduces **CPU → GPU communication**, improving performance.

---

## **What it is**

A **Vertex Buffer Object (VBO)** is an OpenGL object used to store vertex data in **GPU memory**.

Vertex data can include:

* vertex positions
* normals
* texture coordinates
* colors
* indices

In older rendering approaches, vertex data is repeatedly sent from the CPU to the GPU every frame.

With a VBO:

1. Data is uploaded to the GPU once.
2. The GPU reuses that data whenever it needs to render.

This makes rendering **much faster**, especially for large meshes or frequently rendered objects.

VBOs are commonly used with draw calls such as:
```
glDrawArrays()
glDrawElements()
```

---

## **How its Used**

VBOs are used heavily in:

* modern OpenGL rendering
* game engines
* voxel engines
* real-time graphics systems

In voxel engines specifically:

1. A **chunk mesh** is generated.
2. The mesh is stored in a **VBO**.
3. The entire chunk is rendered with **one draw call**.

When the chunk changes, the VBO is **rebuilt and updated**.

---

## **Example**

Creating a VBO in OpenGL:
```
GLuint vbo;
glGenBuffers(1, &vbo);
glBindBuffer(GL_ARRAY_BUFFER, vbo);
glBufferData(GL_ARRAY_BUFFER, size, vertexData, GL_STATIC_DRAW);
```

Rendering the VBO:
```
glBindBuffer(GL_ARRAY_BUFFER, vbo);
glDrawArrays(GL_TRIANGLES, 0, vertexCount);
```

Voxel example:

* A chunk contains **4096 blocks**
* The engine generates vertex data only for **visible faces**
* That vertex data is stored in a **VBO**
* The chunk is rendered with **one draw call**

---

## **Details**

**Advantages**
* very fast rendering
* reduces CPU overhead
* data stored directly on GPU

**Disadvantages**
* harder to debug
* requires more setup than older rendering modes

Important idea:
```
CPU → Upload data → GPU memory → Reused for rendering
```

---

## **Related**

* [[Vertex Array]]
* [[Draw Call]]
* [[Chunk]]
* [[Display List]]

---

## **One Line Recall**

A **Vertex Buffer Object** stores vertex data in GPU memory for fast rendering.