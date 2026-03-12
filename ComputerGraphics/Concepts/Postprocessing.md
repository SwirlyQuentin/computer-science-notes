## **Quick Summary**
Postprocessing is a stage in the graphics pipeline where visual effects are applied to the final rendered image. These effects operate directly on pixel data from the [[Frame Buffer]] rather than modifying scene geometry or lighting calculations.

## **Core Idea**
- Occurs **after [[Rasterization]]**
- Operates on **pixels, not 3D geometry**
- Implemented as **full-screen image effects**
- Enhances visual quality, realism, or artistic style

In the pipeline:

$$[[Preprocessing]] \rightarrow Scene \rightarrow [[Rasterization]] \rightarrow [[Frame Buffer]] \rightarrow Postprocessing \rightarrow Screen$$

The scene has already been rendered; postprocessing modifies the **resulting image**.

## **What it is**
Postprocessing is a stage where image-based operations are applied to the final rendered frame. Instead of recalculating geometry, lighting, or materials, the system treats the rendered output as a [[Discrete Image]] and performs image processing operations on it.

This stage typically uses **full-screen shaders** or image filters that read pixel values from the [[Frame Buffer]] and compute new values.

Because postprocessing operates on the completed image, it can efficiently apply global visual effects across the entire frame.

The result is a modified image that is then displayed on the screen.

## **How its Used**
Postprocessing is widely used in modern graphics systems such as:

- video games
- film rendering
- real-time engines
- image editing pipelines
- virtual reality rendering

In real-time graphics engines, postprocessing is usually implemented as **screen-space effects**, meaning calculations are based only on the rendered image and additional buffers (such as depth buffers).

Typical workflow:

1. The scene is rendered and stored in the [[Frame Buffer]].
2. A postprocessing shader reads the image.
3. Image filters or effects are applied.
4. The processed image is written back to the display buffer.
5. The final frame is presented on the screen.

This allows developers to add cinematic effects without modifying the original scene geometry.

## **Example**

### Example 1: Bloom Effect

Bloom makes bright pixels spread light to surrounding pixels.

A simplified approach:

$$I_{bloom}(x,y) = I(x,y) + k \cdot Blur(Bright(I(x,y)))$$

Where:
- $I(x,y)$ is the original pixel value
- $Bright()$ extracts high-intensity pixels
- $Blur()$ spreads the light
- $k$ controls bloom intensity

### Example 2: Motion Blur

Motion blur approximates camera exposure by blending frames or sampling motion vectors:

$$I_{blur}(x,y) = \frac{1}{n}\sum_{i=0}^{n} I(x + v_i, y + v_i)$$

Where $v_i$ represents motion direction.

### Example 3: Color Grading

Color grading applies a transformation to each pixel's color:

$$C_{final} = LUT(C_{original})$$

Where **LUT** is a lookup table used to remap colors.

## **Details**

### Common Postprocessing Effects

**Bloom**
- Creates glowing highlights
- Simulates light bleeding from bright sources

**Motion Blur**
- Blurs moving objects
- Simulates camera exposure time

**Depth of Field**
- Blurs foreground or background
- Simulates camera focus

**Color Grading**
- Adjusts contrast, saturation, and tone
- Often implemented with lookup tables

**Tone Mapping**
- Converts high dynamic range values to displayable ranges
- Essential for HDR rendering

**Screen Space Effects**
Effects computed using screen-space data:
- Screen Space Ambient Occlusion (SSAO)
- Screen Space Reflections (SSR)

### Screen-Space Processing
Postprocessing effects operate only on **screen data**, meaning they do not require knowledge of the full 3D scene.

This makes them efficient and widely used in real-time graphics.

### GPU Implementation
Most postprocessing effects are implemented using **fragment shaders** that process every pixel of the frame.

## **Related**
[[Preprocessing]]
[[Rasterization]]
[[Frame Buffer]]
[[Discrete Image]]
[[Image Processing Pipeline]]

## **One Line Recall**
Postprocessing applies visual effects to the final rendered image by operating directly on pixels from the frame buffer.