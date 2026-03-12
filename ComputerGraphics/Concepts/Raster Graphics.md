## **Quick Summary**
Raster Graphics represent images as a grid of colored pixels. Each pixel stores a color value, and when all pixels are displayed together they form the final image shown on the screen.

## **Core Idea**
- Images are stored as a **2D grid of pixels**
- Each pixel contains a **color value**
- The image is stored in a [[Frame Buffer]] or image memory
- Quality depends on **resolution (number of pixels)**
- Enlarging the image reveals individual pixels, causing **pixelation**

Raster graphics are the dominant representation used in modern display systems.

## **What it is**
Raster graphics represent images using a rectangular grid of picture elements called **pixels**. Each pixel stores color information, usually encoded using a color model such as RGB.

The raster image can be thought of as a **2D array**:

$$Image[x,y] = Color$$

Where:
- $x, y$ represent pixel position
- the stored value is the color at that pixel

For example, a display with resolution **1920 × 1080** contains:

$$1920 \times 1080 = 2,073,600 \text{ pixels}$$

Each pixel is individually stored and rendered to produce the final image.

Raster graphics are **resolution dependent**, meaning image quality depends on the number of pixels available. When the image is enlarged beyond its original resolution, the pixels become visible and the image appears blocky or blurry.

Most modern computer graphics systems use raster graphics because display hardware renders images as pixel grids.

## **How its Used**
Raster graphics are used whenever images must be displayed on digital screens.

Common uses include:

- digital photography
- video
- computer monitors
- game rendering pipelines
- image editing software
- web graphics

In computer graphics pipelines, the final rendered image is stored in the [[Frame Buffer]] as a raster image. The GPU calculates colors for pixels during the **rasterization stage**, converting geometric primitives like triangles into pixel values.

Raster graphics are especially useful for:
- complex shading
- realistic lighting
- texture mapping
- photographic detail

## **Example**

### Example 1: Pixel Grid Representation

A very small raster image might look like this:
```
[ R ][ G ][ B ]
[ B ][ R ][ G ]
[ G ][ B ][ R ]
```

Each square represents a **pixel with a stored color value**.

### Example 2: Image Resolution

An image with resolution:

$$800 \times 600$$

contains:

$$480{,}000 \text{ pixels}$$

If each pixel stores **24-bit color (8 bits per RGB channel)**:

$$480{,}000 \times 24 = 11{,}520{,}000 \text{ bits}$$

$$= 1.44 \text{ MB}$$

### Example 3: Pixelation When Zooming

If a 200×200 raster image is enlarged to 800×800 without interpolation, each original pixel becomes a large block, producing visible **pixelation**.

## **Details**

### Resolution
Resolution refers to the number of pixels in an image:

$$Resolution = Width \times Height$$

Higher resolution produces:
- more detail
- smoother images
- larger memory requirements

### Frame Buffer Storage
In graphics hardware, raster images are stored in a [[Frame Buffer]], which is a memory region containing the pixel values that will be displayed on the screen.

### Color Depth
Each pixel stores color using a certain number of bits.

Common examples:

- **24-bit color** → 8 bits per RGB channel
- **32-bit color** → 24-bit color + 8-bit alpha transparency

### Rasterization
In 3D graphics, objects defined by triangles are converted into pixels through a process called **rasterization**, which determines which pixels are covered by each primitive.

## **Related**
[[Vector Graphics]]
[[Frame Buffer]]
[[Rasterization]]
[[Pixel]]
[[Resolution]]

## **One Line Recall**
Raster graphics represent images as a grid of colored pixels stored in memory and displayed on the screen.