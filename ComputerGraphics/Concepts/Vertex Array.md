---
aliases:
  - Vertex Arrays
---

## **Quick Summary**

A vertex array stores vertex data in CPU memory and sends it to the GPU in a single draw call.

---

## **Core Idea**

Instead of sending vertices one at a time, vertex arrays send **an entire array of vertices at once**, making rendering faster.

---

## **What it is**

A **Vertex Array** is a method in OpenGL where vertex data is stored in **arrays** and then sent to the GPU in a single operation.

Typical vertex arrays store:

* vertex positions
* normals
* texture coordinates
* colors

The arrays are passed to the GPU during rendering.

This approach is much faster than **[[Immediate Mode]]**, where vertices are sent individually.

However, vertex arrays are still slower than **VBOs**, because the data is transferred from CPU memory each frame.

---

## **How its Used**

Vertex arrays are used when:

* rendering large sets of geometry
* dynamically modifying vertex data
* batching geometry into fewer draw calls

In voxel engines:

1. Vertex data for a chunk is stored in arrays.
2. The arrays are sent to the GPU in a **single draw call**.

---

## **Example**

Vertex array example:
```
float vertices[] = {
    0.0f, 0.0f, 0.0f,
    1.0f, 0.0f, 0.0f,
    0.0f, 1.0f, 0.0f
};
```

Enable vertex array:
```
glEnableClientState(GL_VERTEX_ARRAY);
glVertexPointer(3, GL_FLOAT, 0, vertices);
```

Draw the array:
```
glDrawArrays(GL_TRIANGLES, 0, 3);
```

---

## **Details**

**Advantages**
* faster than [[Immediate Mode]]
* supports dynamic modification
* allows batching of vertices

**Disadvantages**
* vertex data must be sent from CPU every frame
* slower than VBOs

Performance ranking (slowest to fastest):
```
[[Immediate Mode]]
Vertex Arrays
[[Display List|Display Lists]]
Vertex Buffer Objects
```

---

## **Related**

* [[Vertex Buffer Object (VBO)]]
* [[Immediate Mode]]
* [[Draw Call]]

---

## **One Line Recall**

A **vertex array** stores vertex data in arrays and renders them in one draw call.