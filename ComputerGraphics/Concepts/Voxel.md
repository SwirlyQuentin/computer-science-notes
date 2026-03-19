## **Quick Summary**

A voxel is a volumetric pixel — a small cube representing a unit of space in a 3D grid.

---

## **Core Idea**

Voxels divide 3D space into a grid of small cubes where each cube stores data about that part of the world.

This allows environments to be represented as **editable 3D grids**, making them easy to modify dynamically.

---

## **What it is**

A **voxel (volume pixel)** is the basic unit of a voxel-based world.

Instead of representing objects with polygon meshes (like traditional 3D graphics), voxel engines represent the world as a **3D grid of cubes**.

Each voxel may contain information such as:

* Whether it is **active or empty**
* The **type of material** (stone, dirt, water)
* Other metadata depending on the engine

Voxel worlds are typically stored as:
```
world[x][y][z]
```

Each index corresponds to a voxel at that location.

Voxel systems are commonly used for:

* destructible environments
* procedurally generated terrain
* large editable worlds

---

## **How its Used**

**Game engines**
* sandbox games (ex: Minecraft)
* destructible environments
* terrain systems

**Scientific visualization**
* medical imaging (CT scans)
* volumetric data

**Simulation**
* fluid simulations
* physics environments

Voxel engines rely on voxels because they allow **easy modification of the world at runtime**.

---

## **Example**

A small voxel grid:
```
3 × 3 × 3 grid
```

Total voxels:
```
3 * 3 * 3 = 27 voxels
```

Each voxel could store:
```
Voxel {
    bool active;
    int blockType;
}
```

If `active = false`, the voxel is empty and not rendered.

---

## **Details**

**Grid Based**
* voxels exist on a discrete grid

**Memory Heavy**
* worlds may contain **millions of voxels**

**Procedural Generation**
* engines often generate voxel worlds algorithmically rather than storing everything

---

## **Related**

* [[Block]]
* [[Chunk]]
* [[Procedural Generation]]
* [[Voxel Engine]]

---

## **One Line Recall**

A **voxel** is a cube-shaped unit representing a point in a 3D grid.