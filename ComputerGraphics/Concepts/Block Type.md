## **Quick Summary**

Block type identifies what kind of block a voxel represents.

---

## **Core Idea**

Instead of storing detailed visual information per block, the engine stores a **type ID** which determines its appearance and behavior.

---

## **What it is**

A **Block Type** is an identifier that describes what a block represents in the world.

Examples:

* Dirt
* Grass
* Stone
* Sand
* Water

The block type determines:

* texture
* color
* physical properties
* interaction behavior

Instead of storing textures for every voxel, the engine maps:
```
blockType → texture + color + properties
```

This greatly reduces memory usage.

---

## **How its Used**

Block types are used to:

* determine which texture to render
* determine gameplay interactions
* determine block physics

Voxel engines typically store block types as integers:
```
0 = Air
1 = Dirt
2 = Grass
3 = Stone
```

---

## **Example**

Block data:
```
Block {
    active = true
    type = 2
}
```

Lookup table:
```
BlockType[2] = Grass
texture = grass.png
```

The renderer uses the lookup to determine the block's appearance.

---

## **Details**

**Memory efficiency**
* only a small integer stored per block

**Procedural rendering**
* textures derived during rendering

**Expandable**
* easy to add new block types

---

## **Related**

* [[Block (Voxel Block Class)]]
* [[Texture Coordinates]]
* [[Voxel]]

---

## **One Line Recall**

A **block type** determines the visual and physical properties of a block.