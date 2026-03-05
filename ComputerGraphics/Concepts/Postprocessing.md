**Definition:**
Postprocessing is a stage in the graphics pipeline where **image effects are applied _after_ the scene has been rendered**, operating directly on the final [[Discrete Image]] (usually from the [[Frame Buffer]]).

It modifies the completed image rather than the geometry or lighting calculations.


### **Core Idea**
- Happens **after** [[Rasterization]]
- Operates on pixels **NOT** 3D geometry
- Implemented as full screen effects
- Enhances visual quality or style

### **Where it happens in the pipeline**

>[[Preprocessing]] -> Scene -> [[Rasterization]] -> [[Frame Buffer]] -> **Postprocessing** -> Screen


### **Common Postprocessing Effects**

#### 1. Bloom
- Makes bright areas glow
- Simulates light bleeding

#### 2. Motion Blur
- Blurs moving objects
- Simulates camera exposure time

#### 3. Depth of Field
- Blurs background or foreground
- Simulates camera lens focus

#### 4. Color Grading
- Adjusts contrast, saturation, tint
- Often uses lookup tables (LUTs)

#### 5. Tone Mapping
- Converts HDR values to displayable range
- Essential for realistic lighting

#### 6. Screen Space Effects
- SSAO (Screen Space Ambient Occlusion)
- Screen Space Reflections


### **Why \"Post\" processing**

It processes the already rendered image
- NOT scene geometry
- NOT lighting equations directly

It treats the rendered result like an image in image processing