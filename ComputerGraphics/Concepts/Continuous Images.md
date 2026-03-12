## **Quick Summary**
A Continuous Image is an idealized representation of an image defined as a mathematical function over real-valued coordinates. It assumes intensity or color exists at every point in space, giving the image infinite resolution and detail.

## **Core Idea**
- Defined over **real coordinates** $(x, y) \in \mathbb{R}$
- Contains **no pixels**
- Has **infinite spatial resolution**
- Represents the **ideal version of an image before digitization**
- Must be converted into a [[Discrete Image]] through [[Sampling]]

Continuous images are theoretical models used to describe real-world visual scenes.

## **What it is**
A Continuous Image is a mathematical representation of an image where intensity or color is defined for every possible point in space.

It can be described as a continuous function:

$$I(x,y)$$

Where:
- $x,y \in \mathbb{R}$ (real numbers)
- $I(x,y)$ represents the intensity or color value at that exact location.

Unlike digital images, continuous images do not use pixels or grids. Instead, the image exists everywhere across the plane with infinite precision.

This representation is useful in image processing theory because real-world light distributions are naturally continuous. Cameras and scanners convert this continuous signal into a digital image by sampling it into a grid, producing a [[Discrete Image]].

## **How its Used**
Continuous images are primarily used as **theoretical models** in computer graphics and image processing.

They help describe:

- real-world light intensity distributions
- optical imaging systems
- mathematical image transformations
- signal processing theory

In practice, real-world images start as continuous signals (light intensity across space). Devices such as cameras convert these signals into discrete pixel values through **sampling and quantization**.

Typical workflow:

1. Real-world scene produces a **continuous light signal**.
2. Sensors sample the signal at discrete points.
3. Values are quantized into digital numbers.
4. The result becomes a [[Discrete Image]] stored in memory.

## **Example**

### Example 1: Continuous Intensity Function

A continuous grayscale image might be modeled as:

$$I(x,y) = e^{-(x^2 + y^2)}$$

This function defines intensity for **every possible coordinate** in the plane.

### Example 2: Gaussian Image

A common example of a continuous image model is a **Gaussian distribution**:

$$I(x,y) = A e^{-\frac{(x-\mu_x)^2 + (y-\mu_y)^2}{2\sigma^2}}$$

Where:
- $A$ controls intensity
- $\mu_x, \mu_y$ define the center
- $\sigma$ controls the spread

This produces a smooth image with no discrete pixels.

### Example 3: Sampling Into Pixels

If the continuous function is sampled at integer coordinates:

$$I(0,0),\ I(1,0),\ I(2,0)$$

the result becomes a **grid of sampled values**, forming a [[Discrete Image]].

## **Details**

### Infinite Detail
Because the image is defined over real numbers, it contains **information at every possible point**, allowing theoretically infinite detail.

### Infinite Precision
The function values are not limited to fixed bit depths like digital images. In theory, intensity values can have infinite precision.

### Not Directly Storable
Computers cannot store continuous images because digital memory requires finite representations. Continuous images must be **sampled and quantized** before they can be stored digitally.

### Relationship to Sampling
Continuous images are converted to digital form through the sampling process:

$$Continuous\ Image \rightarrow Sampling \rightarrow Discrete\ Image$$

This conversion is fundamental in digital imaging and signal processing.

## **Related**
[[Discrete Image]]
[[Sampling]]
[[Image Processing Pipeline]]
[[Gaussian Distribution]]

## **One Line Recall**
A continuous image is a mathematical function defined over real coordinates that represents an ideal image with infinite resolution and no pixels.