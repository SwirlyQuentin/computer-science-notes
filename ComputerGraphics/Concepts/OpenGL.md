**Definition:**
OpenGL (Open Graphics Library) is a **cross-platform API for rendering 2D and 3D graphics**, primarily using **immediate mode** or modern shader-based pipelines.

### **Core Idea**

- Provides functions to draw shapes, textures, and 3D objects
- Works with GPU for hardware accelerated rendering
- Lets applications control every step of the graphics pipeline

### **Features**

- Supports 2D and 3D graphics
- uses buffers ([[Vertex Buffer]], [[Frame Buffer]]) for storing data
- Handles transformations, lighting, and texturing
- Cross-platform
- Evolved past [[Immediate Mode]], however in this class we only use this mode


## **Coordinate Systems**

OpenGL uses coordinate systems that are defined by the user to draw to the buffers

**Convention**:
- x -> Increases right 
- y -> Increases up

**Units:**
- Units are based on the size of the window or screen
- Visible area stretches to fill window
- Units are a **PERCENTAGE** of window size, they do not correspond to physical units or pixels

**Defining a Coordinate System:**
- defined using a [[Projection Matrix]]
- Supplied to shader as a uniform variable

#### **[[Basic OpenGL Demo]]**

