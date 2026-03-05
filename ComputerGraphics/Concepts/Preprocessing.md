**Definition:**
Preprocessing is the stage in computer graphics (or image processing) where **data is prepared, transformed, or optimized before the main rendering or processing step occurs**.

It improves performance, quality, or efficiency during the actual runtime pipeline.

### **Core Idea**
- Happens **before** rendering or analysis
- Converts raw data into more usable form
- Trades memory for speed; Optimizes rendering
- Reduces computation during real time execution
- Also applies different effects to an image

### **Why it Happens**

Some operations are too expensive to do multiple times when needed

Instead of every frame:

> Compute once -> store result -> reuse later

**Important in:**
- Real time graphics
- Game Engines
- Image processing pipelines

### **Common Types of Preprocessing in Graphics**

1. **Geometry Preprocessing**
	- Computing normals in advance
	- Building bounding volumes
	- Creating level-of-detail ([[LOD]]) meshes

2. **Lighting Preprocessing**
	- Lightmaps
	- Precomputed global illumination
	- Shadow maps
	- Lighting baking (in game engines)

3. **Texture Preprocessing**
	- Generating [[Mipmaps | mipmaps]]
	- Texture compression
	- Pre-filtering textures

4. **Image Processing Preprocessing**
	- Noise reduction
	- Histogram equalization
	- Edge detection preparation

### **Performance Tradeoff**

Preprocessing often:
- Increases memory usage
- **Reduces** runtime CPU/GPU cost
- Improve frame rate stability