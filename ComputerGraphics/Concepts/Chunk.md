## **Quick Summary**

A chunk is a group of blocks bundled together for efficient rendering.

---

## **Core Idea**

Chunks reduce the number of **draw calls** by allowing many blocks to be rendered at once.

---

## **What it is**

A **chunk** is a 3D collection of voxels grouped together.

Typical chunk size:
```
16 × 16 × 16 blocks
```

Chunks are used because rendering each block individually would create too many GPU draw calls.

Instead:

* a chunk generates **one mesh**
* that mesh is rendered with **one [[draw call]]**

---

## **How its Used**

Chunks are used for:

* rendering optimization
* world streaming
* memory management

Voxel engines load and unload chunks dynamically depending on player position.

---

## **Example**

World size:
```
256 × 256 × 256 blocks
```

Total blocks:
```
16,777,216
```

Total chunks:
```
(256 / 16)^3 = 16^3 = 4096 chunks
```

Rendering:
```
4096 draw calls instead of 16,777,216
```

---

## **Details**

Chunks allow efficient rendering, infinite world generation, and localized updates.

However, modifying blocks requires **rebuilding the chunk mesh**.

---

## **Related**

* [[Voxel]]
* [[Chunk Rebuilding]]
* [[Draw Call]]

---

## **One Line Recall**

A **chunk** is a group of voxels rendered together to reduce draw calls.