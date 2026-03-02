Used to prevent flickering that happens when the frame buffer is displayed before the rendering pipeline gets a chance to finish

Prevents flickering:
- Back buffer -> where drawing happes
- Front buffer -> currently displayed image

They swap after rendering completes


**Definition:**
Double buffering is a technique that uses **two frame buffers** to prevent flickering and visual artifacts during rendering.

### **The Problem**
When drawing directly to the screen while it's being displayed the rendering pipeline could take longer than it takes to display the buffer resulting in:
- Flickering
- Tearing
- Partially drawn frames

### **How it Works**

Uses two buffers:
1. Front Buffer -> currently displayed on screen
2. Back Buffer -> where the next frame is being drawn

Process:
1. Render the entire frame into the **back buffer**.
2. When rendering is complete, **swap the buffers**.
3. The back buffer becomes the front buffer (now visible).
4. Repeat for the next frame.

This makes the image appear instantly updated.

### **Importance**

- Smoother animation
- Eliminates flicker
- Standard in modern graphics systems
- Used in games, UI, and GPUs
- Used in systems like [[OpenGL]] and Unity