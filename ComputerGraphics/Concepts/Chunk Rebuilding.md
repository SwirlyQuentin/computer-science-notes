## **Quick Summary**

Chunk rebuilding is the process of regenerating a chunk's mesh when blocks change.

---

## **Core Idea**

When a voxel changes state, the chunk's geometry must be **recalculated and updated**.

---

## **What it is**

Chunk rebuilding occurs when the voxel data in a chunk changes.

Examples:

* placing a block
* destroying a block
* toggling block activity

Since the chunk is rendered as a **single mesh**, any change requires regenerating that mesh.

Steps typically include:

1. Clear previous mesh
2. Loop through blocks in the chunk
3. Add geometry for active blocks
4. Upload mesh to GPU

---

## **How its Used**

Chunk rebuilding happens when:

* players modify terrain
* procedural generation updates terrain
* blocks are toggled on/off

If the modified block lies on a **chunk border**, neighboring chunks may also need rebuilding.

---

## **Example**

Player removes block at:
```
(15, 8, 7)
```

This block lies on the edge of a chunk.

Result:

* current chunk rebuild
* neighboring chunk rebuild

---

## **Details**

| Chunk Size   | Draw Calls | Rebuild Speed |
| ------------ | ---------- | ------------- |
| Large chunks | Fewer      | Slower        |
| Small chunks | More       | Faster        |

---

## **Related**

* [[Chunk]]
* [[Voxel]]
* [[Draw Call]]

---

## **One Line Recall**

Chunk rebuilding regenerates a chunk's mesh after voxel changes.