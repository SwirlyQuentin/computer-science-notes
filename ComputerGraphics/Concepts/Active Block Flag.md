---
aliases:
  - Active Flag
---

## **Quick Summary**

The active flag determines whether a block exists or is empty.

---

## **Core Idea**

Only **active blocks are rendered** in a voxel engine. Inactive blocks represent **empty space**.

---

## **What it is**

The **Active Block Flag** is a boolean value stored in each block indicating whether the voxel is present.

Possible values:
```
true  → block exists
false → empty space
```

During rendering, only blocks with `active = true` are processed.

This allows worlds to contain **air spaces without storing full block data**.

---

## **How its Used**

The active flag is used when:

* generating terrain
* modifying blocks
* building [[chunk]] meshes
* rendering voxels

If a block becomes inactive, it disappears from the world.

---

## **Example**

Block data:
```
Block {
    active = false
    type = 0
}
```

Renderer behavior:
```
if block.active:
    render block
```

Inactive blocks produce **no geometry**.

---

## **Details**

**Performance**
* prevents rendering unnecessary blocks

**World editing**
* blocks can be turned on/off dynamically

**Memory efficiency**
* avoids storing empty geometry

---

## **Related**

* [[Block (Voxel Block Class)]]
* [[Chunk]]
* [[Draw Call]]

---

## **One Line Recall**

The **active flag** determines whether a voxel should exist and be rendered.