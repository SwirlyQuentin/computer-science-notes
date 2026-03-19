## **Quick Summary**

A draw call is a command sent from the CPU to the GPU to render geometry.

---

## **Core Idea**

Draw calls are expensive operations, so graphics engines try to **minimize the number of them**.

---

## **What it is**

A **draw call** is a command issued by the CPU instructing the GPU to render a set of vertices.

Examples of OpenGL draw calls:
```
glDrawArrays()
glDrawElements()
```

Each draw call tells the GPU:

* what geometry to render
* what buffers to use
* what shaders to apply

Too many draw calls can cause **CPU bottlenecks**.

---

## **How its Used**

Voxel engines reduce draw calls by:

* grouping blocks into chunks
* building chunk meshes
* rendering each chunk once

This dramatically improves performance.

---

## **Example**

Without chunks:
```
16,777,216 blocks = 16,777,216 draw calls
```

With chunks:
```
4096 draw calls
```

---

## **Details**

Reducing draw calls is a **major graphics optimization technique**.

Common methods:

* batching
* instancing
* chunk rendering
* vertex buffers

---

## **Related**

* [[Chunk]]
* [[Vertex Buffer Object]]
* [[Vertex Array]]

---

## **One Line Recall**

A **draw call** is a command that tells the GPU to render geometry.