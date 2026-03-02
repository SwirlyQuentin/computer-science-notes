**Definition:**
A frame buffer is a region of memory that stores the **color values of every pixel** that will be displayed on the screen for one frame.


### **Core Idea**

***Think:** 2D array of pixels in memory*

Each pixel in the frame buffer holds information like:
- RGB values
- Alpha

When rendering is finished, the GPU sends the frame buffer's contents to the display

##### **Importance**

- It's the **FINAL** destination of the rendering pipeline
- All Drawing operations ultimately modify the frame buffer


### **Related**
[[Double Buffer]]

