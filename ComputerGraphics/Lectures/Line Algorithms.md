

### **Discrete vs Continuous Images**

 Two kinds of images
 
[[Discrete Image]]
- How images are stored in memory
- Stored in a grid of pixels
- Finite not infinite

[[Continuous Images]]
- Images in the real world
- Example: Gaussian distribution


### **Image Processing Pipeline**

#### **Stage 1: Image Acquisition**

- **Image synthesis**
	- Images created by computer
	- Painted in 2D
		- Photoshop
		- Gimp 
		- etc
	- Rendered from 3D geometry
	- Procedurally Textured
- **Image Capture**
	- Images from the real world
	- information digitized from an analog signal
		- Camera
		- Satelite
		- etc


#### **Stage 2:  [[Preprocessing]]**

- Source image adjusted to fit a given tone, size, shape, etc.. to match a desired quality
- Can make disimilar images seem similar

**Techniques:**
- Color or greyscale curve
- Cropping
- Masking
- Blurring + Sharpening
- Antialiasing
- Scaling

*Some preprocessing effects can also be postprocessing effects*

#### **Stage 3: Mapping**

Mapping is a catch-all stage where several images are combined, or geometric transformations are applied

**Transformations Include**
- Rotating
- Scaling
- Shearing
- Warping

**Compositing:**
- Basic image overlay
- Smooth blending with alpha channels
- Poisson image blending


#### **Stage 4: [[Postprocessing]]**

- Creates global effects across an entire image or area

**Art Effects:**
- Posterizing 
- Faked aging of image
- Texturizing

**Technical Effects:**
- Color remapping to enhance contrast
- Color to B & W


#### **Stage 5: Output**

Choice of display may effect earlier processing stages

- Colors on monitors have different gamuts and HSV values

Different Display Technologies:
- Monitor (LED, OLED, LCD)
- Printer
- DVD


### **Drawing a Line Using the [[Midpoint Line Algorithm]]**
