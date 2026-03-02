**Definition:**  
Clip space is a **coordinate system in the graphics pipeline where vertices are tested against the viewable volume (frustum) before being projected to the screen**.

It’s an intermediate space between **camera/view space** and **normalized device coordinates (NDC)**.

### **Core Idea**
1. Vertices are transformed from **world space → camera/view space**
2. Then multiplied by the **[[Projection Matrix]]** → now in **clip space**
3. **Clipping** happens: vertices outside the view [[Frustrum | frustrum]] are discarded or split
4. Perspective divide converts clip space → NDC → screen coordinates


### **Key Points**
- Coordinates in clip space are [[Homogeneous | homogeneous]]
- Clipping ensures only the visible parts of the scene are processed further
- Both Perspective and Orthographic projections produce clip space coordinates
- Essential step before [[Rasterization | rasterization]]
