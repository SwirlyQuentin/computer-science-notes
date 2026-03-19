---
aliases:
  - Block
---
## **Quick Summary**

A block is the data object that represents a voxel in the engine.

---

## **Core Idea**

The **Block class** stores the minimal information required to represent a voxel in the world.

Because voxel worlds contain **millions of blocks**, the block class must remain **small and efficient**.

---

## **What it is**

In a voxel engine, a **Block** is the class or structure used to represent a voxel.

It typically stores only essential information such as:

* whether the block is **active**
* the **[[block type]]**

Important design decisions:

* **Block position is not stored**
* position can be inferred from the **block's index in the world array**

Example storage:
```
Block blocks[worldX][worldY][worldZ];
```

The array indices determine the block's position, keeping the memory footprint **much smaller**.

---

## **How its Used**

The block class is used when:

* generating the voxel world
* modifying terrain
* saving/loading the game
* determining which voxels should be rendered
* building **[[chunk]] meshes**

---

## **Example**

Simple block structure:
```
class Block {
    bool active;
    int type;
}
```

Position of block:
```
blocks[10][5][20]
```

This corresponds to world position:
```
(x=10, y=5, z=20)
```

No position variable is required.

---

## **Details**

**Minimal storage**
* voxel worlds can contain millions of blocks

**Procedural derivation**
* properties like normals or textures should be derived from [[block type]]

**Serialization**
* blocks must be saved efficiently to disk

---

## **Related**

* [[Voxel]]
* [[Block Type]]
* [[Active Block Flag]]
* [[Chunk]]

---

## **One Line Recall**

The **Block class** stores the minimal data needed to represent a voxel.