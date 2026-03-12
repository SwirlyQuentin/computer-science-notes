## **Quick Summary**
The Frame Buffer is a region of memory that stores the color values for every pixel that will appear on the screen for the current frame. It acts as the final image produced by the rendering pipeline before being displayed.

## **Core Idea**
- The frame buffer can be thought of as a **2D array of pixels stored in memory**
- Each pixel stores **color information**
- Rendering operations write pixel values into this buffer
- Once rendering is complete, the buffer is sent to the display hardware

Typical stored values include:
- RGB color values
- Alpha (transparency)

All rendering operations ultimately modify the [[Frame Buffer]].

## **What it is**
A Frame Buffer is a block of memory used by the graphics system to store the image that will be shown on the screen. Each position in the buffer corresponds to one pixel on the display.

Mathematically it can be viewed as a 2D array:

$$FrameBuffer[x, y] = Color$$

Where:
- $x, y$ represent pixel coordinates
- the stored value represents the pixel's color

For example, on a **1920 × 1080 display**, the frame buffer must store:

$$1920 \times 1080 = 2,073,600 \text{ pixels}$$

If each pixel uses **32-bit color (RGBA)**:

$$2,073,600 \times 32 \text{ bits} = 66,355,200 \text{ bits}$$

$$\approx 8 \text{ MB of memory}$$

This memory stores the complete image for a single frame.

## **How its Used**
The Frame Buffer is the **final output target of the graphics pipeline**.

Typical rendering process:

1. The application describes the scene using the [[Application Model]].
2. The graphics system processes geometry and shading.
3. The renderer computes the final pixel colors.
4. These colors are written into the [[Frame Buffer]].
5. The display hardware reads the frame buffer and draws it to the screen.

In raster-based systems, nearly all graphics ultimately end up as **pixel values stored in the frame buffer**.

Frame buffers are used in:
- game engines
- operating system graphics systems
- GPUs
- video playback
- GUI rendering
- real-time graphics pipelines

## **Example**

### Example 1: Frame Buffer as a 2D Pixel Grid

A very small frame buffer might look like:
```
[ R ][ G ][ B ]
[ B ][ R ][ G ]
[ G ][ B ][ R ]
```

Each cell represents a pixel with a stored color value.

### Example 2: Writing a Pixel

Rendering operations may update individual pixels:
```pseudo
FrameBuffer[200, 150] = (255, 0, 0)
```

This sets the pixel at position (200,150) to red.

### Example 3: Rendering a Triangle

When a triangle is rasterized, all pixels inside the triangle are assigned colors and written into the frame buffer.

$$FrameBuffer[x,y] = C_{triangle}$$

for all pixels covered by the triangle.

## **Details**

### Color Depth
Each pixel in the frame buffer stores a fixed number of bits.

Common formats:
- **24-bit color** → RGB (8 bits per channel)
- **32-bit color** → RGBA (RGB + Alpha)

### GPU Memory
Modern GPUs store frame buffers in video memory (VRAM) for fast access during rendering and display.

### Double Buffering
To avoid flickering during rendering, systems often use [[Double Buffer]] techniques:
- **Back Buffer** → frame currently being rendered
- **Front Buffer** → frame currently displayed

Once rendering finishes, the buffers are swapped.

### Raster Displays
Raster displays read pixel values sequentially from the frame buffer to generate the image shown on the screen.

## **Related**
[[Raster Graphics]]
[[Double Buffer]]
[[Application Model]]
[[Display Model]]

## **One Line Recall**
The Frame Buffer is the memory region that stores the final pixel colors for the frame that will be displayed on the screen.