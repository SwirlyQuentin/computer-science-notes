**Definition:**
A projection matrix is a **mathematical matrix used to map 3D points in world or camera space onto a 2D screen** ([[Clip Space]]) for rendering.

It defines how the 3D scene is projected onto a flat surface

### **Core Idea**

- Converts 3D coordinates -> 2D coordinates
- Controls perspective, field of view, and clipping planes
- Essential in the 3D graphics pipeline

### **Types of Projection**

1. **Perspective Projection**
	- Mimics human vision
	- Farther objects appear smaller
	- Used in most 3D games and simulations
2. **Orthographic Projection**
	- No perspective shrinkage
	- Parallel lines remain parallel
	- Used in CAD, UI rendering, and 2D games


### **How it Works Conceptually**

1. 3D vertex in world space -> transformed to camera/view space
2. Multiply by projection matrix -> maps to [[Clip Space]]
3. Perform perspective divide -> normalized device coordinates
4. Map to screen coordinates -> viewport