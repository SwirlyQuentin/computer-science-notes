## **Quick Summary**
A Discrete Image is a digital image represented as a finite grid of pixels. Each pixel exists at integer coordinates and stores a quantized color or intensity value, allowing the image to be stored, processed, and displayed by computers.

## **Core Idea**
- Defined only at **integer pixel coordinates** $(x, y)$
- Stored as a **2D array in memory**
- Each pixel contains a **quantized color value**
- Represents a **sampled version of a real-world image**
- Forms the basis of [[Raster Graphics]] and the [[Frame Buffer]]

Discrete images are the standard representation used in **digital imaging systems and computer graphics**.

## **What it is**
A Discrete Image is a digital representation of an image created by sampling a continuous visual scene at specific spatial locations and storing the resulting values in a finite grid.

Mathematically, a discrete image can be represented as a function:

$$I(x, y)$$

Where:
- $x, y \in \mathbb{Z}$ (integer coordinates)
- $I(x, y)$ represents the pixel value (color or intensity)

Each pixel corresponds to a single location in the grid, and its stored value represents the color or brightness at that point.

Because the image is sampled at discrete locations and stored with finite precision values, it is an **approximation of a [[Continuous Images|Continuous Image]]**.

Discrete images are used for:
- digital photography
- computer graphics rendering
- video frames
- image processing

## **How its Used**
Discrete images are the fundamental format used by nearly all digital imaging systems.

They are used in:

- digital cameras
- computer displays
- video frames
- image processing algorithms
- graphics rendering pipelines

In computer graphics, rendered scenes are written into a [[Frame Buffer]] as discrete pixel values before being displayed.

Discrete images also serve as the input and output for **image processing pipelines**, where operations such as filtering, scaling, and transformations are applied.

## **Example**

### Example 1: Pixel Grid Representation

A small discrete image might look like:
```
[120][135][140]
[100][115][130]
[ 90][105][110]
```

Each number represents a pixel intensity value.

### Example 2: Mathematical Representation

A discrete grayscale image might be defined as:

$$I(2,3) = 150$$

Meaning the pixel at coordinate $(2,3)$ has intensity value **150**.

### Example 3: Resolution

An image with resolution:

$$1024 \times 768$$

contains:

$$786,432 \text{ discrete pixels}$$

Each pixel stores a color value.

## **Details**

### Spatial Discretization
The image exists only at specific grid locations.

$$(x,y) \in \mathbb{Z}$$

This means the image contains **no direct information about positions between pixels**.

### Intensity (Color) Discretization
Pixel values are stored using finite precision values.

For example, an 8-bit grayscale image stores intensities:

$$0 \le I(x,y) \le 255$$

This limits the number of possible colors or intensities.

### Sampling
Discrete images are typically produced by **sampling a continuous image**, meaning measurements are taken at specific spatial locations.

This is why discrete images are often described as **sampled approximations of continuous scenes**.

## **Related**
[[Continuous Images]]
[[Raster Graphics]]
[[Frame Buffer]]
[[Pixel]]
[[Image Processing]]

## **One Line Recall**
A discrete image is a finite grid of pixels stored at integer coordinates where each pixel holds a quantized color value.